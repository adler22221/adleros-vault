---
tags: [global-audit, agent-out]
date: 2026-07-04
source: "01_methodology/codebook/codebook.yaml"
---


# Codebook Summary (v1.1.1)

Human-readable digest for Gate 0 review. The executable source of truth is `codebook.yaml`.


## DSRP (Distinctions, Systems, Relationships, Perspectives) (`dsrp`)

**Sees:** The subject's thinking structure in his own language: boundary-drawing, part-whole framing, asserted causal links, marked vantage points.
**Blind to:** Temporal dynamics, enacted behavior, motive; anything not textually present.
**Provenance:** Borrowed heuristic, not a validated psychometric instrument; no published inter-rater coding manual exists (RQ3 Findings 1-3). Hard gate: the co-implication pair (both poles) must be present or unambiguously inferable in the subject's own language, never projected by the coder.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `DSRP-01` | Self/role distinction | Subject names what he, a role, or his org/project IS by contrast to what it is NOT (identity/other boundary applied to self-adjacent entities). | empirical | 2 |
| `DSRP-02` | Conceptual distinction / boundary revision | Subject draws, sharpens, or redraws a boundary between two concepts or categories in his own thinking. | empirical | 2 |
| `DSRP-03` | Part-whole composition | An entity is framed as a whole composed of identified parts. | empirical | 2 |
| `DSRP-04` | Nesting / membership framing | A focal entity is framed as a part of a larger named whole. | empirical | 2 |
| `DSRP-05` | Causal / feedback relationship (asserted) | Subject asserts a directional or feedback connection between two named entities or events. | empirical | 2 |
| `DSRP-06` | Co-variation relationship (asserted, non-directional) | Subject asserts that two things move together, without claiming direction. | empirical | 2 |
| `DSRP-07` | Perspective marking | Subject marks whose viewpoint is operating and what it foregrounds, against at least an implicit alternative vantage. | empirical | 2 |
| `DSRP-08` | Perspective shift / reframe | Subject re-describes the same referent from a second vantage and marks the change. | empirical | 2 |

## VMCL (Vision, Mission, Capacity, Learning) (`vmcl`)

**Sees:** Goal architecture: end-states, recurring practices, resource states/trade-offs, feedback loops. Direct scaffold for the nine capacital systems.
**Blind to:** Whether espoused visions are enacted (needs cross-lens triangulation); latent motives.
**Provenance:** NO VALIDATED IMPORT: no peer-reviewed operationalization of VMCL as a qualitative coding instrument exists (RQ3 Finding 5, corrected). First-of-kind n=1 adaptation; reliability must be computed, not inherited.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `VMCL-01` | Espoused vision (end-state) | A desired future end-state framed as a destination, not an action. | empirical | 2 |
| `VMCL-02` | Vision revision / conflict | Two competing end-states are named, or an end-state is explicitly revised or abandoned. | empirical | 2 |
| `VMCL-03` | Mission practice (recurring action) | A recurring practice, routine, or repeated commitment in service of a longer-term aim. | empirical | 2 |
| `VMCL-04` | Mission-vision linkage | An explicit asserted tie between a recurring practice and an end-state ('I do X so that Y'). | empirical | 2 |
| `VMCL-05` | Capacity state report | A report of availability or depletion of time, energy, attention, money, health, or social support, bearing on ability to sustain action. | empirical | 2 |
| `VMCL-06` | Capacity allocation / trade-off decision | An explicit decision or dilemma allocating a scarce resource between named demands. | empirical | 2 |
| `VMCL-07` | Learning loop (closed) | Retrospection on an outcome PLUS a stated resulting adjustment to vision, mission, or capacity allocation. | actual | 2 |
| `VMCL-08` | Reflection without adjustment (open loop) | Retrospective evaluation of an outcome with no adjustment made - the learning loop left open. AUDIT EXTENSION: derived from RQ3's exclusion boundary ('that is reflection, not yet Learning'); feeds espoused-vs-enacted gap analysis. | actual | 3 |

## System-dynamics / attractor evidence (`sd-attractors`)

