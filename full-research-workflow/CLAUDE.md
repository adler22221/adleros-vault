# CLAUDE.md — Rules of the Research Workspace
> Read this file before touching anything in this workspace.
> Last updated: 2026-05-26

---

## 1. Who This Is For

**Researcher:** Adler Yang (adler.yang@thesouledu.org)

**Active projects** (each = one specific submission; see §2.7 for ID convention):
| Project ID | Full title | Venue | Type | Status |
|------------|------------|-------|------|--------|
| `master-thesis` | Between the Universe and the Metaverse | Soochow University (東吳大學) | MA thesis | **IMMEDIATE** — submission 2026-05-31 |
| `planetarycrises-yearbookofedu-chapter` | Education and Planetary Crises (chapter proposal) | Routledge WYoE Vol 29 | book chapter proposal | **IMMEDIATE** — user target 2026-05-27, CFP deadline 2026-05-30 |

> New projects are added here when a submission becomes active. IDs follow the format `theme-target-type` (e.g., `metaverse-scu-thesis`). The current thesis uses the legacy ID `master-thesis`; post-submission it will be updated to `metaverse-scu-thesis`.

**Register:** Transdisciplinary / antidisciplinary. No default authorial voice. The appropriate register (formal academic, grant-proposal, public intellectual, Daoist/Zhuangzi-inflected, etc.) is determined by audience, publication context, and genre — not by a persistent signature. Each `Style-*.md` in `20Wiki/` is a standalone context specification, not a facet of a default voice. **When the target register is not specified in a task, ask before assuming.**

**Primary language:** English (academic writing). Secondary: Traditional Chinese, Japanese.

---

## 2. Workspace Layout

```
full-research-workflow/             ← also the Obsidian vault root (see §2.6)
├── CLAUDE.md                       ← this file
├── .obsidian/                      ← Obsidian vault config (exclusions, plugin settings)
├── 2ndbrain/                       ← symlink → C:\Users\adler-standard\Documents\Obsidian\2ndbrain
│                                      READ-ONLY intent — agent NEVER writes here
├── ThesisRevision/                 ← immediate prototype (see §7 for full rules)
│   ├── viva-passed-draft/          ← canonical ground truth, read-only
│   ├── revision-draft/             ← working DOCX
│   ├── reviewers-comments/         ← authoritative change instructions
│   ├── snippets/                   ← researcher's raw material (status: human-review)
│   ├── audit-notes/                ← Gemini/NLM pre-analysis (status: revision-staging)
│   ├── revision-board.html         ← interactive Phase A–E tracker (browser fallback)
│   └── 00-manifest.md              ← auto-generated revision map
├── 00Inbox/                        ← mobile captures, unsorted refs (READ + process; never write directly)
├── 10Literature/                   ← Zotero-synced notes (written ONLY via `agent compile` or Zotero Integration plugin)
├── 20Wiki/                         ← canonical pages + locked references + Canvas maps
│   ├── canvas/                     ← Obsidian Canvas .canvas files (visual argument maps)
│   ├── _templates/                 ← reusable page templates (project-hub-template.md, etc.)
│   ├── draft-status-board.md       ← Dataview board (thesis-specific phases + benchmark)
│   ├── project-status-board.base   ← Obsidian Base board: all submissions grouped by project
│   ├── [project-id].md             ← project hub pages (one per active submission, on demand)
│   ├── squeeze-ontology.md         ← locked canonical reference (F1–F5 + anti-metaphorical safeguards)
│   ├── top100-rubric-notes.md      ← locked canonical reference (D5/D6 benchmark)
│   ├── nlm-notebooks.md            ← human-readable NLM notebook registry
│   └── Style-*.md                  ← register/voice specs (standalone; not a default voice)
├── 30Drafts/                       ← ALL agent prose outputs (all projects); named [project-id]_[task]_[desc].md
│   └── _staging/                   ← revision-staging pre-briefs (AWAKE-COLLAB prep, not thesis prose)
└── .research/                      ← automation infrastructure only (see below)
    ├── logs/                       ← automation-log.md, nlm-upload.log, revision-log.md
    ├── manifests/                  ← nlm-notebooks.yml, FREEZE-2026-05-31.md, phase0-decisions.md
    ├── scripts/                    ← NEW scripts go here; existing scripts remain at .research/ root during FREEZE
    ├── cache/                      ← t0-retrievals/, downloads/, txt/, zotero_live_snapshot.sqlite
    └── *.py  *.yml  *.md           ← existing scripts/configs at root (frozen until 2026-05-31)
```

