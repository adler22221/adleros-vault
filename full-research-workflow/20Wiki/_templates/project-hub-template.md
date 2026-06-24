---
aliases: ["[Short project title]", "[Abbreviation if any]"]
type: project-hub
project: theme-target-type
status: active
target-venue: "[Full name of submission venue]"
target-date: YYYY-MM-DD
output-type: thesis
word-count-target: 0
current-phase: "[Phase name]"
summary: "[One sentence: what this work argues or achieves]"
---

# [Full Project Title]
*[Venue name] · [Output type] · Due [date]*

> [!INFO] Active Now
> **Phase:** [current phase name]
> **Working on:** [[draft-filename]] — [one-line description of active task]
> **Next blocker:** [what's blocking progress; use [[link]] if it's a file]
> **Deadline:** YYYY-MM-DD

---

## Goal
[1–2 sentences: the core argument, thesis statement, or deliverable goal. What will this submission accomplish that doesn't already exist?]

---

## Submission Requirements

| Item | Detail |
|------|--------|
| Venue | [full name] |
| Format | [format, style guide, submission system] |
| Word limit | [N words / pages] |
| Hard deadline | [date] |
| Language | English / 中文 / 日本語 |

---

## Progress

| Phase | Description | Status |
|-------|-------------|--------|
| A | [phase name and goal] | ✅ Done / 🔄 Active / ⬜ Pending |
| B | | |
| C | | |
| D | | |
| E | | |

---

## Key Files

### Primary Document
- [[path/to/main-document\|Main document]] — working draft

### Project Infrastructure
- [[project-id/CLAUDE.md\|Project rules]] — deadlines, file roles, NLM policy
- [[path/to/review-comments\|Review / examiner comments]] — authoritative change instructions
- [[path/to/revision-tracker\|Revision tracker]]

### Operational
- `.claude/transcript-config.json` → points to `project-id/conversation-history-raw.md`

---

## Canonical References Used
*Pages in `20Wiki/` this project draws on — link here so they appear in their backlinks too:*

[[squeeze-ontology]] · [[method-frame]] · [add others]

---

## Core Literature
*Key notes in `10Literature/` — link to the compiled notes, not raw PDFs:*

[[citekey1]] · [[citekey2]] · [[citekey3]]

---

## Active Drafts

```dataview
TABLE status, summary AS "Notes", file.mtime AS "Modified"
FROM "full-research-workflow/30Drafts"
WHERE project = "theme-target-type"
SORT file.mtime DESC
LIMIT 10
```

---

## Decisions & Pivots
*Running log — newest first. Link to the note or session where the decision was made.*

- **YYYY-MM-DD** — [decision or pivot; [[link]] to relevant note if applicable]

---

*Hub page for [[project-id]]. All project files link back here via `[[project-id]]`.*
*Template: `20Wiki/_templates/project-hub-template.md`*
