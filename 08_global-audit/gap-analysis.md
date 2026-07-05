---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Gap Analysis — AS-IS: existing adlerOS components vs the 14 capacital needs

**Phase 4, deliverable 1.** Inputs: `04_persona/persona-v3.1.md` (member-checked), `05_blueprint/capacital-needs.md` (CN-01..14), `02_extracts/adleros-systems/ai-collab-profile.json` + `summary.md`, `02_extracts/filesystem-misc/`, `02_extracts/obsidian-2ndbrain/summary.md`, `02_extracts/zotero/zotero_agg.json`, `04_persona/claims/claims.jsonl`, `00_admin/HANDOFF.md` (Cubi verdict).
**Privacy**: T3 discipline — third parties role-tagged, no names, no medical/financial specifics, zero verbatim on clm-53xx material.

---

## 1. Component inventory — what exists today

17 components: 12 from the Wave-B AI-collab profile + 5 surfaced by adjacent extracts.

| # | Component | Intended function | Maturity | Evidence |
|---|---|---|---|---|
| 1 | adlerOS 13-lane vault architecture (00_horizons..98_templates; entropy firewall; CANON vs AI-write lanes) | Replace legacy 2ndbrain vault; human-canon-only-as-source enforced by hooks | **Stalled** | vault-staging dated 2026-06-23 marked "not yet in the vault"; Stage A/B migration not executed; no later file confirms restructure (`P:\adlerOS\ops\vault-map.md`) |
| 2 | adlerOS delegation/routing conventions (T0–T4 tiers; free-tier→Sonnet→Opus-reserved→local routing) | Standardize delegation risk-tiers and token-frugal model routing across all automation | **Working as spec / stalled as enforcement** | Policy consistent across 3 independent locations; implemented only in fellowship-applications (working token_tracker.py); no enforcement script inside adlerOS proper (`P:\adlerOS\ops\conventions.md`) |
| 3 | Cubi host + bootstrap kit (Tailscale, Docker, Node, Claude Code CLI) | Always-on agent host for a future 24/7 delegation daemon + capture pipeline | **Working (bootstrap + live mobile host) / stalled (daemon payload)** | Idempotent scripts complete; host now runs Claude Code as the audit's mobile continuation seat; daemon/routing-layer/capture payload not started. Benchmark verdict: local Qwythos-9B 3.7 tok/s — private/offline agent + overnight batch only, **not bulk** (`00_admin/HANDOFF.md`) |
| 4 | Capture pipeline (Telegram bot → faster-whisper → OCR → 05_collab-inbox) | Frictionless mobile/voice capture, local-first for sensitive material | **Abandoned / not started (design only)** | No script, config, or log anywhere; gated on the Cubi daemon that never started (`skill-map.md`, `migration-runbook.md`) |
| 5 | GCal→Obsidian read-only ICS integration | Calendar visibility beside vault time-blocks without dual source of truth | **Working (read direction) / not-started (reverse push)** | Simple completable config, no blockers; reverse push explicitly optional (`gcal-ics-setup.md`) |
| 6 | migrate_backfill_created.py | Additive-only frontmatter backfill for calendar-traceability | **Working script; --apply unconfirmed** | Complete 89-line dry-run-default script; no execution log found |
| 7 | research-hub (pip-installable CLI/MCP package) | Zotero + Obsidian + NotebookLM as an AI-operable research workspace | **Working — most productized system in corpus** | Own repo, CI/publish Actions, CHANGELOG, versioned audit docs to v0.37, 8 sub-skills |
| 8 | full-research-workflow / ThesisRevision governance (status machine; 3-notebook NotebookLM privacy gate; claude-mem 3-layer memory; mobile 3-channel protocol) | Govern multi-submission academic workspace | **Working — most lived-in system** | Dated policy revisions 2026-05-02..26; manifest shows iterative committee-feedback triage; mobile protocol used on a real dated trip |
| 9 | fellowship-applications 5-agent pipeline + model router (orchestrator/researcher/writer/reviewer/editor; MODEL_SWITCHING.md) | End-to-end application drafting with committee-simulation scoring, iterate to score≥7 | **Working — ≥1 real completed run** | PIPELINE_COMPLETE.md + draft v1–v4 + reviews + evidence-register on disk for a named 2026 fellowship |
| 10 | 115 licensing-exam spaced-repetition system (Anki + 3-mode audio + cram sheet from one source markdown) | 9-day structured retake prep under hard deadline | **Working — completed on schedule** | Dated 2026-06-22..07-01 schedule; finished decks and full audio tree on disk; cross-corroborated by 2024–25 training-certificate filenames (fsm) |
| 11 | translate_pptx.py localization pipeline | zh-TW→ja deck translation with glossary + screenshot QA loop | **Working — completed, one full revision cycle** | v1/v2 outputs + two generations of QA screenshots |
| 12 | g0v Summit 2026 talk design-prompt pipeline | Structured prompt template driving AI slide generation for a public talk | **Working artifact; outcome unconfirmed** | Complete 14–16-slide spec; no generated deck found |
| 13 | zenrich Zotero enrichment service | Bulk metadata enrichment/backfill over the Zotero library with review-queue tagging | **Working — exercised at scale** | ~600 items carry zenrich:* tags (old-20pct 364, backfill-social 174, backfill-det 37, needs-review 21) in `zotero_agg.json` |
| 14 | ebook_pipeline/ingest.py (Kindle→Zotero) | DeDRM/EPUB/metadata ingest feeding the research library | **Working — exercised** | Dozen+ ja-language titles processed through calibre_lib/staging (`P:\_automation`) |
| 15 | 2ndbrain legacy vault + GTD layer + live agent lanes | Daily knowledge/task substrate; 05_collab-inbox / 06_agent-out lanes already exist in the live vault | **Working-legacy (aging)** | 3,002 notes, 2020-01..2026-07, peak 2026-06 (408); #_gtd_0_inbox 356 uses; 06_agent-out holds 4 large synthesis notes — the entropy-firewall write lanes exist without the Stage-B migration |
| 16 | AI fit-evaluation / career-coaching practice (long-running third-person coaching thread, 34 turns Feb–Jul 2026) | Holistic fit scoring of fellowships/jobs against his 2026–2030 priorities + health constraint | **Working practice — not infrastructure** | ados-000012; matches confirmed rule clm-0010 ("always use AI to first evaluate the fit") |
| 17 | global-audit persona/claims pipeline (extractors, records.jsonl, claims.jsonl, corroboration passes, summarize_router.py) | Evidence-chained self-audit: extraction → coding → triangulation → member-check | **Working — just exercised** | This workspace; ~658 coded segments, 64 claims, v3.1 corroboration pass completed 2026-07 |

