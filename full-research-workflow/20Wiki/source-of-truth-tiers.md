---
type: concept
project: master-thesis
status: canonical
target: thesis
source-notes: []
summary: "Author-defined source-of-truth tier hierarchy. Specifies which materials count as authoritative for which kinds of claims during thesis revision and AI-assisted research work. Established by author 2026-05-09 to prevent AI from over-trusting Tier 3 (ai-draft) co-created scaffolds as if they represented the author's view."
---

# Source-of-Truth Tiers

> Author-decided rules. Established 2026-05-09 to formalize the tier hierarchy that has been operating implicitly. Locks supersede any prior implicit rule.

## Why this exists

Without a formal hierarchy, AI assistants tend to over-trust co-created drafts (`30Drafts/`) as if their AI prose represented the author's view, when in fact those drafts are AI scaffolding with embedded author annotations. Conflating tiers produces three recurrent errors:

1. Citing AI prose as if it were the author's position.
2. Missing or misrepresenting author annotations embedded *within* `ai-draft` documents (the `[!REVISION]`, `[!VERIFY]`, `<!-- ANNOT: -->` markers).
3. Building synthesis from secondary AI scaffolds rather than primary text in the author's own voice.

This document specifies the hierarchy that prevents these errors.

---

## The four tiers

### Tier 0 — Cited sources