**Folder write rules:**
| Folder | Agent may write? | Notes |
|--------|-----------------|-------|
| `2ndbrain/` | ❌ **NEVER** | Read-only symlink to existing vault |
| `20Wiki/` | Suggest + diff only | Agent may write new canonical files when explicitly creating reference docs |
| `20Wiki/_templates/` | ✅ | Template files only; not thesis content |
| `20Wiki/[project-id].md` | ✅ on demand | Project hub pages; create when project becomes active |
| `30Drafts/` | ✅ | Always `status: ai-draft`; all projects; use `[project-id]_` prefix |
| `30Drafts/_staging/` | ✅ | `status: revision-staging`; AWAKE-COLLAB pre-briefs |
| `[project-id]/` | ✅ on demand | Project infrastructure dirs (CLAUDE.md, source-materials/, .research/); create when project starts |
| `.research/` root | ✅ scripts + ephemera | Do not delete existing scripts during FREEZE |
| `.research/logs/` | ✅ | Append only |
| `.research/manifests/` | ✅ read-mostly | Update when NLM notebook config changes |
| `.research/cache/` | ✅ | Raw data, T0 retrievals, large files |

---

## 2.5 NotebookLM Upload Policy
> Established 2026-05-02 as part of REV-5 architecture upgrade.
> NotebookLM (Google) is used as a verification + source-corpus layer.
> See plan: `~/.claude/plans/i-want-to-improve-compiled-pelican.md`

### 3-notebook architecture

| Notebook | Purpose | Allowed content | Forbidden content |
|----------|---------|-----------------|-------------------|
| **A-Sources** | Citation verification (third-party PDFs) | Items in Zotero `thesis-sources` collection (any metadata completeness) | Anything NOT in `thesis-sources` |
| **B-Self** | Self-consistency check (own published work) | User's own published abstracts, conference papers, OA chapters | Unpublished thesis chapters/drafts |
| **C-Audits** | AI audit feedback (revision priority) | AI-generated audit reports only (Gemini/Perplexity reviewing drafts) | Committee feedback, viva correspondence, reviewer identities |

### Privacy gate
**Opt-in by Zotero collection membership only.** No DOI/ISBN gating. An item in `thesis-sources` collection = explicit consent to NLM upload.

### Hard exclusion (NEVER uploaded to any notebook)
- `ThesisRevision/reviewers-comments/` — committee/viva feedback. **Local-only on disk.** Read by Claude when answering committee responses but never transmitted to Google.
- `ThesisRevision/audit-notes/` content that mentions committee names, reviewer identities, or correspondence
- Items in Zotero NOT in `thesis-sources` collection

### Sync mechanism
- Zotero is canonical source-of-truth.
- `zotero_to_nlm.py` (Phase 2+) syncs items tagged `nlm:pending` from `thesis-sources` collection → Notebook A.
- Tag transitions: user applies `nlm:pending` manually → script replaces with `nlm:synced` after upload.
- **`agent ingest` skill NEVER auto-applies `nlm:pending`** — that's a manual user decision per item.
- Hard refusal: `zotero_to_nlm.py` exits with error if target UUID matches `c_audits` from `.research/nlm-notebooks.yml`.

### Citation provenance format
Hybrid format extends existing `[VERIFY]` schema:
```
[VERIFY: confirmed | <citekey> | nlm-excerpt:"<short passage from cited_text>"]
```
With optional page number (manual Zotero PDF lookup, late-stage):
```
[VERIFY: confirmed | <citekey> | p.42 | nlm-excerpt:"..."]
```
Provenance metadata (NLM `source_id`, full `cited_text`) stored separately at `.research/nlm-provenance.ndjson`.

### Auth preflight
All NLM-using skills MUST run `notebooklm auth check` at session start. Windows sleep can expire OAuth cookies; expired auth → prompt user to run `notebooklm login`.

### Pipeline FREEZE
[LOOKUP] pipeline (`research-hub/src/research_hub/pipeline.py`, `doi_lookup.py`, `discover.py`, `C:\...\thesis_lookups\*.py`) frozen until **2026-05-31** (thesis submission). Not because broken — because pipeline is at 77.8% and any refactor mid-revision risks breaking it. See `.research/FREEZE-2026-05-31.md`.

---

## 3. YAML Frontmatter Schema

Every note created by Claude must begin with valid YAML frontmatter. Use only relevant fields.

```yaml
---
aliases: []
type: literature | concept | draft | project-hub | daily-digest | revision-manifest
project: ""     # REQUIRED. Format: theme-target-type (e.g., metaverse-scu-thesis, labor-oup-chapter).
                # Exception: existing thesis files use master-thesis (grandfathered until post-submission).
                # If the project is unclear, ASK before creating the file.
topic: []
status: ai-draft | revision-staging | human-review | canonical | published
target: thesis | academic-journal | grant-proposal | sns
citation-status: citable | in-preparation | under-review | personal-communication
source-notes: []     # citekeys or note filenames this draft draws from
summary: ""          # 1–2 sentence description (human-written preferred)
---
```

