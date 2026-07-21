---
aliases: ["AI Research Workflow Blueprint", "Workflow Architecture Blueprint"]
type: concept
project: workflow-infrastructure
status: ai-draft
topic: [workflow-architecture, meta, portable-blueprint]
source-notes: [zotero_workflow, feedback_retrieval_cascade, shadow_library_protocol, feedback_factcheck_protocol, feedback_t0_before_attack, source-of-truth-tiers, session_persistence_strategy, pcloud_p_drive_write_reverts, reference_claude_mem_instability, nlm_notebook_registry_2026_05_05]
summary: "Deciphered, generalized blueprint of this workspace's own architecture (model-tier cascades, trust axes, retrieval cascade, knowledge graph, memory) — written to be portable to a different domain/user, kept here as the internal reference copy."
---

> [!NOTE] Vault context
> This is the internal reference copy of a document generated 2026-07-22 in response to a request to decipher this workspace's own AI-augmented research architecture and produce a portable blueprint for a different user's Claude Code. The body below is intentionally domain-agnostic (it was also handed to the user as a standalone file) — for the live, thesis-specific implementation of §2.3's tier hierarchy in *this* vault, see [[source-of-truth-tiers]]. Status is `ai-draft`: this is my synthesis of the workspace's own design, not yet human-reviewed for accuracy against current code.
>
> Hub: [[workflow-infrastructure]] (create if a dedicated hub page is wanted; this doc isn't scoped to `master-thesis` or the Routledge chapter — it documents workspace-wide infrastructure, per the memory prefix convention's "no prefix = workspace-wide" rule).

---

# AI-Augmented Research Workflow — Architecture Blueprint

> Reverse-engineered from a real 3-month production deployment (an academic thesis-revision + book-writing workflow run through Claude Code) and generalized so it can be rebuilt in **any** domain: legal research, financial analysis, journalism, product/UX research, policy work, grant writing, engineering RFCs, etc.
>
> **How to use this document:** feed it to Claude Code at the start of a new project and say "build me a workspace using this blueprint, adapted for [my domain]." Section 12 has a worked adaptation worksheet. Every mechanism below is described at two levels — the concrete instantiation it was observed in, and the domain-agnostic pattern underneath it — so you can port the pattern without importing the thesis-specific vocabulary.

---

## 0. Design Philosophy

Nine principles recur across every subsystem below. If you remember nothing else, remember these — they are what make the individual mechanisms cohere into one architecture instead of a pile of unrelated scripts.

1. **The chat session is an ephemeral cache; the filesystem is the durable substrate.** Nothing that matters should live only in conversation history. Every subsystem below ultimately resolves to "write it to a file, in a predictable place, with a predictable schema."
2. **Escalate cost only on failure, and only as far as needed.** Try the cheapest capable tool first (free deterministic API → free-quota LLM → paid frontier model). Treat arriving at the paid tier as an alarm to fix upstream, not a resting state.
3. **Grounding beats recall.** Wherever a claim is checkable against a real document, force a retrieval before letting the model assert it from parametric memory. Extend the same suspicion to your own retrieval/verification tools — they can hallucinate too.
4. **Never let the agent be the arbiter of its own promotion, and never let it trust its own prior output as ground truth.** These are two distinct failure modes (see §2) and both need an explicit, standing, periodically-reinforced rule.
5. **Flag discrepancies, don't silently auto-resolve them.** A mismatch between two sources of truth is a signal for a human, not an invitation for the agent to pick a winner — some mismatches are two legitimately different real things.
6. **Default to asking, not "fixing," when something looks wrong but came from a domain expert.** Reserve autonomous correction for unambiguous mechanical slips. This is the single most requested behavior correction in the source project's history.
7. **Plain text + folder placement + YAML frontmatter + a naming convention + backlinks is a complete state machine.** You do not need a database to track maturity, ownership, or project membership — you need consistent conventions and a query layer (Dataview, Obsidian Bases, a grep script, whatever) that reads them.
8. **Consent and privacy segregation should be structural, not aspirational.** Gate what leaves your machine by objective membership in an explicit opt-in set (a collection, a tag, a folder), enforced in code with a hard-refuse check — not by a policy sentence an agent might forget.
9. **Verify actions independently of the agent's self-report.** An out-of-band script that reads the actual execution log is the only reliable answer to "did X actually happen" for any side-effectful action class you care about.

---

## 1. Workspace Layout (generic template)

The source project uses a folder taxonomy where **position in the tree is itself a trust signal** — you can tell how reliable a file is largely from which folder it's in, before even opening it.

