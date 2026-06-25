---
created: 2026-06-24T23:22
author: human
type: dashboard
title: Home
---
# 🏠 Home — control panel

> Activates once notes are migrated into the lanes (these are draft Dataview blocks; Bases can replace them later).
> Requires the **Dataview** plugin. Queries may need light tuning against real data.

## 🎯 Today
```dataview
TABLE priority, goal, contexts FROM "02_tasks"
WHERE state = "todo" AND (scheduled = date(today) OR due = date(today))
SORT priority ASC
```

## 🧗 The rollup — open tasks grouped by goal/horizon  *(proves day → … → Mission)*
```dataview
TABLE length(rows) AS "# open" FROM "02_tasks"
WHERE state != "done"
GROUP BY goal
```

## 🌳 Ideas ready to publish
```dataview
TABLE maturity, output FROM "04_ideas"
WHERE maturity = "to-publish" OR maturity = "evergreen"
SORT file.mtime DESC
```

## ⚠️ Stalled goals — no activity 14+ days  *(Coach guardrail)*
```dataview
TABLE (date(today) - file.mtime).day AS "days idle" FROM "00_horizons"
WHERE date(today) - file.mtime > dur(14 days)
SORT file.mtime ASC
```

## 🔋 Energy (last 14 days)
```dataview
TABLE energy, mood, clarity FROM "01_journal/daily"
WHERE date(today) - date(date) <= dur(14 days)
SORT date DESC
```