**`citation-status` rules (applies to files in `source-manuscripts/` and any note representing unpublished work):**
- `citable` — published; cite normally via Zotero citekey
- `in-preparation` — researcher's own unpublished manuscript; agent may read and use as generative scaffolding; **do not cite directly**; produce prose that develops the argument natively; flag with `[NOTE: developed from source-manuscript — check self-plagiarism before submission]`
- `under-review` — submitted elsewhere; same treatment as `in-preparation`
- `personal-communication` — conversations, notes, emails; may inform framing but never cite without explicit instruction

---

## 4. Status Rules — ENFORCE STRICTLY

| Status | Meaning | Agent may use as source? |
|--------|---------|--------------------------|
| `ai-draft` | Agent output. Not reliable. Never cite in future syntheses. | ❌ Never |
| `revision-staging` | Gemini/NLM audit material read at meta-level by researcher. | ⚠️ Yes, but tag every factual claim `[VERIFY: <basis>]` |
| `human-review` | Human has read and assessed. | ✅ With caution |
| `canonical` | Human-verified and accepted. | ✅ Freely |
| `published` | Finalized and released externally. | ✅ Freely |

**Allowed transitions (HUMAN ONLY — agent never promotes):**
- `ai-draft` → `human-review`
- `revision-staging` → `human-review`
- `human-review` → `canonical`
- `canonical` → `published`

**Forbidden:**
- Agent promoting any note past `ai-draft`
- Using `ai-draft` or `revision-staging` as source without `[VERIFY]` tagging
- Jumping `ai-draft` → `canonical` (must pass through `human-review`)

---

## 5. The Four Canonical Commands

### `agent ingest`
1. Sweep `00Inbox/` for new captures
2. Use vision/text extraction to identify candidate DOIs/ISBNs
3. Push to Zotero "Needs Review" collection (tag: `needs-review`) — **do NOT auto-file into main library**
4. Write summary note to `00Inbox/ingest-YYYY-MM-DD.md` (status: `ai-draft`) with candidate matches for human review
5. Append one line to `.research/automation-log.md`: timestamp + action + outcome

