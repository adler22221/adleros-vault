---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Skill + Pilot: ally-coordination  (CN-01 · the loop-cutter)

**The insight this is built on** (your member-check, clm-0006): your recurring collapse into being "the only one who does things" is **not** a heroism disposition — it's **structural coordination failure**. Aligned, busy allies voice support but don't convert it into work, because the coordination/follow-up/accountability overhead falls entirely on you. This system moves that overhead off you. It is the **highest-leverage test in the whole blueprint**: does removing coordination friction actually produce completed asks?

**Delegatable:** drafting the asks, tracking, follow-up reminders, status digests. **Human-reserved:** who to ask, what the ask is, the relationship itself, any actual message sent.

---

## The pilot (deliberately tiny — one ally, 2–3 micro-asks)

Pick **one** currently-active, aligned ally (from an ongoing alliance — Dojo / IARAEHE / a CR group / 雜學校). Not the hardest relationship; a willing one. The pilot tests the *mechanism*, not the relationship.

### 1. The tracker file — `06_agent-out/allies/pilot-tracker.md`
```
## Ally: [ally A]  (role-tag, no real name in shared views)
Alignment note: <what shared goal>   | Capacity reality: <busy/light — be honest>
Light-participation modes they CAN do: <meeting attendance / a 30-min review / an intro / a name-lend>

| Ask (micro, ≤1 unit of their time) | Framed? | Sent? (you) | Status | Follow-up due | Done? |
|---|---|---|---|---|---|
| <e.g. "review 1 page of the Dojo MVP outline"> | draft ready | ☐ | awaiting | +7d | ☐ |
```

### 2. The `ally-ask-draft` skill
Say: *"Run ally-ask-draft for [ally A]: I want to ask them to <micro-ask>."* It drafts a short, low-friction, respect-their-capacity message (in the right language), sized so a busy person can say yes — and stages it for **you** to send. It never sends.

### 3. The weekly digest (Cubi, scheduled — or run manually on the laptop)
Once/week: *"Run the ally-digest"* → summarizes the tracker: what's awaiting a send from you, what's due for follow-up, what completed. 15 minutes, and you're the coordinator without carrying the coordination.

## Validation gate
Over ~2–3 weeks: **did the one aligned ally complete a tracked micro-ask, at lower coordination cost to you than usual?** If yes → the loop-cutter works; scale to 2–3 allies + add scoper/extractor subagents (90-day step). If no → shrink further (smaller asks) or the constraint isn't coordination for this person; note which and try one more before concluding.

## Guardrails
- Micro-asks only — never offload a whole workstream (that's the failed-hire pattern, clm-0006). Light-but-aligned participation is the design target.
- No auto-send, ever. Relationships are human-reserved.
- If the digest ever takes >20 min or the tracker >~8 open asks, that's a stop-and-shrink signal.
