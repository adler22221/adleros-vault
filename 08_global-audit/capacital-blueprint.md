---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Capacital Blueprint — the integrated adlerOS capacital-systems architecture

**Phase 4, deliverable 2 (integration).** Consolidates the nine system specs in `05_blueprint/systems/`, `gap-analysis.md`, `capacital-needs.md` (CN-01..14), and `04_persona/persona-v3.1.md` into one coherent blueprint. Privacy: T3 discipline throughout — third parties role-tagged only ([partner], [father], [Adler's mother], [Adler's sister], [partner's parents]); no names, no figures, no medical or financial specifics anywhere in this document. This file is itself T2 (mechanism, not content) but governs T3 systems.

---

## 1. Executive summary — the whole architecture on one page

**adlerOS becomes a VMCL capacital system.** In Cabrera's frame — Vision, Mission, Capacity, Learning — the audit found that your Vision (regenerative-reciprocal coexistence; book, unschooled PhD, platform, 2026–2030) and Mission (one continuous 16-year program) are unusually stable and member-verified. What has never matched them is **Capacity**: a planetary-scale, multi-person-team workload carried by one person with a cardiac governor, a DSPS chronotype, thin financial runway, and a family architecture under strain. And **Learning** has lived in your head and your instance notes, not in the systems themselves. This blueprint is the Capacity-and-Learning half of the VMCL loop, built as what you named them: *prosthetics under your conscious direction* (clm-0034) — systems that surface blind spots, never hide them.

**The nine systems** (mapped to the fourteen capacital needs):

| # | System (file) | Needs served | Delegable share |
|---|---|---|---|
| 1 | Operations & ally-coordination | CN-01, 05, 12 | ~70% |
| 2 | Outreach & internet engagement | CN-02, 03, 07 | ~70% |
| 3 | Opportunity & applications | CN-04, 08 | ~70% |
| 4 | Business development & career | CN-05, 09 | ~65% |
| 5 | Research & publication | CN-06, 11 | ~65% |
| 6 | Health management | CN-10 | ~55% |
| 7 | Finances management | CN-09 + CN-13 runway wiring | ~70% |
| 8 | Relationship management | CN-13 | ~35% |
| 9 | Family conflict resolution | CN-14 | ~55% |

Weighted across the portfolio, **roughly 60% of the recurring workload in these domains is delegatable to agents** (range 35–70%), with the reserved ~40% concentrated exactly where your standing rules put it: every send, every submit, every argument, every relational judgment, every irreversible or identity-bearing action (clm-0027, clm-0039).

**The ONE core leverage move.** The member-check replaced the "overcommitment/martyrdom" story with a structural diagnosis: the R1 collapse loop runs because *no coordination layer exists* — allies voice support, work concentrates on the one person who does things, reserves get spent as the buffer, depletion follows. The fix is not more heroics, more discipline, or better habits. It is **structural coordination capacity**: an agent layer that captures commitments, sizes micro-asks to what busy allies can actually do, follows up without you chasing, and tracks contribution — plus the eight sibling systems that take everything else mechanical off the one pair of hands. Two paid hires already failed at this; agents are the first team members whose labor is cheap, tireless, and bounded enough to fit the actual shape of the problem. Everything in this blueprint either cuts that loop directly (System 1) or frees the capacity the loop has been consuming (Systems 2–9).

**The build discipline that governs everything**: the gap analysis's stall diagnostic is binding. Maturity in your corpus correlates with *narrow scope and deadline pressure*, never with design sophistication — the 13-lane vault and capture daemon stalled; the exam prep, the translation job, and the fellowship run all shipped. So every increment below is narrow, deadline-anchored, and additive to something already working. No system in this blueprint requires a platform to be "finished" before it pays.

---

## 2. Shared infrastructure — the adlerOS core all nine systems reuse

None of the nine systems invents a platform. They all sit on six shared components that already exist and already work (gap-analysis §3). Build ON, never replace.

**2.1 The model router (free-first tiering).** Inherited verbatim from fellowship-applications (`MODEL_SWITCHING.md` + `token_tracker.py`): free-tier/Haiku-class for bulk scanning and triage → Sonnet for structured extraction, coding, and synthesis → Fable/Opus reserved for high-stakes drafting and voice-sensitive passes → **local model (Cubi, Qwythos-9B) for anything T3**, where privacy overrides cost. No system re-decides cost policy; the router is the standing answer. This honors build-not-buy (clm-0030): near-zero marginal cost to run.

**2.2 The 2ndbrain vault as substrate.** The live agent lanes — `05_collab-inbox` (capture in), `06_agent-out` (AI-drafted material out), `07_agent-synthesis` (digests and rollups) — already exist in the current vault. Every system writes there *now*; nothing waits on the stalled Stage-B 13-lane migration. The entropy-firewall convention holds everywhere: **AI writes to its lanes; only you advance anything to canon.** T3 systems use a local-only analog of these lanes on the Cubi, outside every sync path.

**2.3 The standing agent-boundary rule (clm-0027).** Agents may **draft, stage, verify, and add. They never delete, overwrite, advance canon status, send a message, submit an application, move money, or speak in your voice undisclosed.** Every pipeline in this blueprint enforces this structurally (separate folders/states with no agent-executable transition across the human gate), not as a policy hope.

**2.4 The privacy tiers (privacy-tiers.md).** T1/T2 content (public listings, your own public writing, drafts meant for audiences) runs on cloud tiers under the router. **T3 content — journals, health data, finances, family/relationship material — never transits a cloud model, period.** Role-tags only, zero verbatim, no figures, no medical specifics in any synced or model-visible layer. Three systems (7, 8, 9) are T3-walled end-to-end; System 6 splits (health data local, scheduling logic laptop-side with no health content).

**2.5 Device / agent division of labor.** The triad is a deliberate architecture, not an accident of what you own:

| | **Laptop** | **Cubi** | **Phone** |
|---|---|---|---|
| **Role** | MCP-connected heavy work | Always-on private/offline agent + overnight automation | Remote steering |
| **Connectors** | Gmail, Drive, Calendar, browser MCP | None (by design) | SSH into Cubi/laptop |
| **Model tier** | Cloud (Haiku→Sonnet→Fable/Opus) | Local only (Qwythos-9B, 3.7 tok/s — light/scheduled, never bulk) | n/a |
| **Privacy ceiling** | T1/T2 only | T3 home base | Read/approve only; no sensitive drafting on a phone screen |
| **What runs here** | Drafting pipelines, funder/lead scans, voice-scoring, reviewer-tracking, your weekly review sittings, all MCP staging (Gmail drafts, calendar checks) | Runway models (financial + relationship), health-data aggregation, family chronology/drafting, tracker refreshes, weekly/monthly cron digests, claude-mem continuity | Check "is the batch ready," approve/reject from digests, nudge a staged run while traveling |

The Cubi's benchmark verdict (3.7 tok/s) is respected everywhere: it is the *reliable, private, always-on* seat, not the fast one. Anything bulk goes to cloud tiers on the laptop; anything sensitive stays on the Cubi even though it's slow — the jobs routed there are low-volume and latency-tolerant on purpose.

**2.6 Proven patterns reused across systems.** The fellowship-applications 5-role pipeline (orchestrator→researcher→writer→reviewer→editor, iterate to score ≥7) is the subagent template for Systems 1, 2, 3, 4, 5. The zenrich pattern (bulk batch + `needs-review` queue) is the template for every scan/digest job. The full-research-workflow status machine (ai-draft→…→published, forbidden transitions) governs every artifact's lifecycle. The content-once-generate-many pattern (licensing-exam, translate_pptx) powers repurposing. The global-audit corroboration pipeline is productized as a callable verification service.

---

## 3. The nine systems

### 3.1 Operations & ally-coordination (CN-01, 05, 12) — the loop-cutter

**Purpose**: convert allies' light-but-aligned participation (meeting attendance, voiced support) into distributed, tracked progress — the structural fix for the R1 loop you named yourself. **Delegated (~70%)**: meeting-notes→candidate-task extraction; sizing asks to ally bandwidth (the `task-scope-check` skill hard-codes the failed-hire lesson: never ask a volunteer for employee-shaped work); drafting warm, low-pressure asks into held Gmail drafts; reminder cadences on accepted tasks; the standing who-owes-what tracker; a weekly digest. **Human-reserved**: who gets asked at all, every first send, escalation tone, dropping a thread, any commitment in your name. **First increment**: a single-ally, single-channel pilot — one markdown tracker, one `ally-ask-draft` skill, one weekly Cubi digest; you hand-scope 2–3 micro-tasks over the month. **Interlocks**: cuts the overcommitment loop that starves every other domain; its freed hours are the "dream"-side dividend the whole blueprint exists to pay; its drafter is a lightweight cousin of System 2's voice calibration (short operational messages — a much lower bar than public content).

### 3.2 Outreach & internet engagement (CN-02, 03, 07) — the unblocker

**Purpose**: turn one authored argument into many faithful reconfigurations (blog, newsletter, SNS, scholarly note) in three languages, at a cadence independent of your bandwidth — with **voice calibration (CN-03) as the keystone investment**, because until AI drafts clear your authorship bar, CN-02 stays abandoned-by-default and reach stays below the 2016 documentary. **Delegated (~70%)**: repurposing drafts, style-scoring against a readable style-fingerprint checklist you can correct, translation (translate_pptx QA pattern), scheduling/posting mechanics, weekly scholarly-community digests (CN-07), analytics. **Human-reserved**: the seed argument, final publish approval on every piece, voice-corpus curation, disclosure wording, any re-engagement judgment. **First increment**: voice-calibration loop + one repurposing skill, one seed argument, one language, two formats. Validation: did you approve at least one draft with only light editing? **Interlocks**: **CN-03 unblocks CN-02** — the whole system is sequenced around that dependency; the voice-scorer also serves System 4's bizdev drafting; the community digest reuses zenrich; publish scheduling soft-checks System 6's protected mornings.

### 3.3 Opportunity & applications (CN-04, 08) — the cheap proven win

**Purpose**: formalize the fit-evaluation you already do (clm-0010, the one proven daily AI-delegation habit) into a 4-dimension scored rubric — 2026–2030 program fit / cardiac-safety load / mission alignment / Taiwan-alignment flag — then grow a weekly non-Taiwan funder scan on top of it, so runway risk stops depending on what happens to arrive. **Delegated (~70%)**: scanning, rubric scoring, shortlist digests, deadline/status tracking, drafting via the existing fellowship 5-agent pipeline. **Human-reserved**: every submit decision, the rubric weights, the "high fit" cutoff, any funder outreach in your voice. **First increment**: the `opportunity-fit-scorer` skill + a bare markdown tracker; score 2–3 live opportunities; check the scores against your gut. **Interlocks**: the rubric is shared with System 4 (bread-opportunity screening) and System 7 (runway-impact dimension); the scout directly attacks the runway risk that System 8's commitment depends on; cleared opportunities flow to the already-working fellowship drafting pipeline.

### 3.4 Business development & career (CN-05, 09)

**Purpose**: run bread as a bounded standing portfolio instead of a side effect of the loudest deadline — manufacture the deadline, delegate the volume. **Delegated (~65%)**: lead scanning, fit scoring, pitch repurposing (content-once-generate-many), proposal drafting (fellowship pipeline reused verbatim), pipeline/invoice tracking, monthly capital-conversion review draft. **Human-reserved**: anything that spends money, reputation, or identity — submit/sign/invoice/accept, rates and positioning, which capital gets converted (the sacred core is never monetized, clm-0042; no guru-branding, ever, clm-0033), whether the 推拿 license path is pursued. **First increment**: `fit-rubric-score` skill + one hook (tag a note `bizdev/lead` → score sheet appears). **Interlocks**: shares the rubric with System 3; its income is one of the two inputs System 7's runway model tracks; it sees System 8's financial target only as a role-tagged pointer ("a dated target exists"), never the figure — the T3 wall runs between them.

### 3.5 Research & publication (CN-06, 11)

**Purpose**: your densest-served, bread-AND-dream domain — extend and de-friction, don't invent. Mechanics of production (citations, reviewer-point bookkeeping, evidence verification, submission logistics) move to agents; the argument and every publishable academic sentence stay yours (clm-0039, identity-level here). **Delegated (~65%)**: `reviewer-tracker` (reviewer letter → section-mapped checklist), `cite-check`, `lit-scan` (weekly Cubi cron), `corroborate-claim` — the productized version of this audit's own archival-corroboration machinery (CN-11), returning evidence trails, never verdicts. **Human-reserved**: the claims, the prose, submission decisions, corroboration verdicts, all canon advancement. **First increment**: `reviewer-tracker` against the live JASA/JCR letters — zero new wiring, immediate deadline anchor. **Interlocks**: freeing capacity here is the highest-leverage capacity in the blueprint because bread and dream don't compete in this domain; `corroborate-claim` becomes a service Systems 8/9 can call for chronology work (T3-gated when it does); the reviewer/editor machinery is the same engine Systems 2/3/4 reuse.

### 3.6 Health management (CN-10)

**Purpose**: two halves — (a) actively defend the DSPS-protected morning window (the one recurring, undefended, weekly-to-monthly harm), and (b) aggregate three passive T3 data streams (Apple Health, Garmin, wellnesstracker) into a local, triangulated decision governor that encodes your own Western+TCM+functional rule (clm-0025) as a fixed packet format. **Delegated (~55%)**: calendar-collision detection + reschedule/async drafts (never sent); nightly Cubi aggregation; triangulation-packet assembly (data / TCM-framing questions / lifestyle levers — never a verdict); weekly digest. **Human-reserved**: every actual health decision (with your clinicians), all interpretation, every send, any cross-domain invocation of the cardiac governor. **First increment**: the Scheduler-Defender half only — calendar hook + `schedule-defend` skill; touches zero health content. **Interlocks**: every other system's scheduling respects its protected window; the hard guardrail runs toward Systems 8/9 — health-timeline material never exports into family-facing artifacts with causal framing (the cardiac-causation hypothesis stays disconfirmation-pending, clm-5306).

### 3.7 Finances management (CN-09 + CN-13 wiring) — T3, Cubi-only

**Purpose**: a local ledger-and-forecast layer over gnucash — monthly burn, months-of-runway, deviation flags, bread-opportunity screening — so career and bread-vs-dream decisions get made with numbers instead of dread, and the runway commitment becomes a tracked, recomputed plan instead of a midnight worry. **Delegated (~70%)**: transaction categorization (zenrich batch + needs-review queue), runway recomputation on every ledger export, deviation flags, decision briefs, opportunity screening with a runway-impact dimension. **Human-reserved**: every transfer/payment/account action (no write-back path even exists), the bread-vs-dream hour allocation, any disclosure of numbers to [partner] — in your words, at your timing. **First increment**: the `runway-recompute` skill, run manually once: one number you don't currently have on demand. **Interlocks**: **this is the coupling between money and the relationship runway** — CN-13's commitment is the first dated financial target the bread economy has ever had, and this system is the wiring that measures progress toward it; Systems 3/4 feed the income side; only a non-sensitive summary ("runway: N months") ever leaves the Cubi.

### 3.8 Relationship management (CN-13) — T3, Cubi-only, most human-reserved

**Purpose**: give the runway plan a living, private home (scenario recomputation as career options move) and make counselor-session prep cheap (chronology assembly, redaction, role-labeling, formatting) — so your composure in crisis moments is spent on the relational work itself, not on re-deriving numbers and timelines under stress. **Delegated (~35% — deliberately the lowest)**: arithmetic and scenario recomputation on inputs you supply, chronology skeletons, redaction checking (a separate adversarial subagent pass), formatting, versioned plan history, clearly-labeled draft-only message candidates. **Human-reserved (65%)**: everything relational — what to say, when, to whom; the actual target number and date as commitments; the instrumental-vs-relational separation (the anniversary-episode lesson, clm-5309, is operationalized as a skill flag, not a memory burden); every send, always. **First increment**: the `runway-scenario` skill alone, run manually on the Cubi against one plain-text inputs file. **Interlocks**: couples to System 7 (the financial actuals) and Systems 3/4 (the income options that move the scenarios); shares the counselor-briefing pattern with System 9; zero MCP connectors, zero cloud calls, by design.

### 3.9 Family conflict resolution (CN-14) — T3, Cubi-only, most sensitive

**Purpose**: move the preparatory work of family repair out of crisis windows into calm, scheduled moments — chronology assembly for counselor briefings, protocol-checked repair-message drafts, de-triangulation scripts protecting [Adler's mother] and [Adler's sister], mediated re-entry sequencing options (the unused assets: [partner's mother]'s standing offer; [father]'s reported guilt as an opening), and a three-parent-unit care/cost scaffold so the feared incapacitation scenario has a partial plan instead of only dread. **Delegated (~55%)**: chronology assembly, generic public welfare/care-option research, budgeting templates (structure only — figures stay yours, local), draft candidates, sequencing worksheets (always 2–3 options with tradeoffs, never a recommendation), hypothesis-guardrail checks. **Human-reserved**: whether/when/how to re-approach [father], every word spoken or sent to any family member, any use of health-timeline material, all psychological interpretation (reserved for the counselor), every financial or care commitment. **First increment**: `family-chronology-assemble` + a local non-synced drafts folder, used once before a real counselor session. **Interlocks**: this is the leg of the triple-squeeze (R2, candidate) that could flip sign from stress-source to support-source — a small mediated improvement here de-amplifies every other loop; the mechanical `hypothesis-guardrail-check` enforces the cross-system rule that the cardiac-causation hypothesis is never deployed as a verdict.

---

## 4. Leverage-ranked build roadmap

Sequencing logic = **leverage × cost × dependency**, filtered through the stall diagnostic (narrow, deadline-anchored, additive). Three moves anchor everything: the *cheap proven win* first (momentum + shared rubric), the *loop-cutter* second (highest structural leverage), the *unblocker* third (the keystone investment). Nothing here asks you to build nine systems at once — each month ships one or two validated increments, and **no increment starts until the prior one passes its validation check**.

> ### ▶ START HERE — this week
> **Build the `opportunity-fit-scorer` skill (System 3 / CN-04).** One sitting, on the laptop:
> 1. Write your existing informal rubric down as a 4-dimension scored markdown template (program fit / cardiac-safety load / mission alignment / Taiwan-alignment flag).
> 2. Save it as a named, reusable skill.
> 3. Run it on the 2–3 opportunities already in front of you; log the rows in `06_agent-out/opportunities/tracker.md`.
> 4. Fifteen-minute check: did each score match the call you'd have made anyway?
>
> **Why this one**: it formalizes the *only proven, habitual* AI-delegation success in your corpus (clm-0010) — no new trust required, no new infrastructure, no privacy exposure, done in an afternoon, and it produces the rubric that Systems 4 and 7 immediately reuse. It is the cheapest possible first rep of the build-validate-extend muscle every later system depends on.

**Next 30 days (July 2026)** — three narrow increments, in order:
1. **CN-04 fit-scorer** (above) — the cheap proven win. *Effort: one sitting.*
2. **CN-01 single-ally pilot** (System 1) — the loop-cutter: one tracker file, one `ally-ask-draft` skill, one weekly Cubi digest; 2–3 hand-scoped micro-asks to one active ally. *Effort: ~2 sittings to stand up, ~15 min/week to run.* This is the highest-leverage test in the whole blueprint: does removing coordination friction actually produce completed asks?
3. **CN-03 voice-calibration first pass** (System 2) — the unblocker: you pick 5–8 of your own public pieces as the voice corpus; the style-fingerprint skill produces a checklist you correct; one seed argument → blog piece + SNS thread. *Effort: 2–3 sittings, front-loaded on your corpus curation.*

Also cheap enough to slip in if energy allows (each one sitting, each immediately load-bearing): **CN-10 Scheduler-Defender** (calendar hook + draft skill — defends this week's mornings), **CN-06 reviewer-tracker** (against the live JASA/JCR letters), **CN-13 runway-scenario** (one Cubi skill, one inputs file — the midnight-notes plan becomes a file). These three are deliberately independent; none blocks the top three.

**Days 30–90 (Aug–Sep 2026)** — extend only what validated:
- CN-04 → add the **weekly funder-scout** (CN-08) on top of the now-trusted rubric; non-Taiwan seed list, shortlist-only digests.
- CN-01 → extractor/scoper subagents + scale to 2–3 more allies, *only if* the pilot ally completed tracked micro-tasks at lower cost to you.
- CN-03 → translation pass + posting-staging hooks + the CN-07 community digest, *only if* at least one draft cleared your bar with light edits.
- CN-13 → `counselor-briefing` skill, timed to a real session; CN-14 → `family-chronology-assemble` before its next real use. (T3 pace is deliberately slower — these systems should get *quieter* over time, not busier.)
- CN-09/07 → `runway-recompute` on the Cubi + gnucash-export hook; first monthly heartbeat snapshot.
- CN-10 → if the Scheduler-Defender deflected at least one real collision, begin the local health-aggregation half (Cubi, nightly).

**Months 6–12 (2027 horizon)** — the compounding layer:
- **CN-02 at cadence**: multi-channel, multi-language publishing with trust-band review (spot-check, never zero review) — reach work that finally runs during deadline weeks.
- **CN-05 emerges instead of being built**: the "team of role agents" is grown out of the shipped narrow systems (the gap analysis is explicit: platform-first is the proven failure mode). By now the orchestrator/researcher/writer/reviewer/editor roles are running in four domains; CN-05 is their consolidation, not a new build.
- **CN-14 sequencing work**: mediated-reentry options + care/cost scaffold with real (local) numbers — paced by counselor guidance and real conversations, not by the roadmap.
- **CN-08/09/13 coupling matures**: funder pipeline + bread portfolio measured monthly against the runway target's 2027–2028 window — the first time the dream economy has had a dated, tracked finish line.
- **CN-12 read as the outcome metric**: quarterly, ask the only question that matters — is capacity actually being freed, and is it flowing to the book, the platform, and the family design?

**Honest effort accounting**: the 30-day slate is roughly 6–9 focused sittings of build time plus ~30–45 minutes/week of standing review (the weekly digest/approval passes). That is real cost, taken from real capacity. It is spent once; the coordination overhead it replaces is spent forever. If any week's review load exceeds ~an hour, that is a stop-and-shrink signal, not a push-harder signal.

---

## 5. How to actually build these — a primer

You're new to these mechanisms, so here is the working vocabulary once, in plain terms (each system spec repeats these with domain examples):

- **Skill** = a saved, reusable prompt-workflow you invoke by name — a recipe card, so you never re-explain a repeatable job. Your `research-hub` sub-skills already are skills; this blueprint just names the pattern and multiplies it.
- **Hook** = an automatic trigger tied to an *event* — "when a file lands in this folder / a note gets this tag, run that skill." Nobody has to remember anything; that's the point.
- **Scheduled/cron agent** = a job that runs on a *timer* — "every Monday 06:00, compile the digest" — and leaves output waiting in your lanes. Set once, runs without your initiative.
- **Subagent division of labor** = splitting one job into narrow roles that hand off (extractor → scoper → drafter → reviewer), like a small team, instead of one agent doing everything in one pass. You already own the proven template: the fellowship-applications 5-role pipeline.
- **MCP connector** = the bridge that lets an agent actually operate a real tool (your Gmail, Drive, Calendar, browser) instead of just talking about it. Laptop-only, T1/T2-only, in this architecture.

**How you'd stand up the first increment (the fit-scorer), concretely**: (1) open a session on the laptop; (2) dictate your informal rubric while the agent structures it into a markdown template with the four scored dimensions and a rationale paragraph; (3) save it under a skills folder as `opportunity-fit-scorer`; (4) paste in a live call-for-proposals and invoke the skill by name; (5) read the score sheet, correct anything that doesn't match your judgment, and let the corrections update the template; (6) append the row to the tracker. That's a complete build-validate loop in one afternoon. Every subsequent skill in this blueprint is the same shape: write the workflow down once, run it on something real immediately, correct it, and only then automate it with a hook or a schedule.

**The Cubi's role in your builds**: think of it as the quiet night-shift employee with a locked filing cabinet. It holds everything T3 (finances, health data, relationship/family material) on local storage with a local model, and it runs the timers — tracker refreshes, weekly digests, monthly runway recomputes — overnight, so results are waiting in `06_agent-out` when you surface (DSPS-compatible by design: everything is pull, not push). It is slow (3.7 tok/s) and that's fine, because nothing routed to it is bulk or urgent. You steer it from the phone over SSH when traveling. Its bootstrap kit (Tailscale, Docker, Node, Claude Code CLI) is already running — adding a system means adding a skill directory and a cron entry, not provisioning anything new.

**The order of trust**: manual skill run → hook → schedule → subagent pipeline. Never automate a step you haven't run by hand and validated at least once. This single rule is most of what separates the systems in your corpus that shipped from the ones that stalled.

---

## 6. Risks & guardrails

**Over-automation.** The gravitational pull is toward agents quietly crossing the draft/send line — a staged post going live, a reminder that reads as pressure, a status advancing itself. Guardrail: the clm-0027 boundary is enforced *structurally* everywhere — separate folders/states with no agent-executable transition across the human gate; no send/submit/pay primitive is ever wired to a non-human-gated role. Trust bands may lower review *depth* over time (spot-check instead of full read); they never remove the gate, and any regression reverts to full review.

**T3 leakage.** The single worst failure available to this architecture: family, health, or financial content transiting a cloud model, a synced folder, or a drafting prompt. Guardrails: the device split is binding (T3 lives on the Cubi, which has no MCP connectors and no cloud routing path in any T3 skill file); Systems 7/8/9 have zero cloud escalation — if the local model isn't good enough, the fallback is "you draft it yourself with structural help," never "cloud just this once"; a separate adversarial redaction-checker pass runs before anything T3-derived is viewed off-Cubi; voice corpora and content pipelines structurally exclude `01_journal`/`99_private`, not just by policy.

**Authorial-voice integrity.** Academic prose is yours at the identity level (clm-0039) — no system here touches it, and the status machine hard-blocks submitted/published transitions from any state lacking a human-authorship checkpoint. Nonacademic content is delegable only because the voice-calibration loop plus your per-piece approval gate exist; disclosure wording and whether-to-disclose stay your call. Adjacent guard: no drafting skill anywhere may generate guru/movement/built-authority language (clm-0033) — the reviewer roles flag it for rejection.

**The uncorroborated-hypothesis guardrail (cross-system, absolute).** The cardiac-causation hypothesis remains yours, single-source, disconfirmation-pending (clm-5306). No system presents it as settled — the family drafting skills mechanically block causal-certainty language until reworded or explicitly overridden by you, and health-system outputs never export causal framings into family-facing artifacts.

**The capacity paradox — don't let system-building become the next overcommitment.** The deepest risk is recursive: a person with a multi-person workload spends his scarce hours building systems to relieve the workload, and the building itself becomes the new undeadlined dream project that starves. This is exactly how the 13-lane vault and the capture daemon died. Guardrails, all inherited from your own diagnostic: every increment is one or two sittings, deadline-anchored to a live use this month; no increment starts before the last one validates; weekly review passes are capped (~15–20 min per system that's running — sustained overrun = shrink scope); T3 systems are explicitly designed to get *quieter* as they succeed; and System 6's learning loop applies portfolio-wide — anything that never changes a decision gets pruned, not grown. The blueprint's success metric is not systems built. It is hours returned — to the book, the platform, the runway, and the one leg of the squeeze that can flip sign.

---

*Companion deliverables: `gap-analysis.md` (AS-IS), `capacital-needs.md` (CN-01..14), the nine specs in `systems/`, and the leverage-ranked roadmap embedded here as §4. Next per HANDOFF: the local HTML dashboard.*