### `agent compile [citekey or note name]`
1. Read the specified Zotero item or `10Literature/` note
2. Extract: research question, methods, key findings, relevance to active projects
3. Write structured note to `10Literature/` (status: `ai-draft`, YAML schema above)
   - Include `[[wikilinks]]` in body to related notes in `20Wiki/` and `30Drafts/` where argument connects
   - Include `[[project-id]]` backlink to the project hub page (populates hub's backlinks panel)
   - Mirror all linked sources in `source-notes:` frontmatter as citekeys
4. Append "Candidate Links" section (suggestions only — **do not modify any existing notes**)

### `agent digest [today | week]`
1. Parse workspace for notes updated in the specified period
2. Summarize new literature by project; list candidate concept-concept links for human review
3. Write output to `00Inbox/digest-YYYY-MM-DD.md` (status: `ai-draft`)
4. Append one line to `.research/automation-log.md`: timestamp + action + status

### `agent draft --type [thesis | academic | grant] --topic [topic or note list]`
1. Read style guide from `20Wiki/Style-[type].md` if it exists
2. Read **only** `canonical` or `human-review` notes as source material
3. If using `revision-staging` material, tag every factual claim: `[VERIFY: <citekey or basis>]`
4. Write output to `30Drafts/` (status: `ai-draft`) with `source-notes` frontmatter linking to all sources used
   - Filename: `[project-id]_[section-or-task-id]_[description].md` (existing thesis files grandfathered)
   - Include `[[wikilinks]]` in body to source literature notes and relevant canonical wiki pages
   - Include `[[project-id]]` backlink to the project hub page
   - Mirror all linked sources in `source-notes:` frontmatter

---

## 6. Available Skills

### `academic-writing-skills` (`./academic-writing-skills/`)
Use for: drafting thesis sections, reviewer-response tables (comment → anchor → response → change → evidence), claim-evidence auditing, prose conversion from snippets, register checking, submission compliance.

Key triggers: "revise [chapter]", "reviewer response table", "audit claims in [section]", "convert snippet to prose", "check register"

### `zotero-skills` (`./zotero-skills/`)
Zotero connection:
- Local API: `http://localhost:23119`
- Required header: `X-Zotero-Connector-Api-Version: 2`
- User ID: `4381873`

Use for: looking up exact passages, resolving placeholder citations to citekeys, metadata checks, deduplication audits.

**During thesis revision: use read-only operations only, unless explicitly asked to write.**

PowerShell query template:
```powershell
Invoke-WebRequest -Uri "http://localhost:23119/api/users/4381873/items?q=<SEARCH_TERM>" `
  -Headers @{ "X-Zotero-Connector-Api-Version" = "2" } `
  -UseBasicParsing | Select-Object -ExpandProperty Content
```

---

## 7. Thesis Revision Special Rules
> **Active until: 2026-05-04** — delete this section once revision is submitted.

### File roles
| File/Folder | Status | Role |
|-------------|--------|------|
| `ThesisRevision/viva-passed-draft/` | `canonical` | Ground truth. **READ ONLY — never modify.** |
| `ThesisRevision/revision-draft/` | `human-review` | Current working state of revision. |
| `ThesisRevision/reviewers-comments/` | `canonical` | Authoritative change instructions. |
| `ThesisRevision/snippets/` | `human-review` | Researcher's raw material. May use as source. |
| `ThesisRevision/audit-notes/` | `revision-staging` | Gemini/NLM pre-analysis. Requires `[VERIFY]` tagging. |
| `ThesisRevision/source-manuscripts/` | `human-review` + see `citation-status` | Researcher's own unpublished/in-preparation works. Read for generative scaffolding only; never cite directly without instruction. Flag derived prose with `[NOTE: developed from source-manuscript]`. |
| `ThesisRevision/00-manifest.md` | `canonical` | Auto-generated revision map. |

### Thesis context
**Title:** Between the Universe and the Metaverse

**Core argument (squeeze hypothesis):** Human existence is progressively squeezed between the universe (realist, the given natural substrate) and the metaverse (a new layer of neo-artificiality), with the world (idealist, human-constructed meaning-space nested within the universe) being displaced or transformed.

**Key concepts to preserve precisely:** universe / world / metaverse distinction; squeeze hypothesis; artificiality vs. neo-artificiality; technosphere; disposition to domination; "fully actualized"; world-completeness.

**Ontological distinctions (from viva):**
- Universe = realist; independent of human mind
- World = idealist; nested inside the universe; human-made meaning-space
- World is smaller in portion than universe, not in functionality

**Committee members and their primary concerns (viva 2025-01-02):**
| Member | Primary focus |
|--------|--------------|
| 馬 (Ma) | Conceptual clarity, evidence grounding, comparative breadth across cultures/traditions |
| 米 (Mi) | Argument structure, logical derivation (inductive/deductive), philosophical precision of terms |
| 劉 (Liu) | Scope discipline — what is argued vs. merely mentioned; section architecture |

### Placeholder types in revision DOCX
When reading the revision DOCX, classify every incomplete section as one of:
- `[GENERATIVE]` — vague direction needing expansion from theory + sources
- `[LOOKUP]` — specific citation needed; must find exact passage + citekey in Zotero before inserting
- `[PROSE]` — near-complete argument; convert to grammatical academic English preserving author's voice
- `[VERIFY]` — any claim sourced from `revision-staging` material; Zotero-verify before final

### Output rules
1. All revised sections go to `30Drafts/` with `status: ai-draft`
2. Researcher reviews and promotes to revision-draft manually
3. Every `[LOOKUP]` placeholder must be resolved against Zotero before prose is generated — do not generate plausible-sounding citations
4. When in doubt about whether to expand or cut an argument, default to: **expand with evidence, not cut**

---

## 8. Memory-First Session Protocol (MANDATORY)
> Added 2026-05-03. Purpose: prevent repeated self-troubleshooting of known issues across sessions.
> Updated 2026-05-04: Transcript preservation is now hook-automated. §8.1 added.

### §8.1 Conversation History Preservation (Automated + Auditable)
> Added 2026-05-04. Replaces behavioral "remember to save history" instructions.

**How it works (no Claude involvement required):**
- `PreCompact` and `SessionEnd` hooks fire automatically via `~/.claude/settings.json`
- Hook script: `C:\Users\adler-standard\.claude\hooks\preserve-transcript.py`
- Output per project is configured in `<project>/.claude/transcript-config.json`
- If no config exists, defaults to `<cwd>/conversation-history-raw.md`
- Archives kept at: `<archive_dir>/<event>_<timestamp>.jsonl` + `.md` (never overwritten)
- claude-mem runs on **Gemini free tier** (`gemini-2.5-flash-lite`) — zero Claude tokens consumed

**Per-project output path setup (MANDATORY for new projects):**
When starting work in a project directory that has NO `.claude/transcript-config.json`:
1. **Ask the user:** "Where should I save `conversation-history-raw.md` for this project? Default: `<cwd>/conversation-history-raw.md`"
2. **Create `.claude/transcript-config.json`** with:
   ```json
   {
     "output_path": "<user-specified or default path>",
     "archive_dir": "<same parent dir>/.conversation-archives"
   }
   ```
3. Confirm the path was set before proceeding with any other work.

**This project's config:** `ThesisRevision/conversation-history-raw.md` (set in `.claude/transcript-config.json`)

**Memory layer architecture (3 layers — do not conflate):**

| Layer | Tool | Purpose | Auditable? |
|-------|------|---------|-----------|
| 1 — Raw archive | Hook → `preserve-transcript.py` | Verbatim transcript, lossless | ✅ Plain markdown/JSONL |
| 2 — Semantic retrieval | claude-mem (Gemini free) | Cross-session "did we solve this?" | ❌ Requires tool to query |
| 3 — Curated guidance | CLAUDE.md + MEMORY.md | Rules, gotchas, project facts | ✅ Human-editable markdown |

Layer 1 is the **source of truth**. If Layer 2 conflicts with Layer 1, Layer 1 wins.

---

**At the start of EVERY session involving this workspace, before doing any other work:**

1. **Check `.claude/transcript-config.json` exists** — if not, ask user for output path (see §8.1 above)
1.5. **Identify active project** — infer from task context or ask. If a project directory exists (e.g., `ThesisRevision/`, `[project-id]/`), read its `CLAUDE.md` for project-specific rules. All files created this session must carry the correct `project:` frontmatter (see §2.7). If project is unclear, ask before creating any file.
2. **Read `memory/MEMORY.md`** (auto-loaded in context — scan the index for relevant entries)
3. **Run `claude-mem search`** for at least 2 targeted queries:
   - Query 1: topic of the current task (e.g., "Zotero API add items", "NLM upload")
   - Query 2: any tools/scripts you're about to use (e.g., "pyzotero create_items", "libgen")
   - **For exact prior-content recall (decisions, quotes, error messages):** run `py .research/verbatim-search.py '<query>'` BEFORE or INSTEAD OF `claude-mem search`. Verbatim grep is authoritative; semantic search is a finding aid. (Per plan `vectorized-watching-cook.md`. Full §8.1 layer-role rewrite is deferred to a follow-up plan.)
4. **Fetch details** with `get_observations([IDs])` for any observations marked 🔴 (bug) or ⚖️ (decision) that are relevant
5. **Only then** begin the task

**Why this is mandatory:** Known bugs (pyzotero string-key response, ISBN field on journalArticle, localhost vs Web API for writes) were re-discovered from scratch in a later session because memory was not consulted first. This cost ~45 minutes. The fix was a one-line change documented in memory from a prior session.

**Known gotchas (do NOT re-discover — check memory instead):**
- `pyzotero create_items()` response: use `list(resp['successful'].values())[0]['key']` — string keys `"0"`, `"1"`, NOT integers
- `journalArticle` template: no `ISBN` field — only `DOI`; books use `ISBN`
- Zotero writes: ONLY via Web API (`api.zotero.org`) — local API (`localhost:23119`) is read-only and returns 400/501 for writes
- API key: `.zotero-api-key` at project root (NOT `zotero_api_key.txt`)
- LibGen: `libgen.is`/`.rs`/`.st` **TIME OUT** — use **`libgen.li`** (primary; `download_pdfs_libgen_li.py`) or **`libgen.la`** (DOI→edition.php→ads.php→key→get.php). Check **https://librarygenesis.net/** for which instances are live and pick a working one. Shadow order: libgen.li/.la → shadowlibraries.github.io (mirror directory) → Anna's Archive (**last resort** — slow; fetch resumably in the background, never foreground-short-timeout). Full retrieval cascade — **NLM notebook → Zotero → `P:\books` → opportunistic OA → shadow** — in memory `feedback_retrieval_cascade` + `shadow_library_protocol`. (Corrected 2026-06-04.)
- NLM auth: run `notebooklm auth check` using `.venv-nlm` environment before any NLM operation
- Deadline: **2026-05-31** (hard) — this is a WORKFLOW SETUP project using thesis as real case

**Script inventory (check before writing new ones):**
| Script | Location | Purpose |
|--------|----------|---------|
| `lookup_full_pipeline.py` | `.research/` | Full 25-source LOOKUP: Google Books + CrossRef → Zotero + thesis-sources + nlm:pending |
| `lookup_google_books.py` | `.research/` | Google Books + CrossRef metadata fetch only |
| `lookup_pipeline_free_models.py` | `.research/` | **LOOKUP with 5-tier fallback**: T0 Google Books/CrossRef → T1 Gemini Flash-Lite → T2 Gemini Flash → T3 NVIDIA NIM → T4 OpenRouter → T5 Claude Haiku CLI |
| `switch_claude_mem_provider.py` | `.research/` | claude-mem provider failover: validates current provider, auto-switches to next tier (T1→T2→T4→T5), restarts worker |
| `check_libgen.py` | `.research/` | LibGen availability check (tests libgen.is — but note libgen.is TIMES OUT; use libgen.li instead) |
| `fix_3_journals.py` | `.research/` | One-off fix for journalArticle ISBN field error |
| `download_pdfs_libgen_li.py` | `.research/` | **PRIMARY PDF downloader** — libgen.li mirror (confirmed working 2026-05-04, pure Python) |
| `attach_pdfs_thesis_sources.py` | `.research/` | Attach thesis-source PDFs from ~/Downloads/thesis-pdfs/ to Zotero (uses pyzotero attachment_simple) |
| `export_nlm_cookies.py` | `.research/` | Export NLM browser cookies headlessly from persistent profile (use if auth expires) |
| `tag_nlm_pending.py` | project root | Tags Zotero items in thesis-sources with `nlm:pending` |
| `zotero_to_nlm.py` | `research-hub/scripts/` | Syncs `nlm:pending` items from Zotero → NLM Notebook A-Sources |
| `attach_pdfs_to_zotero_fixed.py` | project root | **DEPRECATED** — has known bugs (obs 72); use attach_pdfs_thesis_sources.py instead |
| `verbatim-search.py` | `.research/` | **Verbatim grep over Layer 1 conversation archives.** Returns file+line passages with pagination; never summarizes. Authoritative recall surface for prior-conversation content (per plan `vectorized-watching-cook.md`, Phase 4). |

**claude-mem provider tier order** (T3/NVIDIA not a supported claude-mem provider):
| Tier | Provider setting | Model | When to use |
|------|-----------------|-------|-------------|
| T1 | `gemini` / `gemini-2.5-flash-lite` | ← current | Default; 1K RPD free |
| T2 | `gemini` / `gemini-2.5-flash` | sub-tier within gemini | If Flash-Lite rate-limited |
| T4 | `openrouter` / `xiaomi/mimo-v2-flash:free` | OpenRouter key pre-loaded | If both Gemini tiers fail |
| T5 | `claude` / CLI auth | Max subscription | Last resort; no API key needed |
Switch: `py .research/switch_claude_mem_provider.py` (auto) or `--to T4` / `--to T5` (manual)

---

## 9. Hard Limits — Never Do Without Explicit Permission

- Modify any file with status `canonical` or `published`
- Delete any file
- Add backlinks or in-line edits to existing `20Wiki/` notes (suggest only; show diff first)
- Submit anything to Zotero main library without human review of metadata
- Infer citations not verified in Zotero or provided source material
- Modify the viva-passed PDF
- Modify `ThesisRevision/reviewers-comments/` files

---

## 2.6 Obsidian Vault Configuration
> Added 2026-05-06.

**Vault root:** `P:\_AI agents\full-research-workflow\`
**Local 2ndbrain mirror:** `C:\Users\adler-standard\Documents\Obsidian\2ndbrain`
**Symlink:** `C:\...\2ndbrain\full-research-workflow` → `P:\_AI agents\full-research-workflow` (created 2026-05-06)

### How it works
Open `C:\Users\adler-standard\Documents\Obsidian\2ndbrain` in Obsidian (as you normally do). The `full-research-workflow/` folder appears as a subfolder of the vault via the symlink. All `00Inbox/`, `10Literature/`, `20Wiki/`, `30Drafts/` files are accessible and Canvas-connectable from within the same vault view. The P: path remains authoritative for Claude Code — no scripts break.

### Obsidian exclusions (configured in `.obsidian/app.json`)
These paths are excluded from Obsidian's full-text index (too noisy or not markdown):
- `.research/cache/` — raw data, PDFs, Zotero snapshot, large text extracts
- `.research/scripts/` — Python files
- `.venv-nlm/` — Python virtualenv
- `research-hub/` — Python package source
- `ThesisRevision/viva-passed-draft/` — canonical ground truth (no indexing needed)
- `ThesisRevision/revision-draft/` — DOCX files (Obsidian cannot render them)
- `2ndbrain/.obsidian` — prevents double-indexing vault config

`.research/logs/` and `.research/manifests/` remain indexed — useful for audit links in Canvas.

### Plugins (minimal set)
- **Dataview** — install from Community Plugins; powers `20Wiki/draft-status-board.md`
- **Zotero Integration** (mgmeyers) — for pulling annotations from `thesis-sources` collection into `10Literature/`
- **Canvas** — built-in (v1.1+); `.canvas` files live in `20Wiki/canvas/`
- **Properties** — built-in (v1.4+); reads existing YAML frontmatter

### Zotero annotations sync (Obsidian-native, no scripting)
1. Install **Zotero Integration** plugin in Obsidian
2. Set output folder → `10Literature/`
3. Configure note template to match existing YAML frontmatter schema (`type: literature`, `status: ai-draft`, `source-notes: [citekey]`)
4. Scope to `thesis-sources` Zotero collection only (collection filter in plugin settings)
5. Import on-demand: `Ctrl+P → "Zotero Integration: Import notes"`

This is the passive sync path (token-free). `agent compile [citekey]` remains the agentic path for synthesised literature notes with relevance analysis.

### 2ndbrain write prohibition
**The agent NEVER writes to `2ndbrain/` under any circumstance.** This applies to:
- Direct file creation or editing
- Moving files from `full-research-workflow/` into `2ndbrain/`
- Any script that outputs to a path containing `2ndbrain/`

To reverse the symlink: `rmdir "C:\Users\adler-standard\Documents\Obsidian\2ndbrain\full-research-workflow"` (removes symlink only; never touches the original P: folder).

### Mobile collaboration (pCloud-based, three-channel)
> Added 2026-05-08 for the 3-day on-the-go period (2026-05-08 → 2026-05-11). May persist as the standard mobile workflow if it proves robust.

The author can drive Claude Code from an iPhone 14 Pro via three coordinated channels. **`P:\` IS pCloud Drive**, so file-level sync is automatic.

**Three channels:**

| Channel | When | Mechanism | Files involved |
|---|---|---|---|
| **LIVE** (primary) | Default; PC online + remote-control wrapper running | Claude mobile app → Code tab → `thesis-revision-mobile` session over HTTPS | None — direct chat with this Claude Code session |
| **TROUBLESHOOT** (out-of-band diagnostic) | Author writes when LIVE seems broken | Watcher script polls `MOBILE-TROUBLESHOOT.md` every 30s; on change spawns `claude -p` headless on PC | `MOBILE-TROUBLESHOOT.md` (input) / `MOBILE-TROUBLESHOOT-RESPONSE.md` (output, newest at top) |
| **FALLBACK** (file-only) | Author creates `MOBILE-FALLBACK.txt` to switch deliberately, or LIVE+TROUBLESHOOT both unreachable | pCloud sync only; author uses MOBILE-prompts.md + MOBILE-dictation.md | `MOBILE-FALLBACK.txt` (signal) / `20Wiki/MOBILE-prompts.md` / `20Wiki/MOBILE-dictation.md` / `20Wiki/MOBILE-board.md` |

**Required PC processes during the trip** (each in its own dedicated PowerShell terminal, started before departure):
1. `.research/scripts/remote-control-wrapper.ps1` — runs `claude remote-control --name "thesis-revision-mobile"` in a restart-on-exit loop. Logs to `.research/logs/remote-control.log`
2. `.research/scripts/troubleshoot-watcher.ps1` — polls `MOBILE-TROUBLESHOOT.md` modtime; on change runs headless `claude -p` to diagnose + respond + archive. Logs to `.research/logs/troubleshoot-watcher.log`

**State-in-files principle (load-bearing):** because LIVE-mode reconnects after a network drop are *new* sessions (no chat-history continuity), all project state lives in markdown files (`.research/b2-autopilot-progress.md`, `20Wiki/MOBILE-board.md`, `20Wiki/MOBILE-prompts.md`, `20Wiki/MOBILE-dictation.md`). The chat is a real-time overlay; the files are the durable substrate. On every LIVE reconnect, Claude reads these files to recover state before continuing.

**Mode-switching protocol:**
- LIVE → FALLBACK is author-initiated (create `MOBILE-FALLBACK.txt` at project root with a one-line note: timestamp + reason)
- FALLBACK → LIVE is also author-initiated (open Claude mobile app, try the session)
- The flag stays until I sweep MOBILE-prompts.md + MOBILE-dictation.md, integrate dictated material, then delete the flag

**Integration sweep procedure** (when LIVE reconnects after fallback / when I'm next awake):
1. Check for `MOBILE-FALLBACK.txt` — if present, read it for context, do steps 2–5, then delete
2. Sweep `MOBILE-prompts.md` for new answers beneath each `> [answer below]` marker; integrate each Qn answer into the corresponding Phase B/C/D action
3. Sweep `MOBILE-dictation.md` for new timestamped entries; route each entry to the relevant scaffold/lock/inbox per the file's "where things go" header
4. Sweep `MOBILE-TROUBLESHOOT-archive-*.md` files (if any) — these are read-only logs of in-trip troubleshoots; review for any unresolved issues
5. Refresh `MOBILE-board.md` to reflect post-trip state; append fresh prompts to `MOBILE-prompts.md` if the next phase needs more author input
6. Append a Change Log entry to `.research/b2-autopilot-progress.md` summarizing what landed

**Hard exclusions** (apply equally in mobile mode):
- Never write to `2ndbrain/` (per above)
- Never push reviewers-comments / committee feedback / NLM-excluded content via any mobile channel
- Never auto-promote drafts past `ai-draft` (status transitions remain human-only, as in §4)

---

## 2.7 Multi-Project Routing Schema
> Added 2026-05-26. Enables simultaneous execution of multiple submissions without file or memory conflation.

### Projects are submission-scoped
Each project = one specific work to be submitted. **Projects are created on demand, not pre-emptively.** Project IDs follow the format `theme-target-type` (e.g., `metaverse-scu-thesis`, `labor-oup-chapter`). See §1 for the active project registry.

### Three-pillar isolation

**Pillar 1 — YAML `project:` frontmatter (REQUIRED)**
`project:` is MANDATORY in every file the agent creates. If project context is unclear, **ASK before creating any file**. See §3 for the full schema. Existing thesis files use `project: master-thesis` (grandfathered; bulk-update to `metaverse-scu-thesis` post-submission).

**Pillar 2 — File naming prefix**
Format: `[project-id]_[section-or-task-id]_[description].md`

| Project | Example filename |
|---------|-----------------|
| Current thesis (grandfathered) | `IV-1_causal-efficacy-argument.md` ← no prefix, existing convention |
| New submission | `metaverse-jvp-article_s2_virtuality-definition.md` |
| Book chapter | `labor-oup-chapter_ch3_allocation-theory.md` |

Files in `10Literature/` use citekey names (globally unique) — no prefix needed there.

**Pillar 3 — `[[wikilinks]]` in body (REQUIRED)**
Every agent-created note MUST include `[[wikilinks]]` to related notes:
- **Project hub** → `[[project-id]]` ALWAYS (e.g., `[[metaverse-scu-thesis]]`) — populates the hub's backlinks panel and keeps it the central graph node
- Source literature → `[[citekey]]`
- Canonical wiki pages → `[[squeeze-ontology]]`, `[[method-frame]]`
- Related drafts → `[[IV-1_causal-efficacy-argument]]`

Mirror all linked sources in `source-notes:` frontmatter. `[[wikilinks]]` create Obsidian graph edges organically — no manual linking step needed.

### Output routing
All outputs land in shared folders, differentiated by frontmatter and prefix:

| Output type | Destination | Differentiation |
|-------------|-------------|-----------------|
| Drafts | `30Drafts/` | `[project-id]_` prefix + `project:` frontmatter |
| Literature notes | `10Literature/` | citekey name + `project:` frontmatter |
| Wiki / canonical pages | `20Wiki/` | `project:` frontmatter |
| Project hub page | `20Wiki/[project-id].md` | one per active submission |
| Project infrastructure | `[project-id]/` at workspace root | on demand (see below) |

### Project hub page
Every active project has a hub page at `20Wiki/[project-id].md` (`type: project-hub`). It is:
- The **most-linked node** for its project — all project files link back via `[[project-id]]`
- The **bird's-eye view**: status callout, goal, progress tracker, key file links, core literature, active drafts (Dataview)
- Created **first** when a project goes active, using the template at `20Wiki/_templates/project-hub-template.md`

### On-demand project directory
When a project transitions to active, create at workspace root:
```
[project-id]/                    ← e.g., virtuality-jvp-article/
├── CLAUDE.md                    ← project-specific rules (deadline, file roles, NLM policy)
├── source-materials/            ← primary sources / review documents for this submission
├── snippets/                    ← researcher's raw notes
└── .research/                   ← project-specific scripts (isolated from shared .research/)
```
**Do NOT create speculatively.** `ThesisRevision/` IS the thesis project directory — no separate dir needed for it.

### Conversation history on project switch
When starting a new project, update `.claude/transcript-config.json`:
- `output_path` → `[project-id]/conversation-history-raw.md`
- `archive_dir` → `[project-id]/.conversation-archives`
Document this in the project's `CLAUDE.md`.

### Memory file prefix convention
| Prefix | Scope |
|--------|-------|
| `thesis_*` | master-thesis / metaverse-scu-thesis (already in use) |
| `[project-id]_*` | future submissions (derive prefix from project ID) |
| no prefix | workspace-wide (zotero workflow, user voice, shadow library, etc.) |

---

## 9. Long-Term Workflow

| Component | Status | Activation |
|-----------|--------|-----------|
| Obsidian vault integration | ✅ **ACTIVE** (2026-05-06) | Symlink live; open `C:\...\2ndbrain` in Obsidian |
| Dataview draft-status board | ✅ **ACTIVE** | `20Wiki/draft-status-board.md` — install Dataview plugin |
| Zotero Integration plugin | 🔧 **Setup needed** | Install in Obsidian; configure template + collection scope |
| iOS sync (Obsidian Git + Working Copy) | 🔜 After thesis submission | Sync local 2ndbrain mirror to iOS |
| `20Wiki/Style-academic.md` | Deferred | Before first journal submission |
| `20Wiki/Style-thesis.md` | Deferred | After revision is submitted |
| `20Wiki/Style-grant.md` | Deferred | Before next grant deadline |
| `20Wiki/Style-sns.md` | Deferred | When social media / public writing begins |
| `agent draft --type sns` | Deferred | After Style-sns.md is written |
| Mac/Hermes agent | Deferred | After thesis revision |
| DAS cold storage | Deferred | After hardware arrives |
| `codex-delegate`, `gemini-delegate` | Deferred | When code-heavy or CJK-heavy tasks begin |
