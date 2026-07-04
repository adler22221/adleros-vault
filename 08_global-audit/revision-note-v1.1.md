---
tags: [global-audit, agent-out]
date: 2026-07-04
source: "C:\Users\adler-standard\Documents\_AI agents\global-audit\01_methodology\memo\revision-note-v1.1.md"
---

# Revision Note — Methodology v1.0-draft → v1.1

**Date:** 2026-07-04 · **Status:** Gate 0 APPROVED (plan-mode review, with amendments)
**Purpose:** integrate Adler's Gate 0 feedback (RQ7–RQ9 research, adversarially verified) into the memo, codebook, and coding manual.

## Core changes

**(a) Perplexity prioritized.** gemini-perplexity → class F, full read of the subject's own turns. Fallback order if volume forces sampling: named spaces (Career coach → Work automation system → Cardio disease) → last 12 months → stratified remainder. Obsidian is the longitudinal backbone; complementarity doctrine added (memo §3): recent-self claims cite Perplexity-era evidence, trajectory claims cite Obsidian strata, divergence between them is espoused/enacted signal, never averaged away.

**(b) User-turns-only.** Encoded as `evidence_scope` in the record schema; new memo §4 step 3; manual Example 6 shows the separation and the uptake exception (your enactment of AI advice counts, with explicit attribution).

**(c) cld-leverage lens.** 10 CLD codes; loops need both links + polarity + ≥1 observed traversal (our own convention — the literature has none); archetypes only after loops pass; your "I am not a cybernetic machine" carried as the lens's standing applicability gate; Meadows levels 1–3 labeled aspirational.

**(d) simple-rules lens.** 6 RUL codes phrased in Argyris & Schön condition-action form — their espoused-theory/theory-in-use distinction is now the formal bridge to the audit's espoused/enacted framing (RUL-03); synthesis-phase only; ≥3 instances/≥2 contexts + near-miss + held-out-instance check.

**(e) Empathy map + VPC.** Output formats only (Phase 3/4), never lenses; every cell cites claims with confidence labels; empty cells stay empty; fit is a hypothesis with a mandatory validation gate; **no pains/gains codes added** — RQ9's deliverable (c) recommends synthesis-time derivation, so pains/gains are relabelings of existing JTBD/VMCL evidence.

## Later-approved amendments (2026-07-04 plan review; marked "(v1.1 amendment)" in the memo)

- **Obsidian full read:** 2ndbrain → class F including `01_journal` + `99_private` (Adler's explicit overrule); journals reclassified T3 → "T2-reflections" (full content, summaries, quotes ≤240 chars; third-party role-tagging still mandatory; journal quotes appear only in member-check materials, never vault-published without per-item OK).
- **Google Drive → S+:** census plus portfolio-assets extraction (achievement / date / type / evidence path / capital type).
- **New F-class source:** public-presence web audit of Adler Yang / 楊逸帆 / アドラー・ヨウ with disambiguation rules (exclude the 大紀元 reporter and the 北科大/通訊科技 engineering author).
- **Reliability (§6):** cross-vendor double-coding — Gemini 2.5 Flash-Lite vs Claude sonnet, haiku tie-breaker — directly mitigating bias-register row 7; α thresholds unchanged.
- **Privacy (§8):** model-routing classes on the training-ingestion boundary; original-IP content routes only to providers with verified no-training-on-inputs (unverified = Claude-only); see `scripts\summarize_router.py` and `01_methodology\training-policy-matrix.md`.

## Decisions ratified at Gate 0

1. simple-rules registered as a synthesis-phase template, not a sixth per-segment pass (RQ8).
2. CLD loops open only from SDA/RET triggers; single-traversal loops cap claims at C2 — audit's own convention (no literature standard exists).
3. Meadows level 1–3 recommendations labeled "aspirational," outside the confidence tiers.
4. No pains/gains codes — synthesis-time derivation per RQ9 (c); traceability tags on output templates instead.
5. RUL-06 revision proposals live outside claims.jsonl as recommendation objects, capped at Plausible.
6. Empathy map/VPC housed inside codebook.yaml as `output_templates` although RQ9 recommended separate schema files — softens the "codebook = Phase 2 only" boundary.
7. Perplexity sampling fallback order + the uptake-of-AI-advice exception (`mixed_with_ai_context`) as specified.

**Net:** 50 codes across 7 lenses (34 existing + 16 new: CLD-01..10, RUL-01..06).
