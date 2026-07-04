---
tags: [global-audit, agent-out]
date: 2026-07-04
source: "C:\Users\adler-standard\Documents\_AI agents\global-audit\01_methodology\codebook\coding-manual.md"
---

# Coding Manual — Worked Examples & Edge Cases

**Use:** read `codebook.yaml` first (unitization section before code lists). This manual shows the mechanical sequence — **segment → inclusion tests → code → cite** — on synthetic records calibrated to the real corpus. All examples are synthetic; none are real quotes.

---

## Example 1 — Zettel on educational dependency (note, T2, empirical stratum)

**Record** `obs-001204` (`obsidian-2ndbrain`, note, lang=en), two paragraphs:

> P1: "Educational dependency is not scaffolding. Scaffolding withers by design; dependency is scaffolding that persists after the learner could stand."
> P2: "Every time I design a workshop with a facilitator at the center, participants defer more in week 3 than week 1."

**Segmentation:** journal/long-form rule → one paragraph = one recording unit. Two units. No splits needed (each paragraph is one assertion-cluster).

**Unit 1 → DSRP-02.** Inclusion tests: two concepts named (dependency, scaffolding)? Yes. Difference asserted in subject's own move ("is not… persists after")? Yes. Exclusion check: not a pasted definition. → Emit:

```json
{"segment_id":"seg-a1b2c3d4","record_id":"obs-001204","code_id":"DSRP-02",
 "locator":"para 1","citation":"[src:obsidian-2ndbrain#obs-001204@para1]",
 "rationale":"Two categories named with subject's own boundary assertion (inclusion 1-2 met)","coder_model":"sonnet"}
```

**Unit 2 → DSRP-05.** Cause pole (facilitator-centered design) and effect pole (rising deference) both present; direction asserted ("every time… defer more"). Also test RET-01: fails — no N-of-M fraction, no comparison set defined; "every time" is exactly the unquantified phrasing RET-01 excludes. Flag the segment for the retroduction lens to *quantify later against workshop records*; do not code RET-01 now. **One unit, one code emitted; the temptation to co-code is resolved by the inclusion tests, not by intuition.**

---

## Example 2 — Calendar aggregate: Japan-trip clustering (event_agg, T1/T2, actual stratum)

**Record** `gcal-000087`: 24-month aggregate; `metrics`: months tagged JP-based (n=4) show seminar-type events 3.1×/week vs 0.9 baseline, board events 0.1 vs 1.2; windows listed.

**Segmentation:** T3/aggregate rule family → one aggregate row/window is the recording unit. Here the whole comparison row is one unit.

**→ SDA-01.** Inclusion tests: regime defined by named metrics *before* counting (seminar density, board-event rate — declared in `gcal_agg.py` config)? Yes. ≥3 recurrences with windows? Yes (4). Seasonal artifact considered? Note: JP months are not seasonally fixed (Mar, Jul, Oct, Feb) — noted in rationale. → Emit with `"citation":"[src:gcal#gcal-000087@row:jp-regime]"`, rationale: "Pre-declared 2-metric regime, 4 recurrences, seasonality checked (inclusion 1-3 met)."

No quotes needed — the citation resolves to metrics. **Ceiling note:** one signal type only, so any claim citing this segment stays ≤C2 until a second, independent signal type (e.g., a DSRP-07 perspective segment about Japan trips, or SDA-05 corroborating event) lands in the same windows (two-signal rule).

---

## Example 3 — Espoused essay vs enacted journal cadence (doc T2 + T3 aggregate; espoused/enacted conflict)

**Record A** `drv-000311` (fellowship essay, doc, T2): "Daily bilingual journaling grounds my research practice."
**Record B** `jrn-000002` (journal_stats aggregate, T3): entries/week by month, 24 months; median 2.1; no month ≥5.

**Record A → VMCL-03.** Recurrence marker ("daily")? Yes. Tie to longer aim ("grounds my research practice")? Yes. Schedulable? Yes. → Code VMCL-03, citation `[src:gdrive#drv-000311@para3]`, quote allowed (T2, ≤240 chars).