```
workspace-root/
├── PROJECT.md                  # the constitution: rules, folder map, status lattice, hard limits (see §11)
├── 00-inbox/                   # raw, unsorted captures (mobile notes, forwarded links, screenshots)
│                                #   agent may READ + triage here; never treat as a source; never leave silently unprocessed
├── 10-sources/                 # synthesized/compiled notes about external material (one file per source)
│                                #   written only via a defined "compile" procedure, never freehand
├── 20-knowledge-base/          # canonical reference docs + one hub page per active project
│   ├── _templates/             #   reusable page templates
│   ├── project-hub-template.md
│   ├── source-of-truth-tiers.md    # <- the tier-hierarchy doc itself lives here (see §2.3)
│   ├── status-board.md             # <- live query view over 30-outputs/ (see §7)
│   └── [project-id].md             # one hub page per active project, created on demand
├── 30-outputs/                 # ALL agent-generated prose/artifacts, every project, status: ai-draft by default
│   └── _staging/                #   working pre-briefs / scaffolds that are not final deliverables
├── [project-id]/                # on-demand project infrastructure dir (created when a project goes active)
│   ├── PROJECT.md               #   project-specific rules layered on top of the global PROJECT.md
│   ├── source-materials/
│   ├── raw-notes/
│   └── .automation/              #   project-scoped scripts, isolated from the shared ones
└── .automation/                 # shared automation infrastructure
    ├── logs/                    #   append-only action logs
    ├── manifests/               #   registries (source-tier config, freeze windows, decision logs)
    ├── scripts/                 #   pipelines: lookup cascade, sync scripts, audits
    └── cache/                   #   raw downloads, extracted text, local mirrors of remote catalogs
```

**Folder write-permission table** — define one of these explicitly for your own workspace; it's the cheapest bias-prevention tool you have, because it makes "can the agent touch this" a lookup, not a judgment call:

| Folder | Agent may write? | Notes |
|---|---|---|
| A read-only mirror of pre-existing material | ❌ never | e.g., a synced copy of an external knowledge base you don't own |
| `20-knowledge-base/` | Suggest + diff only | canonical reference; promote by human action only |
| `20-knowledge-base/_templates/` | ✅ | templates aren't content |
| `20-knowledge-base/[project-id].md` | ✅ on demand | hub pages, created when a project activates |
| `30-outputs/` | ✅ always `status: ai-draft` | this is the agent's actual output surface |
| `.automation/` (scripts, logs) | ✅ | append-only for logs |
| Anything under a project's "authoritative instructions" folder (reviewer comments, legal redlines, client requirements) | ❌ never modify; read only | see §2 — this is Tier-0/Tier-1 material |

---

## 2. Content Trust Architecture — three orthogonal axes

This is the most important and most under-implemented part of the whole system. The source project independently discovered **three distinct trust axes** that get conflated into a single "status" field in almost every simpler system — and conflating them is exactly what causes the recurring failure modes. Keep them separate.

### 2.1 Axis A — Maturity lattice (governs: can this be built upon at all?)

```
ai-draft  →  human-review  →  canonical  →  published
```

- **Forbidden transitions, enforced as a standing rule, not code:** the agent may never promote a file past `ai-draft`. It may never jump `ai-draft → canonical` skipping `human-review`. Promotion is a human action, always.
- **Usability-as-source table:**