---

## 2. Coverage matrix — 14 needs × existing components

Verdicts: **served** / **partial** / **unserved** / **served-but-abandoned**.

| CN | Need | Covering components (#) | Verdict | Diagnostic |
|---|---|---|---|---|
| CN-01 | Admin/coordination for light-but-aligned allies | none — skill-map has no coordination commands; two paid hires failed historically | **UNSERVED** | The R1-loop leverage point has zero tooling. Never even design-drafted — his coordination attempts were human hires, both failed |
| CN-02 | Scaled/public outreach | 12 (one talk), 11 (one localization); historical reach designs (2021 audio/podcast, trilingual blog, author site, video funnel) drafted, never sustained | **SERVED-BUT-ABANDONED** | Stall cause per his own account: capacity, not will — outreach is undeadlined "dream"-side work, plus the CN-03 quality block makes delegation impossible, so channels default to silence |
| CN-03 | Public-facing content at his authorship bar | 9 (writer/reviewer/editor loop proves the draft-review-iterate machinery — wrong domain) | **PARTIAL (blocked-pending-quality)** | No voice-calibration pipeline exists; drafts fail his bar so the clm-0039 boundary defaults everything to his own scarce hours |
| CN-04 | Opportunity fit-evaluation | 9 (committee-simulation scoring, real run), 16 (standing practice), rule clm-0010 | **SERVED** (informal) | The one proven, habitual AI-delegation success. Reactive-only; formalized rubric + proactive scanning are the extension, not an invention |
| CN-05 | Team-sized capacity (umbrella) | 1 (stalled), 2 (spec-only), 3 (scoped host), 4 (abandoned), 933-session agent layer | **PARTIAL** | Task-level augmentation works daily; team-level (standing role agents owning domains) exists only as the stalled 13-lane + daemon design. The flagship build is the corpus's least-executed system |
| CN-06 | Research & publication throughput | 7, 8, 13, 14, 17 (+NotebookLM gate inside 8) | **SERVED** (densest coverage) | Best-tooled domain in his life; residual constraint is his capacity/voice on the academic side, which is policy-protected (clm-0039), not a tooling gap |
| CN-07 | Scholarly-community presence at low cost | none — research-hub digests literature, not communities | **UNSERVED** | Presence faded ~2024 rationally under bread-vs-dream; decay is silent and untracked |
| CN-08 | Funder-alignment scouting beyond Taiwan | 9, 16 (evaluation side only) | **PARTIAL** | Judging what arrives is proven; the pipeline that *finds* aligned funders does not exist — runway risk is live (clm-0017) |
| CN-09 | Bounded bread/income pipelines | 10 (licensing bread shipped under deadline), 11 (completed service-shaped deliverable); revenue designs (tiers, funnel) drafted-stalled | **PARTIAL** (revenue designs abandoned) | Proof he ships bread when deadlined; standing low-capacity revenue pipelines never got a deadline, so they starved — same stall signature as CN-02 |
| CN-10 | DSPS schedule defense | 5 (calendar visibility), 1/skill-map's logical-day /today,/closeday (planned only) | **PARTIAL** | Visibility without defense: nothing negotiates, deflects, or async-shifts morning demands |
| CN-11 | Archival corroboration & evidence work | 17, 7, 6 | **SERVED** | The v3.1 corroboration pass just ran on exactly this machinery; four member-check verification requests closed with it |
| CN-12 | Whole-life value-alignment (meta) | downstream of all | **UNSERVED as a build — by design** | Outcome metric, not a system; tracks whether CN-01..10 relieve the named constraints |
| CN-13 | Relationship management (incl. the [partner]-runway plan) | none as system; manual practice is strong (drafted-and-revised repair messages, redacted role-labeled counselor briefings — rules-in-use clm-5308/5312); 4 (abandoned) was the intended local-first sensitive-capture route | **UNSERVED** (systematize an existing manual pattern) | Everything runs on his scarcest resource — capacity in crisis moments; the runway goal has no tracked/recomputed plan and is unwired to CN-08/09 |
| CN-14 | Family-conflict resolution (two-family care/finance; mediated re-entry) | none | **UNSERVED** | Mediation assets sit unused; the feared-scenario contingency has no plan, only dread; every collision is fresh manual drafting |

**Tally: 3 served (CN-04, 06, 11) · 5 partial (CN-03, 05, 08, 09, 10) · 1 served-but-abandoned (CN-02) · 5 unserved (CN-01, 07, 12*, 13, 14)** — *CN-12 indirect by design.

### Why the abandoned/stalled band exists (diagnostic gold)

The Wave-B extraction's load-bearing observation: **maturity correlates with scope narrowness and deadline pressure, not design sophistication.** The most elaborately designed system (adlerOS proper: 13-lane vault, daemon, capture pipeline) is the least executed; the smallest deadline-bound builds (exam prep, one translation, one fellowship run) all finished. This is not a discipline failure — it is his own member-checked bread-vs-dream economy (clm-0035/0010): under fixed solo capacity, undeadlined infrastructure is "dream"-side and structurally starves. The two attempts to buy capacity (paid hires) both failed. Implication for every Phase-4 build: (a) narrow scope, (b) a deadline or immediate load-bearing role inside a live "bread" workflow, (c) additive to a working system — never a new platform that must be finished before it pays.

---

## 3. The reusable foundation — build ON, never replace

1. **The model router / tiering discipline** (fellowship-applications MODEL_SWITCHING.md + token_tracker.py; same philosophy independently in adlerOS conventions and research-hub delegate-skills). Free-tier-first, Opus/Fable-reserved, local-last. Every new system inherits this router rather than re-deciding cost policy.
2. **research-hub + full-research-workflow governance** (components 7, 8). The status machine (ai-draft→…→published with forbidden transitions), the 3-notebook NotebookLM privacy gate, state-lives-in-files mobile resilience, and claude-mem memory layers are proven governance primitives — reuse them verbatim for CN-01/02/03 artifacts.
3. **The zenrich pattern** (13): bulk batch enrichment + `needs-review` queue tags = the template for any high-volume/low-risk agent job (community digests CN-07, funder scans CN-08, content repurposing CN-02).
4. **The live agent lanes in the current vault** (15): 05_collab-inbox / 06_agent-out / 07_agent-synthesis already exist inside 2ndbrain. Phase-4 systems write there **now**, without waiting for the stalled Stage-B lane migration — the entropy firewall's write side is already real.
5. **The Cubi, scoped honestly** (3): private/offline agent for T3 material (CN-13/14 drafting support, sensitive chronology assembly) + overnight batch host — **not** bulk inference (3.7 tok/s verdict); bulk stays on cloud tiers per the router.
6. **The fit-evaluation practice** (16 + rule clm-0010): the seed of the whole partnership — formalize, don't invent (CN-04→CN-08).
7. **The evidence-register / open-questions QA pattern** (9) and **content-once-generate-many** (10): anti-hallucination and multi-format output patterns for CN-02/03.
8. **His standing rules-in-use as hard design constraints** (claims.jsonl): irreversible/identity-bearing actions reserved for him as use-case-dependent default (clm-0027); adversity→constructive artifact, never venting (clm-0029); build-not-buy is budget-forced — systems must be near-zero-cost to run (clm-0030); systems are prosthetics under his conscious direction and must surface blind spots, not hide them (clm-0034). Plus the capacital-needs register's constraints: academic authorship stays his voice; no mystical/cult reputation mechanics; the mission's sacred core is not monetized; **all CN-13/14 content strictly T3/local-only, role-tags only, and no system ever automates delivery of a relational message or deploys the uncorroborated health-causation hypothesis as a verdict**.

---

## 4. Honest capability gaps — where nothing exists

1. **CN-01 ally coordination** — the single highest-leverage hole (cuts R1 at its structural link) and the only explicitly-named need with literally zero artifacts: no meeting-minute→micro-task conversion, no follow-up cadence, no contribution tracking. His only past instrument was hiring humans, twice, both failed.
2. **CN-03→CN-02 outreach chain** — no voice-calibration pipeline anywhere in the corpus (the fellowship writer agents are the nearest machinery, wrong register); until it exists CN-02 stays abandoned-by-default and reach remains below the 2016 documentary a decade on.
3. **CN-13 relationship management** — the manual pattern is excellent (drafted repair, counselor briefings, runway intent) but zero tooling: no runway feasibility model that recomputes as career options move, no briefing-assembly template, no wiring to CN-08/09 income pipelines that must fund it. Requires the hard T3 privacy wall from day one.
4. **CN-14 family-conflict resolution** — no contingency plan for the feared incapacitation scenario, no care/finance budgeting scaffold for three parent-units on the ten-year horizon, no mediated re-entry sequencing despite unused mediation goodwill on the [partner]-family side.
5. **CN-07 community presence** — no digest/flagging layer; relationships decay silently while he is heads-down; entirely delegable at the light tier and untouched.

Secondary gaps inside partials: proactive funder discovery (CN-08), standing revenue pipelines with real deadlines (CN-09), active calendar defense vs DSPS-incompatible demands (CN-10), and the team-of-role-agents layer (CN-05) — the last to be grown *out of* shipped narrow systems, not built first as a platform (per §2 diagnostic).

---

*Next deliverable: `capacital-blueprint.md` — per-need architectures on this foundation, honoring the §3 constraints and the §2 stall diagnostic (narrow, deadline-anchored, additive).* 
