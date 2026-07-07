---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# adlerOS Orchestrator — System 0, the coordination node

> Added 2026-07-05 after member review: the blueprint described the vault as "substrate" and listed shared infrastructure, but never named the **central orchestrator** explicitly. Without it, the nine systems are nine separate tools — which reproduces the exact structural problem the audit found. The orchestrator IS the externalized coordination layer; it is the leverage move, not scaffolding around it. See the architecture map in the dashboard / this session.

## Why "System 0"
The audit's central, member-confirmed finding: the overcommitment→collapse loop runs because **no coordination layer exists outside your head** — you are simultaneously the dispatcher, router, coordinator, and approver, so everything bottlenecks on one nervous system with a cardiac governor. adlerOS-as-orchestrator externalizes dispatch + routing + governance. It is the structural fix for CN-01/05/12, and the substrate the other eight systems ride on. Everything else in the blueprint either builds it (System 1) or runs on it.

## The coordination model: blackboard, not switchboard
The nine systems **never call each other.** Each reads/writes shared state in the vault; the orchestrator dispatches on that state. Coordination is *stigmergic* (trail-following), which is why systems are loosely coupled and addable one at a time.

**One task's life:**
1. **Signal** — email / note / calendar event / a priority you set in `00_horizons` → lands in `05_collab-inbox`.
2. **Dispatch + routing** reads it → routes by *(system owner, device, model tier, privacy tier)*. The fellowship-applications model router is the standing cost policy; T3 → Cubi-local, else laptop-cloud.
3. **System skill runs** → writes a **draft** to `06_agent-out` (never canon).
4. **Governance membrane** guarantees it stops there (entropy firewall + agent-boundary clm-0027 + privacy tiers): agents draft/stage/verify/add; never send/delete/advance-canon/touch-T3/speak-in-your-voice.
5. **You** read the `07_agent-synthesis` digest at the weekly sitting, approve, and *advance it yourself*. The loop closes at the one point that must be human.

**Cross-system flows are emergent, through the vault** (no point-to-point wiring):
- Finances writes a runway figure → Relationship reads it for the partner-support plan (CN-13).
- Research produces a finding → Outreach's repurposer picks it up (CN-06 → CN-03/02).
- Ally-coordination completes a tracked task → freed capacity flows to the dream projects (CN-01 → CN-06).
- Health/schedule-protection writes load limits → dispatch honors them across *every* system (CN-10 is the cross-cutting governor).

## The three orchestrator layers
1. **Vault = blackboard (canonical, passive state).** `00_horizons` (priorities), `02_tasks`/`03_projects` (work), `12_people` (ally/relationship graph), and the agent lanes `05_collab-inbox → 06_agent-out → 07_agent-synthesis`. Everything reads/writes here; nothing coordinates elsewhere. T3 systems use a **local-only analog on the Cubi**, outside every sync path.
2. **Dispatch + routing (active nervous system).** Reads state → assigns *(system, device, model tier, privacy tier)*. Built from: the model router (already exists), a **daily meta-agent** (scheduled — reads the inbox/horizons, queues work), **hooks** (event-triggered — a new email/note/gnucash-export fires the right system), and **manual invocation** (you asking Claude to run a skill). No system re-decides policy.
3. **Governance membrane.** The entropy firewall (agents write to lanes; only you advance to canon), privacy tiers (T3 never leaves local), the agent-boundary rule (clm-0027). Enforced *structurally* — separate folders/states with no agent-executable transition across the human gate — not as policy hope.

## It is NOT a big-bang build
The orchestrator emerges from three things you mostly have:
- **The vault conventions** (the `05/06/07` lanes already exist in your 2ndbrain) — this is the blackboard, today.
- **The model router** (inherited verbatim from fellowship-applications) — this is routing, today.
- **A thin dispatch skill + a daily scheduled meta-agent** — the one genuinely new piece, and small: a skill that reads `05_collab-inbox` + `00_horizons`, tags each item with its system/device/tier, and writes a queued digest to `07_agent-synthesis` for your review. Everything else is the nine systems plugging into lanes that already exist.

So the build order is unchanged: the **opportunity-fit-scorer** (System 3 START-HERE) is the first system to plug into the orchestrator; the **ally-coordination pilot** (System 1) is the first to exercise the dispatch/tracking loop; the **dispatch meta-agent** is stood up once two systems are live and there's real cross-system state to coordinate (≈ the 90-day mark). Don't build the orchestrator empty — grow it as the systems that feed it come online.

## Mapping to your under-construction adlerOS
This is the same adlerOS you've been building in Obsidian — named, given a control model, and made the explicit hub. The Stage-B 13-lane migration and capture daemon that stalled are **not prerequisites**: the orchestrator runs on the lanes you already have. Build ON, never wait for the stalled migration (the gap-analysis stall diagnostic is binding here too).

## Guardrail: the capacity paradox
The orchestrator must not become another overcommitment. It earns its keep only by *removing* coordination load from you. Metric (CN-12, quarterly): is capacity actually being freed, and flowing to the book, the platform, and the family design? If standing review load exceeds ~1 hr/week, that is a stop-and-shrink signal, not a build-more signal.
