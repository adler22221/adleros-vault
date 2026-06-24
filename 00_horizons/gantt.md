---
created: 2026-06-24T23:22
author: human
type: dashboard
title: Gantt
---
# 🗓️ Gantt — dependencies & timeline (single store, interoperable)

> Renders from the **same `02_tasks` notes** (no parallel store) using their `scheduled` / `due` / `depends-on` fields.
> **Phase-2 decision:** if you want an *interactive* Gantt (drag + auto-reschedule + dependency arrows), adopt
> **obsidian-pm** and point its task folder at `02_tasks` — it operates on the same notes. This Dataview→Mermaid
> version below is the zero-dependency, read-only fallback. **Draft — tune against real data once tasks are migrated.**

```dataviewjs
// DRAFT: builds a Mermaid Gantt from tasks that have both `scheduled` and `due`.
const tasks = dv.pages('"02_tasks"').where(t => t.scheduled && t.due && t.state !== "done");
let g = "gantt\n  dateFormat YYYY-MM-DD\n  title Timeline\n  section Tasks\n";
for (const t of tasks) {
  const id = String(t.file.name).replace(/[^A-Za-z0-9]/g, "");
  const start = String(t.scheduled).slice(0, 10);
  const end = String(t.due).slice(0, 10);
  g += `  ${t.file.name} :${id}, ${start}, ${end}\n`;
}
dv.paragraph("```mermaid\n" + g + "\n```");
```
