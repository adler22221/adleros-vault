---
type: project-hub
title:
author: human
status: canonical
project:             # project-id (theme-target-type)
parent-project:      # [[mother project]]  (omit if top-level)
goal:                # [[horizon this serves]]  → rolls up to Mission
state: ongoing       # your lifecycle: prospective | ongoing | dormant | past  (≈ ACE on|ongoing|simmering|sleeping)
work-dir:            # path under work/ if it has a heavy pipeline (e.g. work/thesis-revision)
created:
---
# {{title}}

## Goal & why  (links up to [[Mission]] / [[2026]])
## Child projects
- 
## Open tasks
```dataview
TABLE state, priority, scheduled FROM "02_tasks"
WHERE contains(goal, this.file.link) AND state != "done"
SORT priority ASC
```
## Key notes & references
- 
