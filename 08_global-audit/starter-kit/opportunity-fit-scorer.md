---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Skill: opportunity-fit-scorer  (CN-04 · START HERE)

**What it does:** scores an incoming opportunity (grant, fellowship, job, invitation, collaboration) against your own decision criteria, so the apply/decline call is fast, consistent, and documented — formalizing the one AI-delegation you already do informally and trust (clm-0010, member-confirmed).

**Delegatable:** the scoring + write-up. **Human-reserved:** the final apply/decline decision, and any weight you override.

---

## The rubric (4 dimensions, score each 1–5)

| Dimension | 1 (poor) → 5 (strong) | Why it's here (from your persona) |
|---|---|---|
| **Program fit** | Does it advance the 2026–2030 program (book / unschooled doctorate / prefigurative-academia platform)? 5 = directly advances a named priority. | Your stable espoused program (clm-0001, C5) |
| **Cardiac-safety load** | Does the timeline/travel/intensity respect the cardiac constraint? 5 = low load, no deadline-crunch collision. **Score 1–2 = a near-automatic decline regardless of other scores.** | Health as decision-governor (clm-0023, confirmed) |
| **Mission alignment** | Does it fit the systemic / bottom-up / cooperative / anti-dependence values (stable since 2009, corroborated)? 5 = deeply aligned; 1 = requires compromising them. | Core values (clm-0006/0051, corroborated 2015) |
| **Bread vs dream** | Is this livelihood ("bread") or mission ("dream")? Not scored — **labeled**. Note which, and whether it's a *deadline-bound bread* (higher completion odds) or an *open-ended dream* (risk of expansion). | Your member-checked bread/dream distinction (clm-0035) |

**Flags (note, don't score):**
- ⚑ **Taiwan-alignment**: if the funder/reviewer is Taiwan-based, flag it — your alignment with Taiwan funders is low (clm-0011, member noted), so weight the fit-signal down.
- ⚑ **Allocation-dependence**: does accepting increase dependence on one funder/institution? (Your anti-dependence lens applies to your own position too.)
- ⚑ **Anti-cult**: does it require reputation-building by mystical/new-age/cult-like means? If yes → decline (your explicit boundary, clm-0033).

---

## Output template (the skill fills this per opportunity)

```
### <Opportunity name> — <date scored>
Link/source:
Deadline:            | Bread/Dream:            | Taiwan? (flag):
Program fit:      /5  — <one line>
Cardiac-safety:   /5  — <one line; if ≤2, say "DECLINE-LEANING on load alone">
Mission align:    /5  — <one line>
Flags: <allocation-dependence / anti-cult / other>
── Composite read: <APPLY / DECLINE / DEFER-&-WATCH> ──
Rationale (2–3 sentences):
Effort-to-apply estimate:            | If apply: reuse from prior app? <which>
```

## How to run it
Open Claude in this workspace and say: *"Run the opportunity-fit-scorer skill on <paste the opportunity / link>."* It applies the rubric, writes a row to `06_agent-out/opportunities/tracker.md`, and gives you the composite read. **You make the call.**

## Validation gate (15 min)
Run it on the 2–3 opportunities already in front of you. **Did each composite read match the decision you'd have made anyway?** If yes → the skill is trustworthy; proceed to increment 2 (ally-coordination). If it diverged, adjust a weight and note why — that tuning IS the value.