| Status | May the agent cite/build on this? |
|---|---|
| `ai-draft` | ❌ Never, in any future synthesis |
| `revision-staging` (AI audit output humans haven't triaged yet) | ⚠️ Yes, but every factual claim drawn from it must carry an explicit `[VERIFY: ...]` tag |
| `human-review` | ✅ With caution |
| `canonical` / `published` | ✅ Freely |

### 2.2 Axis B — Provenance / citability (governs: how may this be used, independent of quality?)

Orthogonal to maturity. "My own excellent unpublished draft" and "a stranger's polished blog post" can both be nominally non-canonical, but they demand *opposite* treatment.

| citation-status | Meaning | Allowed use |
|---|---|---|
| `citable` | Published, third-party | Cite normally with full attribution |
| `in-preparation` / `under-review` | The principal's own unpublished work | May be read for **generative scaffolding only** — internalize voice/argument shape, then write natively. **Never quote or cite directly.** Every derived passage gets flagged: `[NOTE: developed from source-manuscript — check self-plagiarism before finalizing]` |
| `personal-communication` | Conversations, private notes, off-the-record material | May inform framing only; never cited without explicit instruction |

### 2.3 Axis C — Source-of-truth tier hierarchy (governs: when reconstructing "what does the human actually think / what is actually true," which document wins?)

This is the axis that prevents the single most expensive recurring failure in the source project: **the agent building new synthesis on top of its own prior AI-generated scaffolding, and reporting that synthesis as if it represented the human principal's actual position.** ("Self-anchoring.") This is *not* the same bug as an agent illegally flipping a status field — it's subtler: the agent never touches the status field, it just quietly starts treating its own last output as ground truth once the human has "sort of" incorporated it.

```
Tier 0 — External cited sources        (highest truth for "what does source X say")
Tier 1 — The human principal's own thinking (highest truth for "what does the human think"), with sub-tiers:
    1a — Formally accepted/finalized prior artifacts (read-only anchors)
    1b — Current working draft (human-review status)
    1c — The principal's own other unpublished writing (scaffolding only, per Axis B)
    1d — The principal's own inline annotations embedded INSIDE an ai-draft file
         (treated as Tier 1 even though the surrounding prose is Tier 3 — the annotation
         is the human's voice; the AI prose around it is not)
Tier 2 — Canonical knowledge-base docs (high-confidence AI+human consensus reference)
Tier 3 — AI-generated drafts            (co-created scaffolding; NEVER a source for future synthesis)
```

**Operating rules:**
- When making a claim about what the human thinks: cite Tier 1a/1b/1c first; if using a Tier 3 file, explicitly separate "the AI scaffold proposes X" from "the human's own annotation says X."
- When making a claim about an external source: cite via verbatim retrieval (Tier 0), never via a Tier 3 paraphrase.
- Tier 1d (an annotation) always outranks the Tier 3 prose it's embedded in.
- **Mandatory pre-flight before any substantive analysis of a topic:** read Tier 1a → 1b → 1c → 1d, in that order, and *only then* consult Tier 3 material, purely as scaffold-context. Skipping this order is what produces "the AI claims to summarize the human's view but is actually summarizing its own prior prose."

**Build this as its own canonical doc** (`20-knowledge-base/source-of-truth-tiers.md`) with worked right/wrong examples — it's cheap to write and is the single highest-leverage anti-hallucination artifact in the whole system.

---

## 3. Model-Tier Cost Cascade

An escalating fallback ladder used for **two** structurally identical purposes in the source project: (a) a batch data-lookup pipeline, and (b) a long-running memory-compression daemon. Both share one contract.

**Tier ladder (cost- and capability-ascending):**

```
T0  Free deterministic tools/APIs         (no LLM call at all — e.g. a metadata lookup API)
T1  Free-quota LLM, cheapest/highest-quota model of provider A
T2  Free-quota LLM, heavier model of provider A
T3  Free-quota LLM, provider B
T4  Free-quota LLM, provider C
T5  Paid frontier model, reached via a flat-rate subscription CLI (NOT a metered API key) — last resort
```

**The shared contract every tier function must implement:**
```
attempt(input) -> (result | None, diagnostic_reason)
```
- The diagnostic reason (e.g. "rate-limited" vs "empty response" vs "malformed JSON") is used **only for logging/observability.** The escalation *decision* is binary: any non-success (exception, missing key, empty/unparseable result — treat them all the same) triggers escalation to the next tier. Do not try to be clever about which failure "deserves" escalation; that cleverness is exactly what breaks when a provider changes its error format.
- Classify rate-limit-shaped errors by lowercased substring match on the exception text (`429`, `quota`, `resource_exhausted`, `rate_limit`, `too many requests`) for logging — **never** gate escalation on this classification, because a deprecated model ID that 404s instead of 429ing will silently mis-log as a generic miss otherwise.

**Position tracking — two different rules for two different caller shapes:**
- **Stateless batch work over independent items:** re-enter at T0 for every item, regardless of what tier the previous item needed. T0 is free, so there's no cost to re-checking it every time.
- **A long-running service:** persist the current tier to a small settings file; on health-check, re-test *only forward from the saved position* (never restart from T0). Provide both an automatic mode (self-test, walk forward on failure) and a manual override to force a specific tier without testing.

**Terminal-tier discipline:**
- The paid tier should be invoked via a flat-rate/subscription-authenticated path, not per-token metered billing — this bounds worst-case cost if the cascade gets stuck there.
- Treat reaching T5 as a signal to go fix the upstream free-tier problem (quota, call volume, a stale model ID), with an explicit plan to revert once it's fixed — not as a new normal.
- **Tiering does not protect you from a pathological caller.** A cascade with perfect escalation logic can still exhaust its quota and crash-loop if something hooks it into a very high-frequency trigger. Audit call *volume* separately from fallback *depth*.
- Apply the identical cheapest-first logic to **correctness**, not just cost: run a grounded/deterministic check before letting an ungrounded generative step touch a truth-sensitive claim (this is the bridge to §4 and §6).

---

## 4. Source-Acquisition Cascade

A tiered, privacy-segregated, hallucination-resistant pipeline for pulling in outside material and using it to ground claims.

**Tier ladder, in order, with the reasoning for the order:**

```
1. Trusted-corpus query    (a RAG/notebook tool pre-loaded with vetted documents; forces a VERBATIM
                             excerpt back, not a recalled paraphrase — see below)
2. Local file cache        (a prior download; for exact page/passage cross-checks a corpus tool's
                             page numbers may not be reliable)
3. System-of-record lookup (your reference manager / document store — see §5; catalog first, dedupe)
4. Legitimate opportunistic sources (open access, public filings, official APIs — usually manual, no
                             single automated aggregator covers this tier well)
5. Last-resort / gray-area sources  (only if 1–4 fail; ALWAYS fetched resumably in the background,
                             never blocking the main task; verified by content signature before trust)
```

**Why a trusted-corpus tool sits at the top, not memory:** the point isn't search convenience, it's **forced grounding**. A well-designed corpus tool returns an actual quoted excerpt plus a source identifier; require that any "verified" claim embed that literal excerpt, not just a citation label. This makes fabrication structurally harder — a claim can't be marked verified without a string that traces to a real retrieval call against a real document. Scope corpora *narrowly* (per-entity, per-case, per-topic) rather than one undifferentiated pool: it cuts retrieval noise and makes privacy segregation tractable.

**Cost-of-indexing decision rule:** a one-off, clean/born-digital document can stay in the local cache. A noisy scan, or anything you expect to query more than once or twice, is worth the fixed cost of indexing into the trusted corpus — the source project measured its own local-dump path at 50–186KB of OCR-noisy page-dumps per query, against a clean, low-token verbatim excerpt from the indexed corpus for the same query. That gap had to be *discovered* empirically (an earlier session had drifted toward "local-file-dump-first" as the default), not assumed — measure your own pipeline's actual token cost per path before picking a default.

**Privacy segregation, enforced in code:**
- Split your trusted corpora into purpose-scoped notebooks/collections with **hard-refuse checks at the sync/upload script level** — e.g., a sync script that exits with an error if the target matches a known-sensitive collection ID, not just a comment saying "don't upload this here."
- Anything genuinely sensitive (confidential correspondence, privileged material, source-protection material) is declared local-only on disk and never transmitted to any external service, by policy *and* by omitting it from every upload script's input set.
- Gate what's eligible for upload to any tier by **explicit opt-in membership in a defined set** (e.g., a specific collection in your system of record) — never by a blanket "everything in the library" default, and never gated by some proxy like "has a DOI" that leaves silent gaps.

**Two operational disciplines that make the cascade resilient rather than fragile:**
- **Auth-refresh discipline:** for every auth-gated tool in the chain, always attempt the cheap/silent refresh path first (e.g., a CLI re-login against a persisted browser profile) before assuming a slow interactive re-auth is required. Explicitly document any confusingly-similar alternate binary/tool that would *falsely* confirm "manual fix needed" if invoked by mistake.
- **Mirror-rotation discipline:** for any external resource with multiple mirrors/endpoints, maintain (or delegate to) a live-status directory rather than hardcoding one domain — and don't infer a resource is dead from one failed access pattern used the wrong way (e.g., hitting a status page as if it were a download endpoint and reading the resulting 403 as "it's gone").

**Ingestion hygiene:**
- Never add a lossy format-conversion step to fit your pipeline's assumptions (e.g., don't convert EPUB→PDF) — check what your destination systems natively accept first.
- Encode the join key (e.g., a catalog record ID) directly in filenames at acquisition time, so downstream steps (attach, catalog, verify) can run statelessly and idempotently — skip-if-exists on a glob check, not a database round-trip.
- Verify every acquired artifact by content signature (magic bytes) and a minimum size threshold before trusting it as successfully retrieved; log a structured manifest of successes/failures/not-founds for audit and human follow-up.
- For last-resort/slow sources: fetch resumably in the background (`curl -C -` / `wget -c`, launched non-blocking) and poll to completion. A foreground fetch with a short timeout against a throttled server produces silently truncated files that *look* complete.