**Record B → RET-04.** The contradicted pattern is referenced (the espoused daily practice, via Record A's segment id); the counter-instance is specific and dateable (24-month cadence ≪ daily). → Code RET-04, citation `[src:journal#jrn-000002@metric:entries_per_week]`, **no quote — T3**.

**Rule applied:** code the espoused statement and the enacted counter-evidence **separately, at their own strata** (empirical vs actual); never average them into "journals sometimes." Emit both; the pair is flagged to the Phase-2 contradiction-hunter. The *gap itself* becomes claim material for retroduction (candidate mechanisms for why the espoused and enacted diverge) — at claim level, not coding level.

---

## Example 4 — Journal-cadence gap (T3 aggregate, actual stratum)

**Record** `jrn-000005` (journal_stats, T3): weekly entry counts show 5.2/wk (2025-01→2025-10), then 26 consecutive days with zero entries (2025-11-03→11-28), then 1.1/wk after.

**Segmentation:** one aggregate window = one unit. Three windows → the before/gap/after comparison is one candidate-transition unit.

**→ SDA-02.** Before/after windows named with quantified difference in ≥2 metrics? Only one metric (entries/week) → **inclusion fails on this record alone.** Consult census: `obs census` shows 06_agent-out output tripling in the same window — a second metric from a second record. Code SDA-02 on the *pair*, citing both: `[src:journal#jrn-000005@window:2025-11]` + cross-ref in rationale. Logging-practice check: was Obsidian replaced by another journaling tool that month? Noted as unresolved → `confidence_note: "logging-practice rival unchecked"`.

**T3 discipline demonstrated:** no journal content is read, quoted, or paraphrased; the entire code rests on counts. Any claim citing this segment must offer mechanism candidates via the retroduction loop — "stopped journaling" (empirical) is not yet "withdrew into production mode" (real).

---

## Example 5 — Mixed-language chat segment (chat_convo, T2)

**Record** `cld-000442` (claude-sessions, lang=mixed). One message: "また同じことをしてる — I keep rebuilding the same intake spreadsheet for every 面談 instead of fixing the template."

**Segmentation:** chat rule → one message = one unit.

**→ JTBD-03.** Specific situated friction (rebuilding intake spreadsheet per interview)? Yes. Nameable job (run interviews without setup overhead)? Yes, from context. → Code it. **Mixed-language handling:** quote preserved in original scripts (≤240 chars, no translation substituted); `rationale` written in English and may gloss ("また同じことをしてる = 'doing the same thing again' — recurrence marker strengthens the struggle reading"); the record's `lang: mixed` flows into the per-language reliability strata. Never code from a translation only — translation flattening is a named bias (memo §9, row 5).

---

## Example 6 — Perplexity conversation: user-turn/AI-turn separation (chat_convo, T2, evidence_scope)

**Record** `gpx-000107` (gemini-perplexity, chat_convo, lang=en, space "Career coach", `evidence_scope: user_turns_only`). Synthetic thread:

> **User turn 3:** "I keep saying yes to teaching gigs I don't want because refusing elders feels impossible."
> **AI turn 4:** [long boundary-setting advice, offers a refusal script]
> **User turn 5:** "Tried a version of that script with my uncle yesterday — first direct no in years."

- **Segmentation:** chat rule, one message = one unit — **but only user turns are recording units; AI turns are context units** (memo §3/§4; "AI responses do not reflect my real conditions").
- **User turn 3 → JTBD-03** (specific situated friction; job = protect capacity while honoring relationships) and **CLD-01 co-code eligible** ("because", polarity entailed). Cite `[src:gemini-perplexity#gpx-000107@msg:3]`.
- **AI turn 4 → never coded, never quoted as subject evidence.** If a coder emits a segment citing msg:4, the validator rejects it.
- **User turn 5 → uptake-of-advice exception:** the subject's *enactment* is actual-stratum evidence. Record flagged `evidence_scope: mixed_with_ai_context`; code VMCL-07 (outcome + adjustment) or JTBD-05; rationale must attribute: "script provenance AI turn 4 (context); evidence is the subject's own reported enactment, msg:5."

---

## Example 7 — CLD loop walk-through (recurring pattern, multi-record)

**Trigger:** SDA-01 segment (journal-cadence dips following gig-heavy weeks, 4 recurrences) — CLD investigation may open (activation gate met; cite the SDA segment).

- **Link 1:** note "Every translation gig I take collapses my journal cadence for two weeks after" → CLD-01, polarity − (explicit connective; delay language → CLD-05 candidate once loop confirmed).
- **Link 2:** note "when I stop journaling I lose track of my capacity limits and overcommit to the next gig" → CLD-01, two links (journaling↓ → capacity-awareness↓ (+/−? state per wording); overcommitment↑ → gigs↑).
- **Closure test:** every link separately evidenced? Yes (3 CLD-01 segments). Polarity product positive → reinforcing. Full traversal dated (2025-09 gig → 10 journal gap → 11 overcommitment note)? Yes, once → **CLD-03 coded, citing all link segments + the SDA trigger; claims capped C2 (single traversal).**
- **Archetype temptation:** "looks like Shifting the Burden" — no second (balancing) loop evidenced → **withhold CLD-06, log rejected-narrative-causation note.**
- **CLD-10:** level 6 (information flow — weekly capacity view makes gig-load visible pre-commitment); mechanism sentence states why level-12 reminder tweak was rejected (leaves loop gain unchanged). Descriptive only; the recommendation itself is synthesis-stage.

---

## Edge-case rules

**E1 — Mixed-language segment.** Unit boundaries follow the trace-type rule regardless of language switches; never split at a language boundary. Quote in original script(s); English rationale; gloss allowed inside the rationale, never in the quote. If a code's inclusion test hinges on a nuance the coder model is unsure of in ZH/JA, emit no code and log `lang-uncertainty` — these logs feed the per-language reliability review.

**E2 — Espoused-vs-enacted conflict inside one record** (e.g., a note stating a daily practice and, two paragraphs later, admitting it lapsed). Segment normally (two units), code each at its own stratum (VMCL-03 on the espoused; VMCL-08 or RET-04 on the admission), and flag the record id to the contradiction-hunter. Never suppress either side, never harmonize into a middle reading — the divergence is the highest-value implicit-layer signal (plan; memo §1).

**E3 — T3 aggregate coding.** Quotes are impossible by construction (validator hard-fails non-empty quotes on T3). Citations point at metric keys or aggregate rows (`@metric:…`, `@row:…`, `@window:…`). Rationales reference statistics only ("median 2.1/wk vs espoused daily") and must not reconstruct content ("the entries suggest distress" is forbidden — that inference has no admissible evidence). If a T3-based code seems to need content to justify, the code does not apply.

**E4 — When NOT to code.** No-code is the default outcome, not a failure. Do not code when: (a) any inclusion criterion is unmet — close doesn't count; (b) the pattern is coder-projected rather than present in the subject's language (DSRP co-implication gate); (c) the span is below the recording unit (a phrase inside a paragraph — code the unit or nothing); (d) the record is bare structural metadata (folder names, event titles without content); (e) the only reading requires knowledge from *outside* the unit + context unit (e.g., remembering another record — cite that record separately instead). A record read and left uncoded needs no log entry; a *near-miss* the coder judged genuinely borderline gets a one-line `borderline` log entry so codebook revision cycles can find it.

**E5 — Filename/title entities are evidence, not fabrication** (from a Gate-1 member-check: a contract filed as `雜學校國發會國際論壇協議書.docx` names the National Development Council only in its filename; the body's two signatories are ZA Share and the subject's entity. The NDC is the forum's real government sponsor — deleting it as "unsupported by the body" would erase genuine symbolic capital). Rule: filename/title is a first-class datum. Tag every entity with its evidence basis in the rationale — *body-stated* (full confidence), *title/filename-only* (entity real, **role inferred → route to member-check**), or *coder-inferred-from-neither* (the only real fabrication → do not code). Never drop a title-only entity; downgrade its role certainty instead. This matters disproportionately in this corpus because its files are labelled precisely and trilingually, so institutional context frequently lives in the label, not the prose.

---

*Reliability anchor: Examples 1–5 are the fixed calibration set for drift checks (codebook `reliability_protocol.drift_check`); Examples 6–7 calibrate the v1.1 additions (evidence_scope, CLD). Revisions to this manual are codebook amendments and increment the codebook version.*
