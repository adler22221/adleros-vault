<img src="https://r2cdn.perplexity.ai/pplx-full-logo-primary-dark%402x.png" style="height:64px;margin-right:32px"/>

# Analyze how this architecture connects Claude, NotebookLM, Obsidian, and Zotero in the research workflow:

[https://github.com/WenyuChiou/ai-research-skills](https://github.com/WenyuChiou/ai-research-skills)

Here is a thorough analysis of how the [WenyuChiou/ai-research-skills](https://github.com/WenyuChiou/ai-research-skills) architecture connects Claude, NotebookLM, Obsidian, and Zotero across the research workflow.

## Architectural Overview

The repo is a **Claude Code skills catalog** — 13 Markdown instruction files (`SKILL.md`) installed as plugins that Claude Code auto-triggers based on your phrasing . The four tools you mention are not equal-status peers: Claude is the **orchestrator**, while Zotero, Obsidian, and NotebookLM are **specialized data stores** that Claude reads from and writes to via the `research-hub-pipeline` Python CLI . The overall pipeline has 8 stages from literature discovery through submission .

## The Four Tools, Defined by Role

| Tool | Role in architecture | Integration mechanism |
| :-- | :-- | :-- |
| **Claude** | Orchestrator / reasoning engine | Runs all skills; triggers delegation to Codex/Gemini when needed |
| **Zotero** | Bibliographic database (CRUD) | Local API (port 23119) or Web API key; `zotero-skills` + `zotero-library-curator` |
| **Obsidian** | Notes and knowledge graph layer | File-system writes — `research-hub` writes paper notes as `.md` files into your vault |
| **NotebookLM** | AI synthesis + source bundling | Source bundles uploaded by `research-hub`; briefs verified by `notebooklm-brief-verifier` |

## Stage-by-Stage Data Flow

**Stages 1–2 (Discover \& Organise literature)** are where all four tools intersect most densely . The `research-hub` skill instructs Claude to search arXiv/Semantic Scholar/CrossRef/PubMed, then simultaneously: write paper metadata into Zotero, write reading notes into Obsidian as a "cluster," and assemble a source bundle for NotebookLM upload . This means a single Claude invocation populates all three external tools at once — the key architectural integration point.

**Stage 2 specifically** adds a verification loop: NotebookLM synthesizes the uploaded bundle into a brief, and the `notebooklm-brief-verifier` skill then has Claude cross-check that brief against the original Obsidian/Zotero sources to catch missed citations, unsupported claims, or contradictions . This is the only skill that explicitly creates a feedback loop *back from* NotebookLM.

**Stages 3–6** (framing, planning, experiments) operate largely without NotebookLM or Obsidian — Claude produces `.research/*.yml` manifest files locally to preserve project context across sessions . Zotero re-enters in Stage 7 when `academic-writing-skills` flags bibliography entries that need cleanup .

## The `research-hub setup` Onboarding Pattern

A critical architectural detail: the Python CLI `research-hub setup` runs an **interactive onboarding** that asks which of Zotero/Obsidian/NotebookLM you want to wire up . This means the architecture is modular — you can run it with only Zotero, only Obsidian, or all three. Skills degrade gracefully: `notebooklm-brief-verifier` falls back to "Manual mode" (you paste the brief) if the CLI isn't configured .

## Cross-Cutting Delegation Layer

Above the four-tool layer sits a multi-AI routing layer :

- `codex-delegate` — Claude hands off token-heavy mechanical work (batch edits, plotting scripts) to Codex CLI
- `gemini-delegate` — Claude hands off long-context reading or CJK/繁中 output to Gemini CLI
- `research-hub-multi-ai` — a stage-agnostic router that generates a delegation plan + handoff prompts when you ask "who should do this?"

This means Claude is not just calling Zotero/Obsidian/NotebookLM — it is also **routing tasks to other AI models** based on task character (token load, language, context length), making it a true multi-agent orchestration layer, not just a single-AI assistant .

## Key Design Principle

The architecture treats **Zotero as the authoritative bibliography**, **Obsidian as the living knowledge graph**, and **NotebookLM as the disposable synthesis surface** (outputs are verified, not trusted directly) . Claude sits above all three, using them as persistent storage while keeping reasoning and routing entirely in-model — which means the `SKILL.md` files are essentially system-prompt-level specifications that can be ported to Codex, Gemini, Cursor, or any other AI host without losing the workflow logic .

---

# read this previous thread thoroughly to identify what I'm trying to build, and see if WenyuChiou's architecture can be used for my architecture.

Now I have a thorough understanding of both your system and WenyuChiou's architecture. Let me produce a comprehensive analysis.

Your goal is building what you've called an **"Agentic Research Librarian"** — a system that functions like a team of librarians, research assistants, editors, and public communication specialists, so you can delegate knowledge-management chores and focus on your actual research and writing. From the thread, your system involves a Lenovo ThinkBook (main workhorse), a MacBook Air A2179 (AI agent machine), a future DAS, and a layered Obsidian vault (`00Inbox / 10Literature / 20Wiki / 30Drafts`) over your existing `2ndbrain` archive — plus Zotero, GitHub sync, and APIs.[^2_1]

Here is a rigorous comparison of WenyuChiou's architecture against yours:

***

## Where They Align Closely

The conceptual overlap is substantial. Both architectures share the same **core three-tool triangle** — Zotero as the authoritative bibliography, Obsidian as the knowledge workbench, and a Claude-class agent as the orchestrator. The governance model you arrived at (AI drafts go into a staging area → human review → promoted to canonical) maps almost exactly to the `notebooklm-brief-verifier` + `paper-memory-builder` trust pipeline in WenyuChiou's `30Drafts`-equivalent design. Your 4-verb design (`ingest`, `compile`, `digest`, `draft`) also mirrors his canonical skill set almost one-to-one:[^2_1]


| Your verb | WenyuChiou skill equivalent |
| :-- | :-- |
| `agent ingest` | `research-hub` (ingest from arXiv/Semantic Scholar + `zotero-skills`) |
| `agent compile` | `literature-triage-matrix` + `paper-memory-builder` |
| `agent digest` | `research-context-compressor` + `research-project-orienter` |
| `agent draft` | `academic-writing-skills` + `gemini-delegate` (CJK/multilingual) |
| *(your link-suggestion step)* | `zotero-library-curator` (audit + candidate links) |

[^2_1]

***

## Where WenyuChiou Adds Directly Usable Value

**Skills you can install today without building from scratch:**

- **`zotero-skills` + `zotero-library-curator`** — these directly cover your auto-housekeeping use case: deduplication, orphan-tag cleanup, batch metadata repair, and candidate interlinking (as *suggestions*, not auto-commits, which matches your governance model) .
- **`notebooklm-brief-verifier`** — your thread identified NotebookLM as a synthesis surface whose output must be verified against sources. This skill is purpose-built exactly for that, running a cross-check between the NotebookLM brief and the source bundle to catch hallucinated or unsupported claims .
- **`research-context-compressor` + `research-project-orienter`** — these directly solve your "I need to re-onboard a new AI session to my Allocation Dependence project in seconds" problem. They write `.research/*.yml` manifests so future Claude sessions skip the full vault re-scan — critical for your multi-year book project.[^2_1]
- **`academic-writing-skills`** — covers your multi-channel publishing pipeline: claim-evidence audit, banned-word/humanize pass, journal-format check, and reviewer response. Aligns with your need to generate academic, grant, and SNS-format outputs from the same vault .
- **`gemini-delegate`** — since you have Japanese/CJK output needs (ronbun hakase track, Japan Study Tour, Zhuangzi-inflected SNS posts), this skill handles long-context and CJK delegation to Gemini CLI — a workflow gap your original Gemini-centric design didn't formalize.[^2_1]

***

## Where Your Architecture Goes Further

WenyuChiou's repo does **not** cover three important aspects of your system:

1. **Social media → Zotero ingest pipeline** (Instagram/Facebook screenshot → LLM Vision → DOI lookup → Zotero inbox). He assumes papers enter via proper search (arXiv, Semantic Scholar). Your vague-reference ingest from social posts needs the staged automation you designed: iOS Shortcuts → `00Inbox` → batch agent review → Needs Review Zotero collection.[^2_1]
2. **Multi-device hardware architecture** (Lenovo as workhorse, Mac A2179 as agent host, DAS as cold storage). WenyuChiou's skills assume a single machine running Claude Code. Your hot/warm/cold data tiering and the separation of heavy AI jobs to the Mac needs a deployment layer he doesn't address.[^2_1]
3. **Multi-channel tone adaptation in `draft`** — your `agent draft --type` distinguishes formal academic, grant-proposal, and Daoist-inflected SNS tones with source traceability back to vault notes. WenyuChiou's `academic-writing-skills` covers academic/journal, but the SNS and grant-proposal modes with your specific stylistic signature (Zhuangzi framing, prefigurative academia voice) need custom `SKILL.md` files added to his architecture.[^2_1]

***

## Recommended Integration Strategy

Given all of this, you don't need to choose between the two architectures — WenyuChiou's repo is best treated as **the skills layer you install on top of your hardware/vault design**, not as a competing system. A clean integration path:

1. **Use WenyuChiou's `research-hub setup`** to wire up your existing Zotero + Obsidian + NotebookLM — this replaces the manual `pyzotero` + Dataview scripting from the Gemini plan with tested, Claude Code-native skill files .
2. **Adopt his 5 skills immediately** without any custom work: `zotero-skills`, `zotero-library-curator`, `notebooklm-brief-verifier`, `research-context-compressor`, `academic-writing-skills` .
3. **Keep your own vault structure** (`00Inbox/10Literature/20Wiki/30Drafts` + `2ndbrain` archive). His skills write to file paths you specify — your folder conventions are not overridden.
4. **Build two custom `SKILL.md` files** for gaps he doesn't cover: a `social-media-ingest` skill (staged iOS → Zotero pipeline) and a `multi-channel-draft` skill encoding your three tone modes (academic / grant / SNS-Daoist) with source-tracing metadata.[^2_1]
5. **Route heavy AI jobs via `gemini-delegate`** to your Mac A2179 (the agent host machine), using his delegation architecture rather than building your own task-routing from scratch .

The single most important thing WenyuChiou's architecture adds to yours is the **governance layer around NotebookLM outputs** (the verify-before-trust loop), which you had identified as a need but hadn't yet formalized into a specific mechanism.[^2_1]

<div align="center">⁂</div>

[^2_1]: Im-trying-to-build-a-system-for-automating-my-res-2.md


---

# ok, let's figure out whether the architecture will work or needs any modifications based on a real scenario now.

I've passed the viva for my master's thesis, but I want a substantial revision done by this weekend. What I have now includes:

- the viva passed manuscript + reviewers' comments
- the original proposal + reviewers' comments
- snippets of revised draft in free writing or bullet point form:
-- vague directions to be further unpacked, discussed, elaborated
-- placeholders flagging unspecified data/evidence/information required
-- placeholder requiring integration of specific identified theories/evidence (e.g., by properly looking up the exact parts of a theory/evidence and citing them appropriately)
-- near-complete arguments/statements requiring conversion into grammatically correct prose with context-appropriate style/voice
- notebookLM folder with full text files of highly relevant references
- full zotero library (containing references beyond the scope of the thesis)
- hundreds of pages of audits/comments/concept notes/evaluations/strategies for revision generated by Gemini/NotebookLM's deep research, pre-fact-check

Now I have a thorough picture of both your system and your immediate situation. Let me give you a focused, honest analysis.

This is a concrete stress-test of the architecture — and it immediately reveals both what works and what doesn't. Let me map your actual inputs against the tools available.

***

## What You Have vs. What the Architecture Expects

Your revision task is fundamentally a **multi-source synthesis + citation-grounded prose generation** problem under a hard deadline. Let's be specific about your input types:


| What you have | Its role in the revision | Architecture tool that handles it |
| :-- | :-- | :-- |
| Passed manuscript + viva comments | Ground truth + explicit change requests | Human-controlled: your editorial authority |
| Original proposal + reviewers' comments | Scope definition, argument lineage | Context for `academic-writing-skills` |
| Free-writing / bullet snippets with placeholders | Raw material requiring prose conversion | `academic-writing-skills` + `paper-memory-builder` |
| NotebookLM folder (full-text references) | Factual/citation reservoir | `notebooklm-brief-verifier` + direct Zotero lookup |
| Full Zotero library | Citation verification, exact passage lookup | `zotero-skills` |
| Hundreds of pages of Gemini/NLM audit notes | Pre-fact-checked analysis, revision strategies | **Critical bottleneck — see below** |


***

## The Critical Architecture Problem for This Task

The architecture as designed is **optimized for new research ingestion**, not for **revision convergence under deadline pressure**. Here's where it breaks down for your scenario:

**Problem 1: The Gemini/NLM audit notes are in status `ai-draft` — but you need them *now*, not after a weekly review cycle.** Your governance model says no `ai-draft` content feeds future syntheses. This is correct for long-term library management but creates a bottleneck when hundreds of pages of pre-generated audit material are your *starting point*, not a peripheral asset. The architecture needs a bypass mode for materials you've already reviewed at a meta-level.[^3_1]

**Problem 2: Your placeholders require two distinct operations the architecture doesn't cleanly separate:**

- **Type A placeholders** ("vague direction to unpack") — these are generative: Claude reasons from existing notes + references to build an argument. `academic-writing-skills` handles this.
- **Type B placeholders** ("find exact passage from Theory X and cite correctly") — these are *lookup and verify* tasks. They require Zotero's full-text attachments, and critically, the *verification loop* is mandatory before the text goes into a thesis. The `notebooklm-brief-verifier` skill covers this — but only if the source files are already in your NotebookLM bundle .

**Problem 3: The `academic-writing-skills` skill works paragraph-by-paragraph, but your snippets are scattered fragments.** You need a *pre-assembly* pass that maps every snippet to its thesis chapter/section before prose-conversion begins. Otherwise Claude will draft beautifully but you'll spend hours re-placing material. This is a **missing workflow step** in both WenyuChiou's architecture and your V1 spec.[^3_1]

***

## The Modified Workflow for This Weekend

Here's how to adapt the architecture to your actual situation:

### Phase 0 — Context Assembly (~2–3 hours, tonight/tomorrow morning)

Before invoking any skill, you need one master context document. In Claude Code or your Mac agent, run a custom **`agent compile-revision`** that produces a single Markdown file containing:

- All viva + proposal comments, each tagged by `chapter` and `change_type` (add/remove/expand/cite)
- All your free-writing snippets, each tagged by `chapter`, `placeholder_type` (generative / lookup / prose-conversion), and `priority` (mandatory/optional)
- A map from each lookup placeholder to the specific reference in Zotero/NotebookLM that satisfies it

This is your **revision manifest** — the equivalent of `design_brief.md` in WenyuChiou's Stage 3a . Everything else runs against this document.

### Phase 1 — Citation Resolution (parallel with Phase 0)

For every Type B placeholder (specific theory/evidence lookup), use `zotero-skills` to pull the exact item, locate the relevant passage in the attachment, and insert the correct citekey + quotation/paraphrase into the snippet. This must happen **before** prose conversion, or Claude will hallucinate plausible-sounding citations.[^3_1]

Crucially: your Gemini audit notes almost certainly contain candidate citations for these placeholders. Treat those notes as `status: human-reviewed-but-unverified` — promote them to a temporary `revision-staging` status that the agent is allowed to read, but flag each citation for Zotero verification before final commit.

### Phase 2 — Prose Conversion by Chapter

With the manifest and verified citations in hand, invoke `academic-writing-skills` chapter by chapter, passing:

- The relevant snippets for that chapter
- The viva/reviewer comments for that chapter
- The style context (thesis register, your voice conventions from prior chapters)
- The verified citations as ground truth

This is where `paper-memory-builder` also earns its place: it extracts `.paper/claims.yml` from your passed manuscript so the prose-conversion agent can see what claims are already established and avoid redundancy or contradiction .

### Phase 3 — Coherence + Compliance Pass

Once chapters have draft prose, run `academic-writing-skills` again — this time not for prose conversion but for:

- Reviewer-response compliance (does each changed section actually address the specific comment?)
- Claim-evidence audit (do all Type A expansions have supporting citations?)
- Banned-word / register check (your thesis voice vs. your SNS voice are different — the skill catches drift)

***

## The One Modification the Architecture Needs

Add a **`revision-staging` status** between `ai-draft` and `human-review` in your YAML schema. This is specifically for Gemini/NLM outputs that you have already read and assessed at the meta-level (you know roughly what's in those hundreds of pages) but haven't line-verified. The rule:

- `revision-staging` notes *may* be read by the agent as candidate material
- The agent must flag every factual claim from `revision-staging` sources for Zotero verification before insertion
- Once you've spot-checked a section, it moves to `human-review` → `canonical` as normal[^3_1]

This unblocks your immediate task without breaking the governance model — it just makes the trust levels more granular than binary `ai-draft` / `canonical`.

***

## Honest Deadline Assessment

Given it is now Wednesday 1AM and your deadline is this weekend: the architecture is workable, but only if you skip Phase 0 setup and instead do the revision manifest manually (paste your snippet categories into a structured doc yourself in ~2–3 hours). The tools — `academic-writing-skills`, `zotero-skills`, `paper-memory-builder` — are all available and directly applicable. The bottleneck is not the AI tools. It is the **triage and sequencing of your existing material** before the tools can run efficiently.

What would help most right now is knowing: how many chapters are affected, and what proportion of your placeholders are Type B (lookup) vs. Type A (generative expansion)?

<div align="center">⁂</div>

[^3_1]: Im-trying-to-build-a-system-for-automating-my-res-2.md


---

# guide me through the easiest setup process of the modified pipeline (utilizing WenyuChiou with customizations tailored to my needs) for Claude code. let's postpone the dedrm, audiobook, multioutput (social media, grey literature, etc), mac (hermes agent), and das processes for later.

The full setup guide is attached above as a downloadable Markdown file. Here's the summary of what it covers and the key decisions I made for your situation:

## What the Guide Does

**7 steps, roughly 1.5 hours total** if you work straight through. The thesis revision tasks (Steps 1–6) are the priority — Step 7 (GitHub sync for iOS) can wait until after the weekend .

## Key Customizations from the Standard WenyuChiou Install

**Persona choice:** The guide uses `humanities` rather than `researcher` when running `research-hub setup`, because that persona uses Zotero + qualitative-friendly defaults without code-repo assumptions — much closer to your interpretive/theoretical work .

**`CLAUDE.md` with `revision-staging` status:** This is the modification we identified earlier. Your hundreds of pages of Gemini/NLM audit notes get a dedicated status between `ai-draft` and `human-review`, so Claude can read them as candidate material while still being required to tag every factual claim with `[VERIFY]` before it touches your thesis.[^4_1]

**The revision manifest template (Step 5):** This is the pre-assembly step WenyuChiou doesn't have. Filling in the chapter × change-type × placeholder-type table yourself (30–45 min) is the single highest-ROI action before you start any AI-assisted drafting — it stops Claude from producing well-written prose that lands in the wrong chapter .

**`ThesisRevision/` folder with explicit temporal scope:** The CLAUDE.md includes a `Thesis Revision Special Rules` block with a hard deadline date (`2026-05-03`), which you can delete once the revision is submitted. This keeps the governance rules for the one-off revision task separate from the permanent vault rules.

The first command to run once you're inside Claude Code is `paper-memory-builder` on your viva-passed manuscript — that builds the claims map that prevents every subsequent draft from contradicting or restating arguments you've already established .

<div align="center">⁂</div>

[^4_1]: Im-trying-to-build-a-system-for-automating-my-res-2.md