**Sees:** Temporal regimes, regime shifts, early-warning signals, perturbation-recovery in dense time series (calendar, health, finance, journaling cadence).
**Blind to:** Meaning and content; unreliable on sparse or irregular sampling.
**Provenance:** Exploratory import from ecology/physiology (RQ3 Findings 6-11). Molenaar non-ergodicity: no population thresholds may be imported. Two independent signal types required before 'regime/attractor' language; 'attractor' is a structured metaphor, never a claimed mathematical object.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `SDA-01` | Recurring regime candidate | A recognizable mode/configuration of behavior that recurs across the record (e.g., trip-clustered months, deep-work regimes). | actual | 3 |
| `SDA-02` | Regime-shift candidate | A candidate transition between behavioral modes, with quantified before/after difference. | actual | 2 |
| `SDA-03` | Early-warning signal (critical slowing down) | Rising lag-1 autocorrelation and/or variance, or slowed recovery, computed on a pre-declared configuration. | actual | 2 |
| `SDA-04` | Perturbation-recovery episode | An identifiable, dateable disturbance followed by a measurable return toward baseline. | actual | 2 |
| `SDA-05` | Independent corroborating event | A dateable, verifiable real-world event near a statistically flagged transition window - the strongest single validation at n=1. | actual | 1 |
| `SDA-06` | Rejected-as-noise | A candidate signal examined and explicitly dismissed, with the rival (artifact/seasonal/logging-change) explanation named. | actual | 1 |

## Critical-realist retroduction (C-M-O) (`retroduction`)

**Sees:** Demi-regularities, candidate generative mechanisms, contextual conditions, counter-instances. The only lens licensed to feed real-stratum claims.
**Blind to:** Underdetermination is permanent: a mechanism is only best-of-rivals-generated, never proven (RQ2 Finding 10).
**Provenance:** Fletcher flexible-deductive coding + Danermark six moments (RQ2 Findings 5, 8). CR applied to digital traces has no direct precedent (RQ2 Finding 9) - this audit's own adaptation.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `RET-01` | Demi-regularity (contrastive) | A partial pattern stated contrastively: 'in N of M instances, X rather than Y', with the comparison set defined. | actual | 2 |
| `RET-02` | Candidate mechanism (real-stratum) | A named disposition, structure, or mechanism proposed as generative of a coded demi-regularity. The M in C-M-O. | real | 3 |
| `RET-03` | Contextual condition | A context that enables, triggers, or suppresses a candidate mechanism. The C in C-M-O. | actual | 2 |
| `RET-04` | Counter-instance | A specific, dated instance contradicting a coded demi-regularity or a mechanism's prediction. | actual | 1 |
| `RET-05` | Discriminating implication (retrodiction check) | A checkable implication of one candidate mechanism that would NOT hold under a named rival, with the check outcome recorded. | real | 1 |
| `RET-06` | C-M-O observation anchor | An observed outcome explicitly tied into a context-mechanism pair, forming a logged dyad/triad. The O in C-M-O. | empirical | 1 |

## Jobs-to-be-Done + thick data (`jtbd-thickdata`)

**Sees:** Jobs (progress sought in a circumstance), outcome metrics, struggles, workarounds, hire/fire switch moments (four forces: push/pull/anxiety/habit).
**Blind to:** Hindsight bias and narrative smoothing on retrospective motive.
**Provenance:** Christensen/Ulwick/Moesta lineage (RQ1 Finding 9). Self-applied JTBD has NO located precedent - this audit's own convention. Annotations flagged same-day vs reconstructed; elapsed time switch-to-annotation logged as a confidence variable.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `JTBD-01` | Job statement | Progress sought in a circumstance, in when-I-want-so-that form, explicit or fully recoverable from the unit plus context. | empirical | 2 |
| `JTBD-02` | Desired outcome metric | A success criterion with direction and measure, attached to a job (ODI-style). | empirical | 1 |
| `JTBD-03` | Struggle moment | A specific, dated friction with current means while pursuing a nameable job (the push force). | empirical | 2 |
| `JTBD-04` | Workaround | An improvised, non-designed compensating behavior standing in for a missing capability, recurring across the record. | actual | 2 |
| `JTBD-05` | Hire moment (switch: adoption) | A dateable adoption of a tool, practice, service, or collaborator for a job; four forces (push/pull/anxiety/habit) recorded where recoverable. | actual | 1 |
| `JTBD-06` | Fire moment (switch: abandonment) | A dateable abandonment/discontinuation of a tool or practice, with cessation visible in the traces. | actual | 1 |

