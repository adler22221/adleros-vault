---
aliases: [Draft Status Board, Revision Status]
type: project-hub
project: master-thesis
status: canonical
summary: "Live Dataview board tracking all 30Drafts/ scaffolds and Phase A-E revision blocks by status. Obsidian-native replacement for revision-board.html."
---

# Draft Status Board
*Between the Universe and the Metaverse — Thesis Revision*

> **Hard deadline:** 2026-05-31 · **Original target:** 2026-05-08
> Committee: 馬 Ma · 米 Mi · 劉 Liu
> Phase tracker (interactive HTML): [[ThesisRevision/revision-board.html|revision-board.html]]

> [!NOTE] All Dataview `FROM` paths use the `full-research-workflow/` prefix because this board is inside the `2ndbrain` vault — paths resolve from vault root, not from this file's location.

---

## Phase A–E Execution Blocks

```dataview
TABLE status, summary AS "Notes"
FROM "full-research-workflow/30Drafts/_staging" OR "full-research-workflow/20Wiki"
WHERE phase != null
SORT phase ASC
```

---

## All Drafts in 30Drafts/ — by Status

```dataview
TABLE status, project, file.mtime AS "Modified"
FROM "full-research-workflow/30Drafts"
WHERE file.name != "_README"
SORT status ASC, file.mtime DESC
```

---

## Annotation Drafts (ANNOT-*)

```dataview
TABLE status, summary AS "Summary", file.mtime AS "Modified"
FROM "full-research-workflow/30Drafts"
WHERE contains(file.name, "ANNOT")
SORT file.name ASC
```

---

## v2 Scaffolds (highest priority for DOCX integration)

```dataview
TABLE status, file.mtime AS "Modified"
FROM "full-research-workflow/30Drafts"
WHERE contains(file.name, "_v2") OR contains(file.name, "v2")
SORT file.name ASC
```

---

## Staging Pre-Briefs (revision-staging)

```dataview
TABLE status, summary AS "Purpose", file.mtime AS "Modified"
FROM "full-research-workflow/30Drafts/_staging"
SORT file.mtime DESC
```

---

## 6-Dimension Benchmark Reference

| Dim    | Title                              | Owner          | Test                                             |
| ------ | ---------------------------------- | -------------- | ------------------------------------------------ |
| **D1** | Argument integrity                 | 米 Mi           | Defend each section orally                       |
| **D2** | Evidence grounding                 | 馬 Ma           | Each thinker engaged in own terms                |
| **D3** | Novel contribution                 | 劉 Liu          | Squeeze as second-order; every para load-bearing |
| **D4** | Authentic voice                    | Self           | Read-aloud; no AI-detectable prose               |
| **D5** | Methodological reflexivity         | Mi + examiners | Declare + defend lens; link to diagnoses         |
| **D6** | Trans/antidisciplinary positioning | Admissions     | Legible to 7 disciplines (P1–P4)                 |

---

*Board auto-updates as YAML frontmatter `status:` fields change. Requires Dataview plugin.*
*For checkbox-based Phase A–E tracking, open [[ThesisRevision/revision-board.html]] in browser.*