- **Highest level of truth** for any claim ABOUT THE CONTENT OF THESE SOURCES.
- **Locations:**
  - Zotero `thesis-sources` collection
  - NotebookLM A-Sources notebook (UUID `c68ca15e-5a07-4598-a5e0-dd68b9fa73b9`)
  - Author-specific deep-dive notebooks (Uegaki `12addf63-…`, Obara `86e6c0e5-…`, Stiegler, Bhaskar, Hui, etc. — see `nlm-notebooks.yml`)
  - Published primary texts in `P:\books(1)\` and `.research/cache/txt/`
- **Examples:** Uegaki 2017, Obara 1995/2000, Bhaskar 1975, Stiegler 1998, Hui 2016, Lessig 2006.
- **Citation requirement:** every factual claim about a Tier 0 source must be backed by a verbatim retrieval (NLM excerpt or Zotero PDF passage), not by AI paraphrase.

### Tier 1 — Author's own thinking

The top level of truth for any claim about WHAT THE AUTHOR THINKS.

#### Tier 1a — Hearing-passed and viva-passed drafts
- **Location:** `ThesisRevision/hearing&viva-passed-drafts/`
- **Files:**
  - `20240710 The Metaverse Hypothesis (Proposal).pdf` — proposal/hearing-passed (2024-07)
  - `Between the Universe and the Metaverse - 202501passeddraft.pdf` — viva-passed (2025-01)
- **Status:** canonical for what the committee has formally accepted. Foundation that revision must preserve + strengthen, not contradict.
- **Read-only intent:** never modify these files; use them as anchor.

#### Tier 1b — Revision drafts
- **Location:** `ThesisRevision/revision-draft/*.docx`
- **Status:** `human-review`. In-progress strengthening of Tier 1a; reflects current author thinking under active revision.
- Where 1a and 1b conflict: 1b reflects current direction, but 1a's structural foundations cannot be silently abandoned without explicit author decision.

#### Tier 1c — Source manuscripts
- **Location:** `ThesisRevision/source-manuscripts/`
- **Status:** `human-review` + `citation-status: in-preparation` (per CLAUDE.md §3).
- Author's contemporaneous unpublished works (e.g., the dependency-modes paper `20260313交換様式の地平を掘り下げる_アドラー・ヨウ.docx`).
- Often the **most developed conceptual articulation** of an idea — more developed than the thesis text itself, because the manuscript is a parallel paper that develops a particular concept in depth.
- **Use rules** (CLAUDE.md §3):
  - Read for generative scaffolding only.
  - Do NOT cite directly as `(Yang 2026b)` or similar.
  - Flag any derived prose with `[NOTE: developed from source-manuscript — check self-plagiarism before submission]`.

#### Tier 1d — Author annotations embedded in Tier 3 files
- **Markers:** `[!REVISION]`, `[!VERIFY]`, `[!NOTE]`, `[!CRITICAL]` callouts; `<!-- ANNOT: -->` HTML comments.
- Embedded fragments of the author's voice within AI scaffolds.
- **Treated as Tier 1** even when surrounded by Tier 3 prose. The annotation is the author's voice; the prose around it is not.
- When AI reads a 30Drafts file, it should explicitly distinguish "AI scaffold says X" (Tier 3) from "author annotation says X" (Tier 1d).

### Tier 2 — 20Wiki

- **Location:** `20Wiki/*.md`
- Canonical reference docs representing 80–90% AI/author consensus.
- High-confidence reference for both AI and author.
- **Examples:** `squeeze-ontology.md` (F1–F5 lock), `method-frame.md`, `top100-rubric-notes.md`, `Style-*.md`, this document.
- **Status:** `human-review` or `canonical` (per per-file status frontmatter).
- **Operating rule:** Tier 2 locks carry through with high confidence; Tier 2 is where conceptual consensus crystallizes.

### Tier 3 — 30Drafts

- **Location:** `30Drafts/*.md`
- AI-generated prose; status `ai-draft`.
- Co-creation between AI and author; AI prose is a scaffold, not a statement of the author's view.
- Only Tier 1d fragments (author annotations) inside these files represent the author's voice.
- Per CLAUDE.md §4: ai-draft is `❌ Never` valid as source for future syntheses.

---

## Operating rules

### Rule 1 — When making a claim about the author's thinking:
- ✅ Cite Tier 1a / 1b / 1c first.
- ✅ When using Tier 3 file content, explicitly distinguish:
  - *"AI scaffold says X"* (Tier 3 prose — provisional, not citable)
  - *"Author annotation says X"* (Tier 1d — authoritative)
- ❌ Never cite Tier 3 prose as the author's view.

### Rule 2 — When making a claim about a Tier 0 source:
- ✅ Cite via verbatim retrieval (NLM excerpt or Zotero PDF passage).
- ❌ Never cite a Tier 3 paraphrase as a substitute for a Tier 0 source.

### Rule 3 — When inheriting prior reasoning across sessions:
- ✅ Tier 2 (20Wiki locks) carry through with high confidence.
- ⚠️ Tier 3 prose carries through only with explicit author confirmation in the current session.

### Rule 4 — When tiers disagree:
- 1a > 1b > 1c — when they conflict on what the author currently thinks (the revision is the live document; the viva-passed is the committee-accepted foundation).
- 1d (annotations) > Tier 3 surrounding prose, every time.
- Tier 0 > all other tiers — when the claim is about a cited source's actual content.

### Rule 5 — Mandatory pre-flight before V-X / VI-X analysis:
1. Read Tier 1a (viva-passed draft) for what was accepted on this section.
2. Read Tier 1b (current revision DOCX) for current state.
3. Read Tier 1c (source manuscripts) for any developed parallel articulation.
4. Read Tier 1d (annotations in any Tier 3 file on this section).
5. ONLY THEN consult Tier 3 AI prose — and only as scaffold-context, never as source.

Failing to follow Rule 5 produces the "AI building synthesis on AI scaffolds" failure mode. Common symptom: the AI claims to be summarizing the author's view but is actually summarizing prior AI prose.

---

## Worked examples

### Example A — Wrong (do not do this)

> "In your IV-4_v2 draft, you argued that Period 2 collectivism is a cross-actualization of fascism…"

This treats Tier 3 AI prose as the author's view. The cross-actualization claim is in IV-4_v2's AI prose, not in any Tier 1 source. The author may or may not endorse it.

### Example B — Right

> "The IV-4_v2 AI scaffold proposes a cross-actualization framing for Period 2 collectivism (Tier 3 prose, not yet author-confirmed). The Tier 1d annotation `[NOTE: extension by Yang via CR-stratified cross-actualization framing; not Uegaki's own claim — see ANNOT-L8]` indicates this is the AI's extension, not Uegaki's claim. Author endorsement of this extension has not been verified against Tier 1a/1b."

This distinguishes the layers cleanly.

---

## Special note on the viva-passed draft

The viva-passed PDF (`Between the Universe and the Metaverse - 202501passeddraft.pdf`) is the **single most authoritative document** for what the thesis is about. The current revision is the answer to viva comments + own ongoing development; it does not replace the viva-passed draft as authority.

Any claim like "your thesis argues X" must be cross-checked against the viva-passed PDF before being asserted, *not* against `30Drafts/V-X` or `30Drafts/VI-X` AI scaffolds.

---

## Maintenance

This document is itself Tier 2 (canonical). Update when:
- New tier categories are introduced (e.g., a new manuscript family).
- File locations change.
- Author refines the rules.

Last updated: 2026-05-09 (initial canonical version).
