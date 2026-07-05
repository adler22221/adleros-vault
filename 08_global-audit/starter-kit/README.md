---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Starter Kit — the first three increments, ready to run

These are the **30-day top-three** from the roadmap in `../capacital-blueprint.md`, scaffolded as usable templates so you can start today instead of setting up. Build order is deliberate: cheap proven win → loop-cutter → unblocker. **Do not start increment N+1 until N passes its validation check.**

| # | File | System / need | Effort | Validation gate |
|---|---|---|---|---|
| 1 | `opportunity-fit-scorer.md` | CN-04 opportunity fit — **START HERE** | one sitting | Each score matches the call you'd have made anyway |
| 2 | `ally-coordination-pilot.md` | CN-01 ally-coordination (the loop-cutter) | ~2 sittings + 15 min/wk | One aligned ally completes a tracked micro-ask at lower cost to you |
| 3 | `voice-fingerprint.md` | CN-03 content voice-calibration (the unblocker) | 2–3 sittings | One draft clears your bar with only light edits |

**How to use with Claude Code:** each file is written as a *skill* — a reusable, named prompt-workflow. On the laptop (or the Cubi via SSH), open Claude in this workspace and say e.g. *"run the opportunity-fit-scorer skill on [this opportunity]"* — it reads the template, applies it, and writes the result to `06_agent-out/`. Nothing is sent or made irreversible; you approve every output. This is the whole adlerOS pattern in miniature: **AI drafts and scores; you decide.**

**The one rule that governs all of these** (your own, clm-0027): AI may draft, stage, verify, and add — never delete, overwrite, advance canon, touch T3-flagged content, or write in your voice without disclosure. Every send, every irreversible act, stays yours.
