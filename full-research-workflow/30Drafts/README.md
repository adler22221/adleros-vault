---
type: project-hub
project: master-thesis
status: canonical
---

# 30Drafts — AI Output Staging Area

All AI-generated draft content for the thesis revision lands here before human review.

## Naming convention

This folder serves **all active submissions**. Files are disambiguated by project prefix and YAML frontmatter.

**Format (new files):** `[project-id]_[task-id]_[description].md`

| Project | Prefix | Example |
|---------|--------|---------|
| master-thesis (grandfathered) | *(none)* | `IV-1_causal-efficacy-argument.md` |
| New submission | full project ID | `metaverse-jvp-article_s2_virtuality-definition.md` |

**Existing thesis files** (90+ without prefix) are grandfathered — do not rename during the thesis freeze. The `project: master-thesis` frontmatter field identifies them.

Task IDs for the thesis cross-reference `ThesisRevision/00-manifest.md`.

## Wikilinks (required in all drafts)

Every agent-created draft MUST include `[[wikilinks]]` in body text:
- `[[project-id]]` — link back to the project hub page (e.g., `[[metaverse-scu-thesis]]`); makes this draft appear in the hub's backlinks panel
- `[[citekey]]` — link to source literature notes in `10Literature/`
- `[[canonical-page]]` — link to relevant `20Wiki/` pages (e.g., `[[squeeze-ontology]]`, `[[method-frame]]`)
- `[[related-draft]]` — link to related drafts in the same argument chain

These links are how the Obsidian graph organically maps the project. They require no manual upkeep — they are produced at draft-creation time.

---

## Traceability markers

Every AI draft opens with a blockquote header:

```
> [AI draft | task: IV-1 | date: 2026-04-29 | sources: viva-comments, docx-comment-2025-12-31]
```

**When you accept a passage:**
1. Delete the marker line
2. Copy prose into the revision DOCX with Track Changes ON
3. Update `.research/revision-log.md`: change status from `generated` → `accepted` (or `modified`)

**When you modify a passage:**
- Edit the draft file directly, then copy — keep the marker but note "modified by human" in the log

**When you reject a passage:**
- Update log status to `rejected` with a brief reason — do not delete the file

## Status rules

| Status | Meaning |
|--------|---------|
| `generated` | AI output, not yet reviewed |
| `accepted` | Inserted into DOCX as-is |
| `modified` | Inserted after human editing |
| `rejected` | Not used; reason logged |
| `pending-lookup` | Awaiting Zotero verification before draft can be finalized |

## Self-plagiarism flags

Any passage developed from `ThesisRevision/source-manuscripts/` carries this inline tag:

```
[NOTE: developed from source-manuscript — check self-plagiarism before submission]
```

Do not remove this tag until you have reviewed the passage against the kaikan manuscript.
