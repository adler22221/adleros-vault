# Handover Protocol — Manually Downloaded PDFs → Zotero → NotebookLM

> Established 2026-05-02 as part of REV-5 architecture upgrade.
> See plan: `~/.claude/plans/i-want-to-improve-compiled-pelican.md`

## Purpose

Many academic books are blocked from automated retrieval (libgen Cloudflare, Anna's Archive DNS issues, etc.). This protocol lets the user download PDFs manually and hand them off to Claude for processing — Claude attaches to Zotero (Pass 1) and uploads to NLM (Pass 2).

## Folder structure

```
P:\_AI agents\full-research-workflow\00Inbox\
├── pdfs-to-process/      ← Drop new PDFs here
└── pdfs-processed/
    └── <YYYY-MM-DD>/     ← Pass 1 moves files here after attaching
```

## Naming convention

`<author-lowercase><year>.pdf`

Examples:
- `eliade1954.pdf`
- `dalley2000.pdf`
- `stiegler-tc.pdf` (when author has multiple works in same year, append abbreviation)

## Two-pass workflow

### Pass 1 — Zotero attach (Phase 1+, ALWAYS runs first)

Trigger: User says "process the new PDFs" or "run Pass 1"

1. Claude scans `00Inbox/pdfs-to-process/` for `*.pdf`
2. For each file:
   - **Lookup** filename in `.research/handover-keymap.yml`
   - **If keymap entry has `status: need_zotero_item` OR filename is absent from keymap** →
     - Append entry to `.research/pending-manual-keymatch.md` with: filename, file size, suggested Zotero metadata fields (extracted via PDF metadata if possible)
     - Skip file (do NOT crash, do NOT attempt random key)
     - User reads `pending-manual-keymatch.md`, creates Zotero item manually, runs Better BibTeX `item.citationkey` JSON-RPC to get citekey, updates keymap, re-runs Pass 1
   - **Otherwise:**
     - Validate: `%PDF-` header (first 5 bytes), size ≥ 500 KB
     - Check `already_has_pdf(zotero_key)` via pyzotero `Zotero.children(key)` — return True if any child has `contentType == 'application/pdf'`
     - If has PDF: skip + log "already_attached" reason
     - Else: attach via `pyzotero.Zotero.attachment_simple([path], parentid=zotero_key)` (method confirmed available 2026-05-02)
     - Add tag `nlm:pending` to the Zotero item
     - Move file to `00Inbox/pdfs-processed/<YYYY-MM-DD>/<filename>` (use `os.makedirs(dest, exist_ok=True)`; ISO 8601 date format for sort-friendliness)
3. Log results to `.research/handover-log.md` (append; one row per file)

### Pass 2 — NLM upload (Phase 2+, runs after Pass 1)

Trigger: User says "run Pass 2" or "sync to NLM" or runs script directly

```bash
# From workspace root:
& "P:/_AI agents/full-research-workflow/.venv-nlm/Scripts/Activate.ps1"
python "research-hub/scripts/zotero_to_nlm.py" thesis-sources <a-sources-uuid> --pending
```

The script:
1. Reads `.research/nlm-notebooks.yml` for UUIDs (target must NOT be `c_audits` UUID — hard exclusion)
2. Queries Zotero for items in `thesis-sources` collection tagged `nlm:pending`
3. For each item:
   - Find attached PDF locally
   - Upload to NLM Notebook A with `--name <citekey>` (display name = citekey for verifier compatibility)
   - Replace `nlm:pending` tag with `nlm:synced` in Zotero
   - Append to `.research_hub/bundles/<a-uuid>/manifest.json`

## Collection sync (automated)

`collection_sync.py` keeps the `thesis-sources` collection aligned with what is actually cited in the drafts. Run it before Pass 1 or at any session start.

```bash
# Preview without changes
python "research-hub/scripts/collection_sync.py" --dry-run

# Apply adds (default — liberal: all cited/mentioned items)
python "research-hub/scripts/collection_sync.py"

# Remove uncited items (near-final draft only)
python "research-hub/scripts/collection_sync.py" --remove-mode --dry-run
python "research-hub/scripts/collection_sync.py" --remove-mode --confirm
```

**Tiers scanned:**
- Tier 0: `source-notes:` frontmatter + `[AI draft | ... | sources: ...]` header
- Tier 1: `[LOOKUP: ...]` tags
- Tier 2: `[VERIFY: confirmed | citekey | ...]` — CRITICAL flag if citekey not in Zotero
- Tier 3: inline BBT citekeys, Zotero keys, `Author (year)`, `— Author, First` attributions
- Tier 4: narrative mentions ("Illich argues", "as Stiegler notes")
- Tier 5: `[GENERATIVE: topic]` — batched full-text Zotero search

**Logs written:**
- `.research/collection-sync-log.md` — run summary per execution
- `.research/missing-from-zotero.md` — items cited in drafts but absent from Zotero (feeds [LOOKUP] pipeline)
- `.research/critical-flags.md` — Tier 2 CRITICAL: `[VERIFY: confirmed]` with no Zotero backing

**Dependencies:** `pyzotero`, `pyyaml`, `requests` (all in workspace env). Optional: `python-docx` for DOCX scanning.

---

## Re-upload mechanism

If user gets a better PDF version (e.g., cleaner scan replacing a stub):

```bash
python research-hub/scripts/zotero_to_nlm.py thesis-sources <a-uuid> --force <citekey>
```

This:
1. Removes existing NLM source by citekey display name
2. Re-uploads from current Zotero attachment
3. Updates manifest entry with new file_hash

## Edge cases

- **PDF in `pdfs-to-process/` with no matching keymap entry** → logged to `pending-manual-keymatch.md`; user must add Zotero item + update keymap
- **Zotero item already has a PDF** → skip with `already_attached` reason (idempotent)
- **PDF fails validation (header or size)** → logged to handover-log.md as `validation_failed`; file stays in `pdfs-to-process/` for user inspection
- **Network error during NLM upload** → tag stays `nlm:pending`; next `--pending` run retries
- **Notebook C-Audits UUID accidentally passed as target** → script exits with error; tag remains unchanged

## Privacy gate (enforced)

`zotero_to_nlm.py` only uploads items in the Zotero `thesis-sources` collection — explicit opt-in by user via Zotero collection membership. No DOI/ISBN gating (Better BibTeX may not capture these even when present).

See `CLAUDE.md` §2.5 for full upload policy.