---

## 5. System-of-Record Integration Pattern

Generalizes the "Zotero" role: whatever tool is your **canonical catalog of external facts/entities/citations** (could be a reference manager, a CRM, a document management system, a case-management system).

**Dual-API pattern, if your system-of-record has one:**
| | Fast local/read path | Authoritative write path |
|---|---|---|
| Typical shape | A local desktop app's read-only API (no auth needed, very fast) | A cloud Web API (requires an API key, has rate limits) |
| Use for | Search & read | Create / update / delete |
| Gotcha | Will return 400/501 for any write attempt — don't try | This is the ONLY path that should ever mutate the record |

If your tool doesn't have this split, at minimum separate "search/browse" credentials from "mutate" credentials, and never let an agent mutate the system of record through a path that wasn't designed for writes.

**Staging/consent patterns:**
- **"Needs review" staging collection:** agent-ingested candidates land in a dedicated staging bucket, never directly in the main catalog — a human sweep promotes them.
- **Collection-membership-as-consent:** an item's presence in a specific, explicitly-named collection is treated as the sole permission signal for downstream automation (e.g., "eligible for upload to the trusted corpus") — no secondary gating by metadata completeness. This makes consent auditable (you can literally list the collection) and revocable (remove from collection = revoke).

**Known API-shape gotchas worth checking for in any client library you build:**
- Response payloads for batch-create operations are sometimes string-keyed dicts (`"0"`, `"1"`, not integer indices) — don't assume you can index numerically.
- An item-type template that has a `DOI` field may not have an `ISBN` field (or vice versa) — check per-type before blind-assigning.
- A JSON-RPC style endpoint may behave differently under different HTTP clients (e.g., failing under a client that negotiates keep-alive) — if a call mysteriously errors in one tool but works via a plain low-level HTTP request, suspect the client library, not the API.
- Two "views" onto the same underlying data (e.g., a citekey plugin's own index vs. the main API) can disagree — check both when resolving an identifier if one comes back empty.

**"Check the system of record before declaring something unavailable"** — this deserves its own callout because it was the single most costly recurring mistake in the source project: an agent concluded a cited source "wasn't held" based on a filename glob not matching, when the item existed under a different filename with correct metadata in the actual catalog. **Rule: exhaust the full acquisition cascade (§4) and match by authoritative metadata, never by filename pattern, before asserting something is unavailable.** For non-Latin-script or translated content, search using the *original*-language terms, not a translation — the quote you're checking for is often the author's own translation and won't glob-match the English search term you tried.

---

## 6. Epistemic Hygiene / Bias-Mitigation Checklist

Every one of these tactics was minted **reactively**, after a specific real error, then written up as a standing rule. That's the right process to imitate: don't try to anticipate every failure mode up front — build the checklist by promoting real incidents into rules, and keep it in a living, searchable memory file, not buried in a one-time instruction.

**How "unknowns" get explored, as a distinct move from "how errors get caught":** the tactics below are mostly about not asserting something false. A separate, prior question is how the system finds out what it doesn't yet know it needs to check. Three mechanisms do this: (1) the `digest` command (§9) periodically surfaces new material and *candidate* cross-links for human triage — it proposes, never auto-applies; (2) the retrieval cascade (§4) is run in scouting mode whenever a claim's evidence tier is uncertain, not only when it's already known to be checkable; (3) the multi-axis sweep (tactic 7 below) is explicitly not scoped to "things already flagged" — it's the mechanism that turns "we don't know what we don't know" into a bounded, repeatable search, by fixing the *dimensions* of ignorance (attribution? internal consistency? translation?) even when the specific instances aren't yet known.

**A. Grounding tactics**
1. **Retrieve before you assert**, for any claim that characterizes, disputes, or attacks a third party's position — never formulate the claim from memory and check it afterward.
2. **Evidence-tier ranking:** primary document > independently-queried tool/retrieval output > the model's own trained memory. Forbid the lowest tier from being cited as a verdict on a consequential claim.
3. **Distrust the verification tool too.** A purpose-built retrieval/verification layer can itself hallucinate a discrepancy that doesn't exist in the primary source. When a finding from your "trusted" tool is surprising or load-bearing, check it against the literal primary artifact anyway.
4. **Scale rigor to stakes.** Full grounding-before-assertion for contested/consequential claims; lighter-touch for routine, uncontroversial summary. A flat maximum-rigor policy is unworkable at scale; a flat zero-rigor policy is how the incidents above happened. State the rigor function explicitly so it's applied consistently.
5. **When verification structurally isn't possible** (source not in your indexed corpus, tool down), mark the claim explicitly unverified (`[unverified — source not available]`) rather than either asserting it confidently or silently dropping the caveat.

**B. Coverage tactics**
6. **Select what to scrutinize from the artifact's current text, not an inherited flag list.** A prior pass's silence is not evidence of correctness — confidently-stated, unflagged content is the *highest*-risk category, precisely because no one has looked yet.
7. **Sweep a fixed taxonomy of distinct failure axes every time**, not one question repeated. (Worked example from the source project, for a citation-heavy document: quote fidelity / citation locus / attribution / internal consistency / factual accuracy / interpretive fidelity / self-citation dating / translation equivalence. Adapt the axis list to your artifact type — e.g., for a financial report: figure provenance / calculation consistency / period-comparison validity / disclosure completeness / attribution of forward-looking statements.)
8. **Calibrate check coverage to each layer's structural blind spot.** Know which error classes each automated check can and cannot see by construction; run the *only* layer that can see a given error class at 100%, never sampled, while cheaper layers run as a first pass.
9. **Learn each verification tool's own noise profile before trusting its raw hits.** A cross-check API might be dominated by benign false positives (e.g. edition/reprint-year drift for a citation checker) — restrict it to its actually-reliable sub-signal.
10. **Validate any custom-built verification tool with a blind, planted-error test before trusting its claimed catch rate.** Don't assume it works because it runs without crashing.

**C. Human-interface tactics**
11. **Default to asking, not fixing, when a domain expert's choice looks non-standard.** ("Did you intend X over the standard Y, for reason Z?") Reserve unilateral correction for unambiguous mechanical slips (a true typo, a mismatched bracket).
12. **Build pattern-matching tolerant of real human variance**, not the cleanest theoretical format — informally-authored markers/tags/annotations get typed inconsistently (case, spacing, punctuation) by real humans. A too-strict search silently under-counts and produces a false all-clear.
13. **When a human asserts your negative search result is wrong, treat it as a signal to search more robustly — not a claim to argue against.**

**D. Process tactics**
14. **Flag discrepancies between two sources of truth; don't auto-resolve.** Check for a legitimate reason both could be correct before treating either as an error.
15. **Verify the actual output against the actual goal — never let "the script exited 0" or "N items processed" substitute for inspecting whether the result is fit for purpose.**
16. **Route the agent's own quick/manual edits through the identical review pipeline used for fully generated output.** Small ad hoc patches are exactly where quality-gate bypass happens.
17. **After any incremental/accretive edit to multi-part output, do a full linear re-read as a first-time reader** (not just a diff of the new part) — insertions can create forward-references invisible from reviewing only the new content.
18. **Build an independent, out-of-band auditor over the raw execution log** for any side-effectful action class you care about (writes, sends, deletions, payments). An agent's self-report of what it did can diverge from what actually executed; only the log is authoritative for "did X actually happen."

**E. Structural/scale tactic**
19. **For a high-stakes fact-check pass, don't rely on one agent checking its own work — fan out independent verification and require agreement.** The source project's most successful fact-check runs were explicitly run as a multi-agent job: one pass generates candidate findings, then multiple independent agents each re-check a finding against the primary source before it's reported as confirmed (a single agent grading its own output tends to rubber-stamp it). This is the same principle as tactic 3 (distrust the verification tool) applied at the orchestration level: don't let the thing that produced a claim be the sole thing that clears it. *(This document was itself produced this way — the research behind it ran as parallel independent fact-finding passes over the source material, not one agent's single read-through.)*

---

## 7. Knowledge-Graph / Progress-Tracking Layer

The core insight: **you don't need a database.** Folder placement + YAML frontmatter + a naming convention + backlinks *is* the entire state machine, queryable by any tool that can parse markdown + frontmatter (Obsidian, Notion-via-import, a plain Python script, `git grep`).

**The four signals, and what each one encodes:**
| Signal | Encodes |
|---|---|
| Folder placement | Coarse maturity/type (per §1's write-permission table) |
| YAML frontmatter (`status`, `project`, `citation-status`, `summary`, `source-notes`) | Fine-grained, machine-queryable state |
| Filename convention: `[project-id]_[task-id]_[description].md` | Project + task routing, sortable, greppable |
| `[[wikilinks]]` in the body, back to a project hub page | Graph edges — creates a backlinks panel with zero manual linking |

**Status board pattern:** a single query-view file (Dataview, Obsidian Bases, or a hand-rolled script) that tables every file in your outputs folder by `status`, grouped/sorted by project and modification time. This is your bird's-eye "what's still ai-draft vs. what's canonical" view, and it updates automatically the instant a frontmatter field changes — no separate tracking system to keep in sync.

**Project hub page pattern:** one page per active project (`20-knowledge-base/[project-id].md`), created first when a project goes active, containing: a status callout (current phase, what's blocking, deadline), a progress table, links to key files, links to core source material, and a live query listing active drafts for that project. Every other file for that project links back to the hub via `[[project-id]]`, making the hub the most-connected node in the graph automatically.

**Multi-project isolation on shared folders** (when several initiatives share the same output folders): use **three redundant signals together** — (1) `project:` in YAML frontmatter, (2) a `[project-id]_` filename prefix, (3) a `[[project-id]]` wikilink in the body. Redundancy matters here: any single signal can be dropped by accident (a copy-paste that loses frontmatter, a rename that drops the prefix), but three independent signals essentially never all fail at once, so files never silently get conflated across concurrent projects.

---

## 8. Durable Memory & Session-Continuity Architecture

Three structurally different failure modes converge on one fix: context-window compaction erases in-session memory; reconnects after a dropped connection are brand-new sessions with zero chat continuity; and work that spans devices has no shared runtime at all. The fix in every case: **push durable state to files, read them back at the start of every entry point, regardless of how that entry point was reached.**

**Three-tier memory stack, with an explicit, written precedence rule:**

| Tier | What | Trigger | Authority |
|---|---|---|---|
| **A — Raw archive** | Lossless, append-only, complete transcript of every interaction including tool calls | A **lifecycle hook** (pre-context-truncation, session-end, process-exit) — never an instruction telling the agent to remember to save | **Wins any conflict.** Source of truth. |
| **B — Semantic index** | Fast, approximate "have I dealt with this before" search, typically running on a cheap/free model | Built incrementally as sessions happen | Convenience finding-aid only — **never authoritative.** Can go down without taking durability with it. |
| **C — Curated rules** | A small, human-editable file of standing rules, gotchas, and decisions (your `PROJECT.md` + a memory index) | Written deliberately, reactively, after real incidents (see §6) | Authoritative for *policy*, not for *what happened*. |

**Why lifecycle hooks, not instructions:** the source project's own history shows the evolution directly — an early version relied on an instruction ("before compaction becomes imminent, export the conversation") and it was fragile precisely because it depended on the agent noticing compaction was coming in time. It was replaced by a hook wired to the platform's actual pre-truncation and session-end events — pure file I/O, no model dependency, so it can't fail from a rate limit or provider outage. **Any instruction-based persistence rule should be treated as a stopgap to be replaced by a lifecycle hook, not a permanent design.**

**Two distinct recall tools, not one search bar:**
- A **verbatim/grep** surface that returns exact passages with file+line provenance and never summarizes — use first whenever exact wording, a decision, or an error message matters.
- A **semantic/embedding search** tool for fuzzy "have we touched this before" discovery — demoted to a finding aid, never trusted as authoritative, because embedding retrieval can drift or approximate.

**If your durable substrate is a cloud-sync drive (Dropbox/pCloud/OneDrive/etc.):** the sync engine becomes a dependency with its own failure mode. A real incident: a scripted bulk rename of ~66 files followed immediately by ~1,500 rapid edits silently corrupted the cloud service's per-file object records; the damage didn't surface until later, as a revert loop (any local write to an affected file got silently restored to the stale cloud copy within ~10 seconds). Toggling the sync connection did nothing (the corruption was server-side, not in the local link); the fix was a full client cache reset (pause → quit → clear cache/relink → restart). **Two durable lessons:** (1) don't fire rapid bulk filesystem mutations at a cloud-sync drive — pace them or do them on a local copy and let sync catch up gradually; (2) keep a cheap **marker-write-and-poll canary** (write a distinctive string, poll at fixed intervals, confirm it survives) to catch silent revert corruption before mistaking it for a saved write.

---

## 9. The End-to-End Content Pipeline

Putting §2, §6, and §7 together into the actual brainstorm → draft → publish flow.

**Typed placeholder taxonomy** — when triaging an incomplete section/deliverable, classify every gap by *what kind of work it needs*, not just "todo":
- `[GENERATIVE]` — needs expansion from underlying theory/reasoning/sources; direction is set but content isn't written
- `[LOOKUP]` — a specific external fact/citation is needed; must be resolved against the system of record (§5) before any prose is generated around it — **never generate a plausible-sounding citation and backfill it later**
- `[PROSE]` — the argument/content is essentially complete; needs conversion into polished output preserving the author's voice
- `[VERIFY]` — a claim sourced from non-canonical material; must be resolved against Tier 0 (§2.3) before the deliverable finalizes

**Four canonical, fixed-procedure commands** — give each of these a name, a fixed sequence of steps, and a fixed output location, so invoking them is deterministic rather than improvised each time:
1. **`ingest`** — sweep the inbox, extract candidate entities/citations, push to the system-of-record's staging collection (never directly to the main catalog), write a summary for human review, log the action.
2. **`compile`** — read one source item, extract the structured facts you care about (for research: question/method/finding/relevance), write a structured note with backlinks to related knowledge-base pages and the project hub.
3. **`digest`** — periodic sweep of what's new across a time window, summarized by project, with candidate cross-links flagged for human review (never auto-applied).
4. **`draft`** — read only `canonical`/`human-review` material (§2.1) plus the relevant style/register guide; if using `revision-staging` material, tag every factual claim `[VERIFY: ...]`; write to the outputs folder at `ai-draft` status with full `source-notes` provenance and backlinks.

**Claim-evidence ledger** (for any deliverable making assertions that need defending): a table — `Claim | Location | Evidence Source | Certainty Allowed | Problem | Revision` — plus a fixed mapping from evidence tier to permitted assertion-strength vocabulary (e.g., "we measured X" only for direct observation; "X suggests Y" for inference; ban "proves"/"confirms"/"ensures" outside of stipulated/directly-observed facts). Make the check mechanical: a small banned-words/overclaim lexicon that's grep-able by anyone, human or agent.

**Stakeholder/reviewer-response closure contract** (for any deliverable that goes through external review): a table — `ID | Comment (verbatim) | Anchor | Classification | Artifact Change | Evidence` — with one hard rule: **a row closes only when the artifact visibly changed, or the response gives an evidence-backed reason for not changing it.** A bare "acknowledged"/"clarified" with no diff is a named failure mode, not a valid closure. Sequence the work so the change is made *before* the response is drafted — this structurally prevents writing a response that describes a change that doesn't exist.

**Agent self-audit gate, before human review:** a short internal checklist the agent runs on its own output before presenting it — findings-before-claims ordering, every number traceable to a source, overclaim language removed, every reviewer-response row points to a real change. This catches format violations early and cheaply, distinct from and prior to whatever the human-facing review checklist covers.

**Compressed cross-session context packet** per major long-running deliverable: a small fixed set of files (format/style rules, project context, a claim ledger, a reviewer-comments log, a submissions/revision-history log) that lets a fresh session reconstruct "where are we" without re-reading the entire deliverable — and specifically lets "did we already address comment N" be answered by a file lookup instead of either re-reading everything or, worse, defaulting to the agent's own last guess (the self-anchoring failure from §2.3 again).

---

## 10. Build Sequence

A rough phased rollout — later phases assume earlier ones exist, but each phase is independently useful; stop wherever gives you enough value.

1. **Vocabulary pass.** Fill in the adaptation worksheet (§12) for your domain. Write your `PROJECT.md` constitution: folder map, the three trust axes (§2) with your domain's actual field values, the write-permission table (§1), and your hard-limits list (deletions, external sends, anything requiring human sign-off).
2. **Folder skeleton + status lattice.** Create the folders from §1. Pick your YAML frontmatter schema. Nothing automated yet — just get humans and the agent using the conventions manually for a week or two before scripting anything.
3. **System-of-record integration (§5).** Connect your reference manager / CRM / document store. Build the staging-collection pattern. Get the dual read/write path (or its equivalent) working and documented.
4. **Model-tier cascade (§3).** Only build this once you have a concrete recurring lookup/generation task worth optimizing — don't build it speculatively.
5. **Source-acquisition cascade + trusted corpus (§4).** Stand up your RAG/notebook tool, scope your first 2-3 corpora narrowly, wire the privacy-segregation hard-refuse check before you upload anything sensitive-adjacent.
6. **Bias-mitigation checklist as a living memory file (§6).** Don't write this speculatively either — start with the grounding tactics (A1-A3) as defaults, and add each new tactic *reactively*, the first time you catch a real error of that shape. This file should visibly grow over the project's life.
7. **Knowledge graph + status board (§7).** Once you have enough files that "what's the state of everything" is hard to hold in your head, add the query-view layer.
8. **Session-continuity hooks (§8).** As soon as you're relying on cross-session memory for anything load-bearing, replace any instruction-based persistence with a lifecycle hook. Don't wait for a data-loss incident to force this.

---

## 11. Hard Limits Template

Adapt this list for your own domain and put it in `PROJECT.md`, phrased as absolute prohibitions, not preferences:

- Modify any file at `canonical` or `published` status
- Delete any file
- Add edits to existing knowledge-base pages without showing a diff first
- Submit anything to the system-of-record's main catalog without human review
- Fabricate a citation/reference not verified against the system of record or provided source material
- Modify authoritative instruction material (reviewer comments, legal redlines, client requirements — whatever your domain's equivalent is)
- Self-promote any file's maturity status
- Treat the agent's own prior output as a Tier-0/Tier-1 source (§2.3)

---

## 12. Adaptation Worksheet

The blueprint above was extracted from an academic-thesis/book-writing workflow. Here's how its concrete instantiations map onto the generic pattern — use this table to find-and-replace for your own domain.

| Generic pattern | Source-project instantiation (academic) | Example: legal research shop | Example: financial-analysis desk | Example: journalism/fact-checking |
|---|---|---|---|---|
| System of record | Zotero (reference manager) | Case-management system / precedent database | Filing/document-management system (EDGAR mirror, internal DMS) | Source/document management tool, contact database |
| Trusted corpus tool | NotebookLM notebooks per author/topic | RAG over case law + statutes, scoped per matter | RAG over filings, scoped per company/sector | RAG over primary documents, scoped per story/beat |
| Privacy tiers | A-Sources / B-Self / C-Audits | Public precedent / client-privileged / internal work product | Public filings / MNPI-adjacent internal notes / audit trail | Public record / source-protected material / editorial notes |
| Last-resort acquisition | Shadow libraries (background-fetched) | Court-record retrieval services, FOIA queue | Alternative data vendors, manual filing pulls | Public-records requests, archive.org |
| Maturity lattice | ai-draft → human-review → canonical → published | draft → associate-review → partner-approved → filed | draft → analyst-review → desk-approved → published | draft → editor-review → fact-checked → published |
| Citation-status axis | citable / in-preparation / personal-communication | citable precedent / privileged work product / off-the-record | citable filing / internal model / off-the-record source comment | on-the-record citable / background-only / off-the-record |
| Source-of-truth Tier 1 (the principal's own thinking) | Viva-passed draft, revision DOCX, source manuscripts | The lead attorney's own prior briefs/memos on the matter | The lead analyst's own prior notes/models | The reporter's own notes and prior published pieces |
| Knowledge-base hub page | Project hub (`20Wiki/[project-id].md`) | Matter hub page | Coverage-initiation hub page | Story/investigation hub page |
| Typed placeholders | [GENERATIVE]/[LOOKUP]/[PROSE]/[VERIFY] | same pattern, applied to brief sections | same pattern, applied to report sections | same pattern, applied to article sections |
| Claim-evidence ledger | Certainty-vocabulary table (banned overclaim words) | Holding-support table (record-supported vs. inferred) | Figure-provenance table (reported vs. derived) | Claim-source table (confirmed vs. single-sourced) |
| Reviewer-response closure | Reviewer-response table (R1.1, R1.2...) | Partner-comment closure table | Compliance-review closure table | Editor-note closure table |

**Sizing note:** the source deployment ran for ~3 months, generated dozens of memory/rule files reactively, and integrated 5+ external services (reference manager, RAG/notebook tool, cloud storage, a markdown-native knowledge base, and a multi-tier model-routing layer). Don't try to build the whole thing in week one — §10's build sequence exists specifically so you can stop at whatever phase gives you enough leverage for your actual workload.