## Causal-loop + leverage points (Meadows / Forrester / Senge) (`cld-leverage`)

**Sees:** Causal-structural explanations of recurring patterns: evidenced links with polarity, closed reinforcing/balancing loops, delays, archetype matches, Meadows-level leverage candidates for shifting limiting loops relative to stated ideal states.
**Blind to:** One-off events; anything without corpus repetition; meaning outside causal structure. APPLICABILITY GATE (subject's own condition): the subject is not a cybernetic machine - a single-episode narrative cause remains the default rival unless the traversal criteria are met (RQ7 Findings 9, Deliverable 2).
**Provenance:** Text-based CLD construction per Kim & Andersen 2012 / Eker & Zimmermann 2016 / Newberry & Carhart 2024; archetypes per Senge (co-developed with Goodman/Kiefer/Kemeny); hierarchy per Meadows 1999 (self-labeled 'tentative...slithery'). NO published minimum-evidence standard for asserting a loop and NO n=1 personal-trace precedent exist (RQ7 Findings 4, 9) - the both-links + stated-polarity + >=1-observed-traversal rule is this audit's own convention. Loops feed retroduction as mechanism candidates; they never bypass the >=2-rival gate.


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `CLD-01` | Causal link, explicit polarity | Subject links two named variables/states with an explicit causal connective; polarity (same-direction + / opposite -) stated or directly entailed by wording. | empirical | 2 |
| `CLD-02` | Causal link, implicit polarity | Two variables co-occur in fixed temporal order across >=2 separate corpus instances; directionality supplied by the subject or a documented rule, not coder inference alone. | actual | 2 |
| `CLD-03` | Reinforcing-loop candidate (R) | >=2 evidenced links (CLD-01/02) form a closed chain returning to the starting variable; polarity product positive; chain instantiated from text at least once. | actual | 2 |
| `CLD-04` | Balancing-loop candidate (B) | Same as CLD-03 but the polarity product around the closed chain is negative. | actual | 2 |
| `CLD-05` | Delay marker | A link in a confirmed loop has a dated/orderable gap between cause-mention and effect-mention, long enough that omitting it would change predicted behavior. | actual | 1 |
| `CLD-06` | Archetype match: Shifting the Burden | A confirmed quick-fix reinforcing loop (CLD-03) coexists with a confirmed or partially-evidenced root-cause balancing loop (CLD-04) it undercuts or delays; loops share >=1 variable. | actual | 2 |
| `CLD-07` | Archetype match: Limits to Growth/Success | A confirmed growth-driving CLD-03 is followed by a confirmed constraint-driven CLD-04 sharing a variable, with observable flattening/reversal of the growth variable in the trace. | actual | 2 |
| `CLD-08` | Archetype match: Escalation | Two confirmed reinforcing loops coupled such that each loop's key variable is a documented input to the other's driving variable - mutual, not one-directional. | actual | 2 |
| `CLD-09` | Archetype match: Drifting/Eroding Goals | A confirmed CLD-04 where the setpoint variable itself (stated goal/standard), not just performance, shows a documented downward trend across >=2 time-separated instances. | actual | 2 |
| `CLD-10` | Leverage-point candidate | A confirmed loop (CLD-03/04) or delay (CLD-05) annotated with a Meadows level (1-12) at which an intervention is hypothesized to act, plus a one-line mechanism statement for why that level rather than a shallower one. | real | 1 |

## Simple rules / theories-in-use (Argyris & Schon, Sull & Eisenhardt, Eoyang, Cabrera) (`simple-rules`)

**Sees:** Recurring condition-action policies driving self-organization of the subject and the systems he forms/joins: rules-in-use, espoused rules, espoused-vs-in-use conflicts, enabling/limiting judgments, maintain/revise/retire proposals tied to desired emergence.
**Blind to:** Single instances however striking; motives beyond the stated governing-variable hypothesis; anything requiring a tidy motto the corpus does not repeat.
**Provenance:** Condition-action phrasing adapts Argyris & Schon's theory-in-use formula (1974) - the formal bridge to this audit's espoused/enacted framing (RUL-03 is its named instrument). Rule-type awareness: Sull & Eisenhardt 2012/2015. Emergence framing: Cabrera CAS + Eoyang CDE (Eoyang criteria retrieved via secondary sources only - moderate-confidence provenance, RQ8 Findings 3-4). n=1 retrospective trace detection has NO published precedent; the >=3-instances/>=2-contexts floor and held-out-instance check are this audit's own conventions (RQ8 Finding 8).


| Code | Label | Definition | Stratum | Min evidence |
|---|---|---|---|---|
| `RUL-01` | Candidate rule-in-use | A recurring condition-action pattern visible across >=3 independent trace instances spanning >=2 distinct contexts, never stated by the subject anywhere in the corpus. Phrased per the Argyris & Schon template: in situation S, when [trigger], the subject [does A] - apparently to [C], assuming [a1..an]. | actual | 3 |
| `RUL-02` | Espoused rule | The subject explicitly states, in his own words, a rule/principle he claims governs a class of decisions. Recorded verbatim first, then translated into the condition-action template side by side so translation distortion stays visible. | empirical | 1 |
| `RUL-03` | Rule conflict, espoused-vs-in-use | A paired RUL-01 and RUL-02 on the SAME behavioral domain where the in-use rule contradicts or systematically narrows/loosens the espoused rule. The audit's most direct named instrument for the espoused/enacted gap (Argyris & Schon bridge). | actual | 2 |
| `RUL-04` | Enabling rule | A RUL-01/02 rule judged, with a stated one-sentence mechanism, to expand the subject's or his system's adaptive range (more workable responses, lower switching cost, or sd-attractors-corroborated recovery from perturbation). | real | 2 |
| `RUL-05` | Limiting rule | A RUL-01/02 rule judged, with a stated one-sentence mechanism, to narrow adaptive range (forecloses a response category regardless of context, or correlates with repeated lock-in/non-recovery). | real | 2 |
| `RUL-06` | Rule-revision candidate (maintain/revise/retire) | A RUL-04/05 judgment plus a drafted alternative condition-action rule stating the desired emergence it should produce. PRESCRIPTIVE OUTPUT: never enters claims.jsonl as a descriptive claim; logged as a recommendation object, capped at Plausible until a follow-up check shows the revision was tried. | real | 1 |

## Confidence scale

- **C1**: {'name': 'speculative', 'definition': "Coded but below minimum evidence, or only one candidate mechanism generated (loop step-4 fails), or refutation pass not run. RQ2 'Speculative' floor. Never enters the persona."}
- **C2**: {'name': 'plausible', 'definition': "Minimum evidence counts met but from a single source or one clustered period; rivals generated but not eliminated. Maps to RQ2/RQ6 'Plausible' (pre-elimination)."}
- **C3**: {'name': 'supported', 'definition': "Minimum evidence met across >=2 distinct sources; demi-regularity stated contrastively; for real-stratum content, loop steps 1-6 complete with rivals down-weighted. Persona-admissible for empirical/actual strata. Also the CAP for claims that survived refutation only in weakened form (boundary condition added / member-check 'Nuance') and for claims resting solely on tentative-reliability codes."}
- **C4**: {'name': 'corroborated_survived_refutation', 'definition': "C3 plus completed refutation pass (devil's advocate, red-team rival, minimum counter-searches) with verdict 'survived'; disconfirmation_status completed_supported. Maps to RQ2/RQ6 'Confirmed'."}
- **C5**: {'name': 'member_checked', 'definition': "C4 plus member-check response 'Confirm' recorded in Phase 3. 'Deny' withdraws or demotes and is itself recorded as data; 'Nuance' returns the claim for rewording, capped at C3."}
- **second_axis_note**: Every reported claim carries an evidence-base label alongside its C rating (RQ6 two-axis rule): Thick = >=3 independent trace items across >=2 periods/platforms; Moderate = 2 items or single-period clustering; Thin = 1 item or heavy inference. Derived from evidence[] and sources_distinct_count; reported in prose (claim.schema.json intentionally does not store it).

## Key rules

- Citation format: `{'pattern': '[src:<source_id>#<doc_ref>@<locator>]', 'rules': ["source_id must be one of record.schema.json's 16-value enum.", "doc_ref is the record's doc_ref (absolute path, URL, or thread/conversation id).", 'locator identifies the recording unit (line range, message index, paragraph n, aggregate row/window). Required whenever the record is larger than the segment.', 'T3 records: locator points to an aggregate row or metric key, never to raw content; the citation resolves to statistics, not text.', 'Every quote supporting a C3+ claim must pass deterministic exact-string verification by local script (whitespace/punctuation-normalized); fabrication tolerance is 0%.']}`
- Persona admission: {'min_confidence': 'C3', 'implicit_claims': 'cr_stratum: real requires disconfirmation_status in [completed_supported, completed_weakened] before admission (plan invariant; claim.schema.json).', 'evidence_chain': 'Every persona statement carries resolvable claim_ids; every claim resolves to segment_ids; every segment resolves to a record and locator. No chain, no admission.', 'falsifiability': 'Barnum statements banned; each statement must be falsifiable against the corpus and cite specific dated instances (RQ1 Finding 1).', 'time_validity': 'A statement may not assert beyond its evidence period; historical evidence supports historical claims only.', 'member_check': 'All C3+ claims enter the Phase 3 member-check questionnaire; a Deny is sufficient to pull a claim and is recorded as data (denial-as-data rule); contradicting enacted evidence is reported alongside the denial, at most C3, never as a validated implicit claim.', 'privacy': 'Claims derived from T3 sources cite aggregates only; no quotes exist to cite (validator-enforced). Third-party role tags are preserved verbatim in persona text; real third-party names never appear.'}
- Disconfirmation: min counter-searches 2, verdicts {'survived': 'Claim withstands counter-case, rivals, and counter-searches -> disconfirmation_status: completed_supported; eligible C4.', 'weakened': 'A disconfirming instance or live rival absorbed as an explicit boundary condition -> completed_weakened; claim reworded; capped at C3.', 'refuted': 'A disconfirming instance the claim cannot accommodate -> completed_refuted; claim WITHDRAWN and logged, never silently dropped or reasserted.'}
- Reliability: {'double_coding_sample': '100 segments (program plan), drawn stratified across lenses, languages (EN/ZH/JA), and trace types; PLUS 100% of instances of any code with <20 corpus instances (rare-code rule, RQ4 Finding 3).', 'coder_pairing': 'Independent haiku and sonnet passes, mutually blinded, fresh contexts, hypothesis-free prompts.', 'human_anchor': 'Adler double-codes a 30-unit gold subsample drawn from the 100 (RQ4 Deliverable A: >=30 units). Mandatory because all machine coders are Claude-family models; LLM-LLM agreement alone cannot rule out shared blind spots (RQ4 Finding 9).', 'metric': "Krippendorff's alpha (primary); raw percentage agreement reported alongside, never alone.", 'threshold': 0.7, 'threshold_provenance': "HONEST CAVEAT: 0.70 sits in the literature's 'tentative' band (0.667-0.80); the conventional 'reliable' bar is alpha >= 0.80 (RQ4 Finding 2). 0.70 is this program's cost-calibrated convention, NOT a literature-validated standard. Codes landing in [0.70, 0.80) are flagged tentative-reliability and claims resting solely on them are capped at C3.", 'escalation': ['Below threshold: freeze the code; no claims may rest on it.', 'Pull every disagreement (content review, not just the statistic) and classify: codebook ambiguity / model error / genuine borderline.', 'Ambiguity -> revise the entry (tighten criteria; add the disputed case as example or counter-example), re-code the subsample, recompute.', 'Model error (fabricated evidence, drift) -> re-run the pass with mitigations; never average over the error.', 'Maximum 2 revision cycles; persistent failure retires the code to exploratory status - claims demoted and labeled. Persistent unreliability is a finding about codability, not a process failure to engineer away.'], 'drift_check': 'Compare alpha on first vs last third of the coding timeline; a drop >0.10 triggers recalibration against the original worked examples (context rot + coding drift, RQ4 Findings 8, 10).', 'citation_fidelity': '100% of quotes behind C3+ claims exact-string verified locally; 15% random for others; program gate >=95% overall; one fabrication removes the claim and triggers a full re-check of that coding run (fabrication clusters by run and topic rarity, RQ4 Finding 7).', 'per_language_reporting': 'Alpha reported separately for EN, ZH, JA segments; a >0.15 gap between languages triggers a language-specific codebook review.'}

## Provenance caveats

{'provenance_caveats': ['DSRP and VMCL are borrowed heuristics adapted for this audit, not validated instruments; no third-party inter-rater statistics exist to inherit (RQ3 Findings 2, 5). This codebook computes its own.', "VMCL specifically has no peer-reviewed coding operationalization anywhere in the literature - this is a first-of-kind n=1 adaptation ('no validated import').", 'SDA codes are an exploratory import from ecology/physiology time-series methods to personal digital traces, a data type they have not been validated against (RQ3 Findings 8, 10). Two-signal-type minimum and hedged language are mandatory.', "CR retroduction applied to digital-trace data has no direct precedent (RQ2 Finding 9); the loop's exit criteria substitute for precedent.", "Self-applied JTBD has no located precedent (RQ1 Finding 9) - this audit's own convention.", "The unitization table extends Krippendorff/Campbell et al. to trace types (calendar, personal logs) no source covers - this audit's own extension (RQ3xRQ4).", "VMCL-08 is an audit-specific extension derived from RQ3's exclusion boundary, not part of any published VMCL scheme.", 'min_evidence_count values are program conventions calibrated to corpus density, not literature-derived thresholds.', "All privacy protections are procedural risk reduction; no formal guarantee exists at n=1 (RQ5). Outputs are 'risk-reduced', never 'anonymized'.", 'All coders are Claude-family models; every reliability statistic in this program carries the single-coder-family caveat (memo section 9, row 7). v1.1 amendment: double-coding is now cross-vendor (Gemini 2.5 Flash-Lite vs Claude sonnet, haiku tie-breaker), directly mitigating that row; the human gold subsample is retained.', "CLD/leverage-point methodology has no published minimum-evidence standard for loops and no n=1 personal-trace precedent (RQ7 Findings 4, 9); the both-links + polarity + >=1-traversal rule is this audit's own convention. Meadows' hierarchy is used as tentative ('slithery'), never as validated ranking.", "RUL simple-rules detection: no source tradition (Argyris & Schon, Sull & Eisenhardt, Eoyang, Cabrera) addresses n=1 retrospective trace detection; the >=3/>=2 floor, near-miss requirement and held-out check are this audit's own conventions (RQ8 Finding 8). Eoyang criteria rest on secondary-source provenance (moderate confidence, RQ8 Findings 3-4). DSRP-universality debate note: Midgley's 2008 critique and the 2023/24 co-authored response are overlapping-authorship positions, not critique-then-independent-vindication (RQ8 Finding 2).", "Empathy map and VPC are output formats, not lenses; self-as-customer adaptation is this audit's own convention (RQ9 Finding 10). Empathy-map provenance: Gray/XPLANE, Gamestorming 2010 (not '2009', not d.school/IDEO)."], 'coherence_checks': ['VMCL pyramid check: a Vision code with zero corpus-level Mission/Capacity/Learning support is an over-interpretation flag, not a persona fact (RQ3 Deliverable B rule 2).', 'DSRP co-implication gate: both poles present or unambiguously inferable, or the code does not apply (RQ3 Deliverable A rule 2).', 'SDA two-signal rule: no regime/shift claim above C2 on one signal type; require one quantitative + one qualitative/corroborating signal in the same window (RQ3 Deliverable C standing rule).', 'Emergent codes are permitted (Fletcher flexible-deductive stance, RQ2 Finding 8) but must be proposed as codebook amendments with a priori/emergent provenance logged - never applied ad hoc mid-pass.', "CLD archetype gate: an archetype tag (CLD-06..09) may only be applied after the underlying loop(s) independently pass the traversal criteria; resemblance to an archetype's surface story is never sufficient. Every resisted tag is logged as a rejected-narrative-causation note (RQ7 Deliverable 2, Implication 9).", 'CLD applicability gate: loop candidates open only from SDA/RET triggers; the subject is not a cybernetic machine - single-episode narrative rivals stay live unless traversal criteria are met.', 'RUL held-out-instance check: before any RUL-01 is finalized, one instance not used to construct the rule must be predicted correctly by it (post-hoc-smoothing mitigation, RQ8 Deliverable A).']}