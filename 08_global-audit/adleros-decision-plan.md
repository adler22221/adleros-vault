# adlerOS — Plain-Language Decision Plan (v2, web-verified)
*Converted from the 2026-07-07 System 0 audit (`05_blueprint\adleros-orchestrator-audit.md`) + your reprioritization. Written for commenting, not for engineers.*

**Verification note:** you asked that nothing rest on training-knowledge alone. Every technical choice below was checked against live online sources on **2026-07-07** by five research agents (Obsidian docs/changelogs/plugin releases, Claude Code official docs, ollama docs + model libraries, the Hermes/agent ecosystem, backup-tool releases). A second five-agent sweep on **2026-07-19** re-checked the plan against everything that changed in the meantime — other Claude sessions, the live vault, Zotero, the Cubi — before you'd even finished commenting; those findings are woven in as dated notes throughout. Markers: **✓** = my original suggestion verified current · **✱** = changed after checking · **✗** = my original claim was wrong and is corrected here. Key sources are linked inline.

## Why this file exists

An earlier AI session wrote an architecture document for how your Obsidian vault should coordinate all your AI systems. You told us you couldn't evaluate it technically, so we audited it against your own files, your questionnaire answers, and the references you trust. This file translates everything that audit found — plus your three new priorities — into plain decisions you can approve, change, or reject one by one.

## How to comment

Under every item there is a line starting with `→ you:`. Type your response right after it — "agree", "no, because…", a question, anything. **Items you leave blank are treated as "no objection — proceed as written."** You can comment on a few items at a time; nothing gets built from a section until you've had the chance to respond to it.

## The short version

1. Your vault is in better shape than we thought: the big folder reorganization **already happened on June 24–25** (the old docs wrongly said it never ran). What's missing is not structure — it's *usability* (templates, knowing where notes go) and *any live system using it*.
2. About half the architecture document just restates your own design and is fine. The other half needs fixing: two false facts, one privacy mistake, several rules made stricter than you ever asked for, and some machinery too complicated to survive contact with real life.
3. Your new build order rules: **make the vault usable daily → build phone capture → fix the Cubi's role → then the opportunity scorer.**
4. "Hermes agent" is identified: **Hermes Agent by Nous Research** — and it turns out to be a near-perfect fit for your Cubi (details in P2). Two official Claude Code alternatives also now exist.
5. The Cubi isn't broken — it's a low-power machine running a large thinking model, and the numbers suggest it may be running on **one RAM stick instead of two** (P3).
6. Seventeen decisions only you can make are in Part 3. Several build steps depend on them.
7. New from your comments: AI *discussions* are now first-class inputs — each of the nine systems gets a talk-to-it entry point whose session digest files itself into the vault (P1 item 5) — and the iPhone launch problem is solved by keeping standing sessions on the Cubi that your phone attaches to (P2).

**Status re-check (2026-07-19):** twelve days passed between writing this plan and your first round of comments, and things kept moving elsewhere. A five-agent sweep of other Claude sessions, the live vault, Zotero, and the Cubi found: your vault already has a task-management plugin system (TaskNotes) you started actively using on Jul 17 — P1 below is now "configure and integrate," not "build from scratch," and tasks currently split across two folders (new **Q13**); a Zotero-vault bridge plugin (zotflow) is installed but never configured, and the "already wired" research↔Zotero connection this plan assumed is actually dormant (new **D12**, new **Q14**); your Zotero cloud storage expired and a self-hosted replacement is now running on the Cubi, mid-decision (P3 note, new **Q15/Q16**); and a website/brand consolidation was decided and partly executed the same evening as the audit, which needs an owner among the nine systems (D11 update, new **Q17**). None of this preempts anything below — it just means a few sections needed updating, and a few new questions joined the list. Skip this box if you'd rather just read the plan.

---

# Part 1 — What we build first (your stated priorities)

## P1. Make the vault usable for everyday life — FIRST

**The problem in your words:** the system is incomplete; you don't know where and how to add notes depending on the situation; nothing fills in templates automatically.

**What we'd build (one sitting):**

1. **A one-page "where does this note go?" guide.** A simple decision list: something that happened today → `01_journal`; something to do → `02_tasks`; a project → `03_projects`; an idea worth growing → `04_ideas`; something about a person → `12_people`; **a discussion with an AI (coaching, thinking-through, planning) → you never file it yourself — see item 5, it files itself**; **anything you're unsure about → `05_collab-inbox` (the inbox is always a correct answer — sorting it later is the system's job, not yours in the moment).** Linked from your `_Home.md` front page.
2. **Automatic templates ✱ — already installed, not something to build.** The 2026-07-19 status re-check found **Templater** and **QuickAdd** have both been installed in your vault since February — you (or an earlier session) already did this part. What's actually missing: Templater's "Folder Templates" feature (which auto-applies a template the instant a note is created in a lane) isn't switched on/configured yet, and the templates you have haven't been audited against what you need. So the work becomes: turn on Folder Templates per lane, write/tidy the actual template files, confirm both plugins are current (still verified actively maintained: Templater last release Jan 2026, QuickAdd ~Jun 2026). Obsidian's built-in template feature still *cannot* auto-apply by folder, and the newer core "Bases" feature can't either — so the plugin route remains correct. ([Templater](https://github.com/SilentVoid13/Templater/releases) · [QuickAdd](https://github.com/chhoumann/quickadd/releases) · [core Templates docs](https://obsidian.md/help/plugins/templates))
   *Two build details we'll respect: templates must use the plural `tags:`/`aliases:` metadata keys (Obsidian dropped the singular forms), and core Templates must not point at the same folder as Templater (double-processing).*
3. **`_Home.md` refreshed as the daily front door:** today's tasks, capture buttons, the guide, and a small "waiting for your approval" list (this replaces the scheduled weekly review the audit found never works for you). Your existing Bases views stay the task/project lens — verified: Bases reads and writes note metadata only, which matches your "tasks are the single source, views are just views" design. **Gantt: you said wanted.** Your own `00_horizons\gantt.md` note (written June 24, before this plan) already names **obsidian-pm** as your intended Phase-2 interactive Gantt plugin over `03_projects` — and the 2026-07-19 review found the current Gantt view renders nothing precisely because that plugin was never installed. So obsidian-pm gets first look, alongside the two we verified independently ([bases-gantt](https://github.com/lhassa8/obsidian-bases-gantt), [Timeline for Bases](https://github.com/TfTHacker/timeline-for-bases)) — we install whichever actually renders your projects; that's the pass/fail test, not which name wins.
4. **A tidy pass, scoped by what an earlier review already found wrong.** A 2026-07-19 check of the live vault turned up specific, concrete debt: inconsistent frontmatter (metadata fields) on task notes, a backlog of files still sitting loose in the vault root, an unresolved pile of 458 saved web-clips, and a calendar view that's blind to anything before April 2023. We fix the root-file backlog and normalize frontmatter while setting up templates (item 2). The webclips backlog and the pre-2023 calendar blind spot are real but bigger — **explicitly out of scope** for this first sitting unless you want them pulled in now.
5. **Conversation homes — where AI discussions live (NEW, from your comment).** You're right that this was missing: much of your input will be *discussions with AI* (e.g., a bizdev/career coaching conversation), and those need a home just like notes do. The design, consistent with your firewall:
   - **Where you talk:** one standing entry point per capacital system — in Claude Code these are slash commands (`/bizdev-coach`, `/research-think`, …), one per system, each loading that system's context (your persona claims, the system spec, the relevant project notes from canon). Same commands work from laptop or phone (see P2 for the phone side).
   - **Where the record goes — automatically, never filed by hand:** at the end of a session, the agent writes a **session digest** into that system's own subfolder of the AI lane — e.g. `06_agent-out/bizdev-career/2026-07-07-coaching.md` — using a fixed template: topic, key points, decisions reached, action items (each linked to `02_tasks`/`03_projects`), open questions, and links to every note touched. Digests sit in the AI lane like any other agent output: visible on `_Home.md`'s approval list, promoted by you if worth keeping, ignorable if not.
   - **Full transcripts** stay in Claude Code's own session history (searchable, resumable — you can continue any past discussion). The vault gets the *distilled* record, not raw logs — this is your own anti-rag "crystal" discipline applied to conversations, and it keeps the vault readable. (If you'd rather also archive full transcripts in the vault, that's Part 3 **Q12**.)
   - **Concurrent sessions never collide:** if two sessions are live at once (say, laptop and Cubi), each writes only its own dated digest file — never edits a shared file — so nothing gets silently overwritten (same discipline as D6's inbox-claiming rule).
   - This is also *how the nine systems integrate in practice*: a coaching discussion produces linked tasks, project updates, and people-notes drafts — all landing as proposals in the AI lane, all routed through the same single promotion gate.
6. **Reconcile the task system you've already started using (NEW, from the 2026-07-19 review).** Since June 25 your vault has had a plugin called **TaskNotes** installed — a proper task/kanban/calendar system built on Bases — and since July 17 you've actually been creating task notes in it. Right now the same task can end up in two places: its own `TaskNotes\Tasks\` folder, and the `02_tasks` lane this plan designed. Before templates and Gantt views go in, we need to pick ONE home for tasks (Part 3 **Q13**) — the loser becomes a view onto the winner, or gets migrated, not a second parallel system.

**What we would NOT do:** no mass reorganizing, no renaming of lanes, no new folders. Usability only.

→ you:

**One embedded question:** is "when in doubt, throw it in the inbox" acceptable as the single rule you have to remember?

→ you:

## P2. Phone → adlerOS pipeline — SECOND ✱ (this section changed the most after web research)

**Two good surprises from verification:**
- The `ob` program already syncing your vault to the Cubi every night turns out to be **Obsidian's official headless Sync client** (open beta, actively released — latest version July 5, 2026). It supports a `--continuous` mode, meaning the Cubi can see your phone captures **within seconds, not next-morning**, if we wrap it in a background service. ([obsidian-headless](https://github.com/obsidianmd/obsidian-headless) · [official docs](https://obsidian.md/help/sync/headless))
- Obsidian's May 2026 mobile update added a **built-in iPhone share-sheet capture** with configurable destinations — the fastest capture path on iOS now needs no plugins at all. ([changelog](https://obsidian.md/changelog/2026-05-28-mobile-v1.13.0/))

**Version 1 (one sitting, no new infrastructure):** capture button/share-sheet on the phone → note lands in `05_collab-inbox` with the right template → syncs everywhere; Cubi switched from nightly to continuous sync so it sees captures live.

**Version 2 — pick a "front door" for talking to your system from the phone.** You said "Claude Code, Hermes agent, or anything." All three real options, verified current:

| Option | What it is | Strengths | Cautions |
|---|---|---|---|
| **A. Hermes Agent** (what you named) | Open-source self-hosted agent daemon by Nous Research; runs in Docker on the Cubi; you talk to it from **Telegram/Signal/WhatsApp**; has a **bundled Obsidian vault skill** and local voice transcription (voice-note capture works offline). Very active: v0.18.0 released Jul 1, 2026. ([repo](https://github.com/nousresearch/hermes-agent) · [Obsidian skill](https://hermes-agent.nousresearch.com/docs/user-guide/skills/bundled/note-taking/note-taking-obsidian)) | Chat-app front door; voice notes; model-agnostic; runs entirely on your hardware | New daemon to operate; its agent must be scoped to write ONLY into the inbox/AI lanes (our firewall rules apply to it too) |
| **B. Claude Code official** | Two shipped features: **Channels** (a Telegram bot that feeds a running Claude Code session on the Cubi, with approve-from-chat) and **Remote Control** (drive a Cubi session from the Claude phone app, with push notifications when your approval is needed). ([Channels](https://code.claude.com/docs/en/channels) · [Remote Control](https://code.claude.com/docs/en/remote-control)) | Stays in one ecosystem; the push-notification approve loop is exactly the "promotion gate on your phone" the architecture wants | Both are research-preview; needs a session kept alive on the Cubi |
| **C. DIY webhook** | Phone share-sheet/Shortcut → HTTPS call over your Tailscale network → tiny receiver on the Cubi appends to the inbox | Zero third-party services, dead simple | Text-only, no conversation |

**Your iPhone constraint, addressed directly (NEW, from your comment):** correct — the Claude iOS app cannot *launch* a Claude Code session out of thin air. The verified workaround inverts the problem: **sessions don't get launched from the phone; they're kept alive on the always-on Cubi, and your phone *attaches* to them.** Concretely: the Cubi runs `claude remote-control` as a standing background service (it supports many concurrent sessions and survives reconnects); you pair your iPhone once by QR code; from then on, opening the Claude app on the phone drops you into the live session — where the per-system slash commands from P1 item 5 work exactly as on the laptop. So "a bizdev coaching discussion from my iPhone" = open Claude app → attached session → `/bizdev-coach` → talk; the digest files itself into the vault (P1 item 5) and syncs everywhere. If the session machine ever needs a nudge, the fallback is one tap in a terminal app over Tailscale SSH — but the standing-service design exists precisely so you shouldn't need that. ([Remote Control docs](https://code.claude.com/docs/en/remote-control)) *(Secondary option: Anthropic's "Dispatch" can spawn sessions from the phone, but only onto a machine running Claude Desktop — your laptop, which must be awake — so the Cubi standing-session route is the dependable one.)*

**Recommendation:** V1 now regardless (it's the foundation all three ride on). For V2, **A and B are not mutually exclusive** — Hermes as the capture/chat front door, Remote Control for the attach-from-iPhone discussions and approvals — but each is its own small setup, so we'd start with ONE. Given your iPhone comment, **B (Remote Control on the Cubi) now looks like the first build**: it directly solves the launch-from-phone problem AND gives you the coaching-discussion surface; Hermes can follow as the quick-capture/voice front door. Either way, one condition holds: every front-door agent gets the same write-restrictions as any other agent.

*(Also checked because it's in your notes: OpenClaw. It had a serious security crisis in early 2026 — 138 CVEs in 63 days, ~12% of its skill marketplace confirmed malicious. It's hardening fast, but Hermes occupies the same niche with a cleaner record. Not recommended as the front door.)*

**🚀 FAST PATH (your call, 2026-07-19): "i want to start running v2 asap."** V2 jumps the queue. The first sitting becomes the **V2 core package** — the minimum set that makes the iPhone coaching loop real: (1) write-deny rules first (D2 — no front door goes live unguarded), (2) `claude remote-control` as a standing service on the Cubi, paired to your iPhone, (3) the first per-system command (`/bizdev-coach`) + the session-digest template + `06_agent-out/bizdev-career/` (P1 item 5's convention, built for one system first), (4) Cubi vault-sync flipped to continuous so digests reach your phone fast. P1's guide/templates and V1 capture polish follow immediately after, informed by how V2 feels in real use. Front door: you didn't explicitly pick A/B/C, but V2-ASAP + the recommendation above means we start with **B (Remote Control)** — say so if you wanted Hermes first.

→ you (if B-first is wrong, or you also want voice capture early):

## P3. The Cubi — fix expectations and setup, not the hardware ✱ (one claim of mine was wrong)

**What the investigation found:** nothing is broken. The model runs inside Docker. Memory is fine. The machine simply is what it is: a low-power mini-PC. Generating text on a CPU means pushing all ~7 GB of the model through the processor *for every single word* — we measured 3.75 words/second, which is this hardware performing normally for this model. The "8 GB RAM is enough" review you read was about whether a model *fits in memory* — never the problem; speed is a different budget entirely.

**Status re-check (2026-07-19):** re-verified fresh, via read-only SSH, that all of P3 below is exactly as open as when we wrote it — no hermes-agent, no new ollama model, no restic, no new cron jobs. Nothing here needs to change. One new fact, though: since July 13 your Zotero cloud storage expired, and the Cubi now also runs a self-hosted Zotero attachment-storage service (Docker, started July 17) — mid-decision on its exact storage layout, with its own separate project and decision log at `C:\adleros`. It isn't competing for the Cubi's disk or memory (841 GB free, RAM unchanged) — it's competing for *your* session time, and it should stay its own tracked line rather than quietly eating sittings meant for P1/P2/P3 (Part 3 **Q16**).

**What we'd do — all details verified against current ollama docs and model libraries:**

1. **✱ Install `qwen3.5:4b` for routine triage work** (~2.5 GB). Verified best current small model for exactly your workload — structured extraction, summaries, classification — and notably strong in Traditional Chinese (201 languages). Expected on your machine: **~7–9 words/sec, i.e. roughly 2–2.4× faster**, and much more in practice because it can run with thinking off. A 2B version runs ~12–15 w/s if we want faster still; `gemma4:e4b` is the verified fallback. ([qwen3.5](https://ollama.com/library/qwen3.5) · [CPU benchmarks](https://www.promptquorum.com/local-llms/best-cpu-only-llm))
2. **✗ Correction to my earlier claim:** I said we could "turn thinking off" on your existing 9B model. **We can't** — verified: that specific community build has reasoning baked into its template, and ollama's off-switch doesn't work on it (its own model card says to strip the thinking output afterward instead). Thinking-off works properly on library-native models like qwen3.5 — one more reason the small model handles the routine work. Your 9B stays for occasional quality-sensitive private jobs, with its thinking output stripped in post-processing. (No smaller model in that same Claude-distilled family exists yet — the maker says one is coming; we'll re-check.) ([ollama thinking docs](https://docs.ollama.com/capabilities/thinking) · [model card](https://huggingface.co/empero-ai/Qwythos-9B-Claude-Mythos-5-1M-GGUF))
3. **✱ New lead on the speed mystery — probably a missing RAM stick.** Verified that CPU generation speed scales almost directly with memory bandwidth, and your measured speed implies ~21 GB/s — which is single-stick territory for this machine (two sticks ≈ double). A community user going from one stick to two measured 1.5 → 4 words/sec. **Concrete step: check whether the Cubi has one or two sticks** (BIOS or the sudo password gets us the answer in one command). If it's one, a ~$40 second stick roughly doubles every model's speed. ([bandwidth analysis](https://www.hardware-corner.net/memory-bandwidth-llm-speed/) · [1→2 stick datapoint](https://github.com/ggml-org/llama.cpp/discussions/3167))
4. **Small verified config fixes:** pin the context window to the 4k–8k band for triage jobs (the "1M context" label on your model doesn't pre-allocate memory, so no emergency there — verified); set the thread count explicitly (~4) since Docker+hybrid-core CPUs mis-detect it; keep the queue single-stream. ([context docs](https://docs.ollama.com/context-length))
5. **Fix its job description:** overnight/queued work only — never live back-and-forth, never bulk. Even at current speed it produces 100,000+ words per night.

→ you:

## P4. Opportunity-fit-scorer — moved BEHIND P1–P3

The audit originally recommended this as the first build. Your priorities override that. It stays in the plan, unchanged, as the first *capacital system* to build once the vault works daily and phone capture exists.

→ you:

---

# Part 2 — Corrections to the architecture document

Each item: what the document says → what's actually true (or what you actually said) → what we'd change it to.

## D1. Fix the false story about your vault (the audit's biggest finding)

**The document says:** your vault reorganization is "stalled at Stage B — staged but never executed," and that's why your systems feel uncoordinated.
**Actually true (checked on disk):** the reorganization **ran on June 24–25**. Your journal lane has 871 files, tasks 1,052, projects 28, ideas 40. What's left over is small: moving your people-notes (1 of 155 moved), archiving old attachments, and two folders that exist under different names than the design doc uses (`10_commonknowledge`/`11_myconcepts` vs the planned `10_knowledge`/`11_frameworks`). The systems feel uncoordinated because **none of the nine planned systems has been built yet** — not because your folders are wrong.
**Change to:** state the true status. Kill "finish the migration" as a standing project (that shape of task — open-ended infrastructure with no deadline and no user — is precisely what your own history shows never gets done). Instead: a lane gets migrated **only when something you're building needs it, in batches of 30 minutes or less**, inside that build's own work session. Also: there are **two different copies** of the architecture document (one in the audit workspace, one in your vault) that disagree with each other — we keep exactly one (your choice, Part 3 Q9) — and we reconcile the two folder names. *(✱ Also folded in: the 2026-07-19 review found the original inventory missed several non-numbered folders that already existed at audit time — `TaskNotes`, `wellnesstracker`, `002_monthviews`, `004_yearviews`, `Projects - Demo Project` — the revised spec's inventory needs to include them.)*

→ you:

## D2. The safety gate exists on paper only ✱ (mechanism now verified against current official docs)

**The document says:** AI agents are physically blocked from writing into your personal lanes ("enforced by hooks, not memory").
**Actually true:** no such blocks exist anywhere — today the rule survives only because the AI remembers being told. Your own design doc explicitly forbids relying on that.
**Change to (verified current mechanism):** Claude Code's official docs confirm the right tool is **deny rules in a settings file** — one rule per protected lane blocks every built-in file-editing tool at once, it overrides any "allow" anywhere, and it works even in permission-skipping modes when paired with a hook. Verified details that matter for you: the rules must be written **twice** — once for the vault's main path and once for its mirror path — because path aliases don't cross-match; and they honestly cover *AI file-editing tools*, not every conceivable program the AI could run — so the manual review checklist stays as the second layer, plus a small read-only violation-scan script run at review time. ([permissions docs](https://code.claude.com/docs/en/permissions) · [hooks guide](https://code.claude.com/docs/en/hooks-guide))
The same restriction discipline applies to whatever P2 front door you pick (Hermes gets folder-scoped write access only).

→ you:

## D3. The approval rules were made stricter than you ever asked

**The document says:** every AI output, forever, in every category, must be personally approved by you before it counts.
**What you actually said (questionnaire):** "depends on the use-case"; strict where it matters institutionally (your book, your voice), expected to loosen elsewhere as quality improves. You even built a 5-level delegation dial (`deleg:` T0–T4) into your own conventions for exactly this.
**Change to:** approval strictness follows your own dial, per note. **Permanently strict:** anything in your voice, anything about people, money, your book, and promotions into your trusted knowledge base. **Batch-approve or spot-check allowed:** low-stakes structured output like tracker rows and regenerated summaries. (Which categories go where is yours to set — Part 3 Q3.)

→ you: **✅ ANSWERED (2026-07-19): "yes, use a tiered system."** Locked in: the `deleg:` dial governs approval strictness. Default category assignment as written above unless you refine it in Q3.

## D4. The people lane — you overruled the audit, with a better design ✱

**The document says:** your people-notes lane (`12_people`) is freely readable by all AI agents.
**The audit said:** your old design doc marked it *sensitive* — so the audit flagged this as a critical error.
**✅ YOUR RULING (2026-07-19), which supersedes both:** *"keep it readable. no sensitive data there. those should be node notes where wikinotes can backlink to; use ai to keep the people node note updated by summarizing the backlinks."*

So the design becomes:
- `12_people` stays **AI-readable**. Each person gets a **node note** — a hub that other notes link *to*; the node note itself is an AI-maintained rollup summarizing what links to it (meetings, tasks, ideas involving that person).
- The safety line moves from the *lane* to the *content rule*: **nothing sensitive ever gets written into `12_people`** — sensitive relational material lives only in the local-only P3 systems (relationship/family), as before. The AI that maintains node notes summarizes backlinks; it doesn't import private material.
- The AI-updates-the-node-note loop runs at your D3 dial's "AI executes, you spot-check" tier — one of the first live uses of the tiered gate.
- The revised spec drops the "sensitive, flag-gated" classification for `12_people` and documents this node-note design instead (your old `vault-map.md` note gets updated to match — it's the one that called the lane sensitive).

→ you (only if this restatement got your intent wrong):

## D5. Can AI read what AI wrote? The document contradicts itself

**The document says:** AI output is "never read back as a source" — but the same document's own tracker and digest features require agents to re-read files that AI wrote.
**Change to:** split the rule in two plain parts. (1) Agents **may** re-read AI-written working files to keep track of things — count them, update them, summarize them. (2) Agents **may not** treat AI-written *claims* as established facts in anything headed for your trusted notes, unless the claim is tagged as needing verification. And the flashy "systems automatically feed each other" idea in the document gets an honest caveat: under your rules, nothing flows between systems until *you* approve it — so either you accept being that bottleneck, or you allow a small exception (Part 3 Q4).

→ you: **✅ ANSWERED (2026-07-19): "yes."** The two-part rule is locked in. (Q4 — whether to allow the narrow structured-signals exception — is still yours to call.)

## D6. The dispatch machinery: simpler, later, safer ✱ (one nuance updated from current docs)

*(Context, since you said you lost track: "dispatch" is the machinery that notices a new item — a phone capture, a note in the inbox — and routes it to the right agent without you doing anything. It's the plumbing between "you captured something" (P2) and "the right system worked on it." The original architecture document proposed an always-on daily robot manager for this; these four fixes shrink that to something that will actually survive.)*

Four related fixes to the "how work gets routed" section:

- **Daily robot manager → weekly or on-demand.** The document wants a scheduled agent running every day. Your sleep pattern and history say a daily anything becomes guilt-debt (Part 3 Q8 decides the cadence). It also shouldn't exist at all until at least two real systems are running — until then it manages nothing.
- **"Events trigger agents automatically" → scheduled check-ins.** Verified against the current docs: Claude Code did add a file-watching trigger recently, but it only works *inside an already-running session on specifically named files* — there is still no "new email/note wakes an agent" capability, and building one means a standing watcher daemon (the project that already died once). A simple scheduled check ("anything new in the inbox?") gives the same result at your volume. ([hooks reference](https://code.claude.com/docs/en/hooks))
- **Sensitivity decided at capture, not after.** The document has a cloud AI read each new item to decide whether it's too sensitive for cloud AI — which means the sensitive thing was already read. Instead: a separate capture channel for sensitive items that goes straight to the Cubi, and the normal inbox declared non-sensitive by definition.
- **A "claimed" marker on inbox items.** Without one, two agents can process the same item twice, or overwrite each other's updates. Fix: processing an item *moves* it to a `processed` folder (a move can't half-happen, so it doubles as a lock), and each machine writes only its own tracker file.

→ you: **✅ ANSWERED (2026-07-19): "sounds generally fine"** (context you asked for is now at the top of this section). One note: your Q8 answer chose a **daily** digest, which overrides the first bullet's "weekly" lean — see Q8.

## D7. The name "T3" means two opposite things

In *your* conventions, T3 = "AI executes, I approve" (your default delegation level). In the audit documents, T3 = "most sensitive data." Same label, opposite feelings. **Change to:** privacy levels get renamed **P0–P3** everywhere, so the two scales can never be confused. (Part 3 Q10 — cheap to do now, expensive to untangle later.)

→ you:

## D8. Two silent data risks ✱ (both sharpened by verification)

- **The double-sync on your vault is now *officially* discouraged.** Obsidian's own help pages state plainly: don't run Obsidian Sync alongside a cloud-storage service on the same folder — it causes duplicate files, duplicated note sections, and (in the worst reported cases) corruption. Your vault currently has **two live sync authorities**: Obsidian Sync and the pCloud mirror. This is no longer just our caution — it's the vendor's. **Proposed change:** pCloud stops live-mirroring the vault and becomes a one-way scheduled backup destination instead (same protection, no write-conflicts). This changes your current setup, so it's now its own question — Part 3 **Q11**. ([Obsidian guidance](https://obsidian.md/help/sync/switch) · [conflict reports](https://forum.obsidian.md/t/obsidian-sync-incorrectly-duplicates-sections-of-files/94732))
- **Your most sensitive data is the only data with zero backup.** The plan deliberately keeps it off every sync service — but as written, one dead Cubi disk = total loss. **✱ Change (tool updated after verification):** nightly encrypted backup using **restic** — the current standard for exactly this (encrypts on the machine before anything leaves it, keeps a history of versions, prunes old ones automatically, actively maintained — new release two days ago — and can push to an external disk or to pCloud). My earlier "7z or age" suggestion works but is worse on every count; replaced. ([restic](https://github.com/restic/restic/releases) · Part 3 Q7 picks the destination.)
- *(Cubi write path — one device, one folder — unchanged from before; and the Cubi's nightly vault→GitHub archive gets a small ignore-list fix so app-window noise stops polluting its history.)*
- **✱ (NEW, 2026-07-19) The Zotero project is planning its own backup, separately.** Its own decision log (`C:\adleros`) plans an rclone-to-pCloud mirror for the WebDAV store — not yet built, decided independently of this plan. Left alone, the Cubi ends up with two backup toolchains and two pCloud write paths, chosen in two different repos — exactly the racing-sync problem this section exists to prevent. **Change:** fold it into the same decision — one restic setup covers both jobs, one deliberate pCloud write path (Q7/Q11 cover this either way).
- **✱ (NEW, 2026-07-19) Secrets, made explicit.** A near-miss on July 14 (a WebDAV password briefly sat in plaintext in a tracked file, caught before it was ever pushed — no actual leak) previews what happens once this plan adds its own long-lived secrets (a restic password, front-door agent tokens). **Rule, stated once so it doesn't have to be re-learned:** every service/backup secret lives in a gitignored env file or your password manager — never in a README, runbook, or committed config — and whatever caught the July 14 near-miss stays mandatory in every adlerOS-adjacent repo.

→ you:

## D9. Reviews attached to what you're already doing — not a weekly appointment

**The document says:** you review pending AI output "at the weekly sitting."
**Your record says:** scheduled periodic reviews are your documented lapse point; your reflection happens when you open a project you currently care about. The digest folder the weekly review depends on has *never contained a file*.
**Change to:** pending approvals surface where your attention already goes — on `_Home.md` and inside the relevant project page — with a hard cap (~1 hour/week total) instead of a fixed appointment. (Part 3 Q5. And if you pick Remote Control in P2, approvals can also reach you as phone push notifications.)

→ you:

## D10. Add the missing half: the thinking layer

The document calls itself your "everyday note-taking system" yet contains **nothing about how notes connect** — no note-links, no maps of content (hub notes that collect a topic — your own convention), no path for ideas to mature from seed to publishable (your `04_ideas` pipeline — which feeds the book that is your #1 mission output). **Change to:** add a section stating plainly: folders control *who may write where*; **knowledge lives in the links between notes**; every AI-written note must carry links; and the ideas-maturing pipeline is the flow all of this ultimately serves. Plus one discipline borrowed from your own research-tool design: summaries get frozen and dated, marked stale when their sources change, and regenerated deliberately — never silently.

→ you:

## D11. The "nine systems" carve-up was never actually yours

The division of your life into nine named systems (research, outreach, opportunities, career, relationships, family, finances, health, operations) was invented by AI sessions. It may be right! But you never signed off. **Change to:** the document labels it as "our proposed carve-up, pending Adler's edit" until you ratify or redraw it. (Part 3 Q2.)

**✱ One thing this carve-up needs to account for (NEW, 2026-07-19):** the evening of the audit, a separate session decided and partly executed a website/brand consolidation — retiring the old WordPress site, moving everything to one site (`adleryang.com`), with a `/lab/` section and multilingual concept pages. Whichever nine (or ten) systems you settle on, one of them needs to own this — it's already live work, not a hypothetical (Part 3 **Q17**).

**✅ Your answer (2026-07-19):** a possible **tenth system — "design/programming system for artifacts"** — owning website construction and working especially closely with Systems 2 (outreach) and 4 (bizdev). The revised spec drafts it as **System 10 — Design & artifact engineering** for your ratification with Q2.

→ you:

## D12. (NEW, 2026-07-19) The research system's "Zotero is already wired" claim doesn't match what's actually running

The research-publication system spec says Zotero-to-Obsidian is "already wired via research-hub" and treats it as a finished foundation. The 2026-07-19 review found otherwise: `research-hub` (the tool the spec names) hasn't been touched since May 27; the 125 citation notes in your vault's `80_reference` folder are a one-time snapshot from June 25 against a Zotero library that now holds over 28,000 items; and a second, different bridge plugin (**zotflow**) is installed in your vault but was never configured. Meanwhile your actual Zotero energy this month went into an emergency WebDAV storage migration (see the P3 note) — a different project entirely. **Change:** before the research system design leans on "Zotero is wired," confirm which bridge is meant to be the real one going forward — `research-hub`, `zotflow`, or the enrichment work being built alongside the WebDAV service (Part 3 **Q14**). Also worth folding in: a bulk import of your existing Calibre ebook library into Zotero was already being planned as part of the WebDAV project — worth deciding whether that's part of this system or stays separate.

→ you: **✅ ANSWERED (2026-07-19): "yes, evaluate the options with latest info and let's decide together."** Research is running now (all three candidates + current mainstream alternatives, with fresh online sources); you'll get a decision-ready comparison, then we pick together.

---

# Part 3 — The seventeen decisions only you can make

**Q1. The June migration.** Did you (or a session you ran) intend it as done? Was the unfinished part (people-notes, old attachments) a decision or an interruption you want picked back up? *(Unlocks: D1's migration list.)*
→ you: **✅ ANSWERED (2026-07-19): "the migration seems to be partial. i see residuals of previous directory architecture."** Confirms D1's approach: no big cleanup project — residuals get absorbed lane-by-lane as each build touches them, ≤30 min at a time.

**Q2. The nine systems.** Does that carve-up match how you think about your life? Merge/split/rename anything? *(Unlocks: D11.)* Here is the full proposed carve-up (you asked to see it again — System 0 is the vault itself, coordinating the nine):

| # | System | What it covers |
|---|---|---|
| 1 | **Operations & ally-coordination** | turning allies' voiced support into distributed, tracked work — the loop-cutter |
| 2 | **Outreach & content** | one authored argument → many formats/languages; voice calibration is its keystone |
| 3 | **Opportunities & applications** | fellowship/funding scanning, fit-scoring, application drafting |
| 4 | **Bizdev & career** | bread income as a managed portfolio — leads, pitches, invoicing, the 推拿 license question |
| 5 | **Research & publication** | Zotero, literature flow, the book, JASA-type academic output |
| 6 | **Health management** | cross-cutting governor: cardiac safety, sleep-phase-aware scheduling (local data) |
| 7 | **Finances** (P3, local-only) | runway model, gnucash, scenario recomputation |
| 8 | **Relationship management** (P3, local-only) | [partner]-runway planning, counselor-session prep |
| 9 | **Family-conflict resolution** (P3, local-only) | two-family burdens, chronologies, briefing material |

*(New since the audit: the `adleryang.com` website — per your Q17 answer, now drafted as a proposed **System 10 — Design & artifact engineering**, tightly coupled to Systems 2 & 4.)*
→ you (ratify the 9+1 carve-up, or merge/split/rename):

**Q3. Approval strictness.** Which AI outputs may be batch-approved or spot-checked, and which must you always read line-by-line? *(Unlocks: D3.)*

*You asked: "what's the current architecture related to this?" — here it is, read fresh from your own conventions (identical in both `P:\adlerOS\ops` and `C:\adleros`):*
- **The dial already exists:** every note can carry a `deleg:` field with five tiers — **T0 solo** (no AI) · **T1 assist** (AI pre-processes, you do the core) · **T2 collab** (AI does sub-steps, you steer) · **T3 review** (AI executes, you approve — *your stated default for new automation*) · **T4 auto** (AI completes routine low-risk work, logged).
- **The promotion ladder:** `ai-draft → revision-staging → human-review → canonical → published`; AI can never move anything past the first two rungs — promotion is yours alone.
- **A hard floor above all tiers:** irreversible or outbound actions (sending anything, git push, deleting files/events) always gate to you, even at T4.
- **Supporting flags:** `human_edited: true` (AI must never overwrite a note you touched), `sensitive: true` (excluded from digests), `[VERIFY:]` tags on unverified AI claims.
- **Reality check:** none of this is machine-enforced yet (that's D2), and almost nothing is automated yet — so today everything is effectively T0–T2 by default. Q3 is deciding, *before* systems go live, which output categories start at which tier.

**Proposed defaults (edit anything):**
| Tier | Output categories |
|---|---|
| **T4 auto** (logged, you spot-check occasionally) | tracker-row updates · regenerated digests · `12_people` node-note rollups (your D4 design) · sync heartbeats |
| **T3 review** (AI does it, you approve) — default | session digests from coaching conversations · opportunity fit-scores · literature notes · drafted (never sent) messages |
| **T2/T1** (you steer or do the core) | anything in your public voice · book-related drafting |
| **T0 / hard floor** (never delegated) | every send/submit · money · canon promotion · relational judgment calls |

→ you:

**Q4. AI reading AI.** May agents read a *small set of structured numbers* from each other's approved output (a savings-runway figure, a workload limit) without your per-item approval — or is that exactly what the firewall exists to prevent? *(Unlocks: D5.)*
→ you:

**Q5. What makes you review.** Has a fixed weekly review ever stuck for a month+? Is it a calendar slot that gets you to review — or opening a project you care about? *(Unlocks: D9.)*
→ you:

**Q6. The Cubi's hand-off.** Should the Cubi write into the vault directly, or hand you results another way (e.g., your phone reads them off the Cubi — which both Hermes and Remote Control would give you for free)? *(Unlocks: D8, P2 v2.)*
→ you:

**Q7. Backup destination for the sensitive-only data.** Encrypted backup on an external disk at home, or an encrypted (unreadable-to-them) backup on pCloud? Both are handled by the same tool (restic); pick by what you trust. *(Unlocks: D8.)*
→ you: **✅ ANSWERED (2026-07-19): encrypted backup on pCloud.** restic → pCloud (encrypted before leaving the machine), one toolchain for both this and the Zotero store per D8.

**Q8. Digest rhythm.** Would a daily digest really get read daily — or pile up as guilt? Is weekly or on-demand the honest answer? *(Unlocks: D6.)*
→ you: **✅ ANSWERED (2026-07-19): "daily, and i think you should utilize gemini notebook (recently renamed from notebook LM) and zotero for that."** Daily it is. **Research came back — here's what's real (all verified with current sources):** the rename to Gemini Notebook is confirmed (July 16, 2026). There is **no official consumer API** — full automation exists only through an unofficial tool (`notebooklm-py`, mature and widely used, but cookie-based and can break whenever Google changes internals) or an Enterprise API needing licenses you don't have. However, Google shipped one crucial supported piece in May: **sources that live in Google Drive auto-refresh in the notebook.** That enables:
- **Option B (recommended start — fully supported, one tap/day):** every night the Cubi compiles a "Research Digest — date" Google Doc from your Zotero deltas (new items via the Zotero Web API + key passages from the WebDAV PDFs) into a standing notebook that auto-refreshes; each morning you open Gemini Notebook on your iPhone and tap once for the Audio Overview or briefing. Nothing can silently break; the cost is one tap.
- **Option A (upgrade if the tap annoys you — fully automated, fragile):** same pipeline, but `notebooklm-py` also triggers generation and downloads the audio/Markdown to a private podcast feed your iPhone picks up before you wake. Needs Google AI Pro (~$20/mo) for quota headroom, and accepts that Google can break it without notice.
- (A fully self-hosted alternative exists — SurfSense/Open Notebook — if you ever want zero Google dependence; noted, not pushed.)
**Proposed: start with B for a week, upgrade to A if the daily tap is friction.** One constraint either way: your 28k-item library can't fit in a notebook (caps are in the hundreds of sources) — the digest feeds on *daily deltas*, which is what a daily digest wants anyway. Blank = B-then-A as described.

**Q9. Which spec copy is canonical** — the audit-workspace one, the one inside your vault, or (✱ new as of 2026-07-19) the actively-maintained ops repo at `C:\adleros` (GitHub `adleros-ops`, its own decision log ADR-001..023), which a note from another session says has already superseded `P:\adlerOS\ops`? Three-way now, not two — we keep one and turn the others into pointers. *(Unlocks: D1. See also Q15.)*
→ you: **✅ ANSWERED (2026-07-19): "i don't know."** Fair — that's ours to untangle: the step-0 reconciliation pass will read all three copies plus `C:\adleros`'s decision log and come back with a concrete recommendation instead of a question.

**Q10. Renaming privacy tiers to P0–P3** so "T3" only ever means your delegation level. OK? *(Unlocks: D7.)*
→ you:

**Q11. (NEW, from verification) Demote pCloud from live vault mirror to one-way backup?** Obsidian officially recommends against two sync services on one folder. Saying yes removes a real corruption risk and loses nothing (pCloud still holds a copy — just written on a schedule instead of racing Obsidian Sync). Saying no keeps your current arrangement, accepting the vendor-documented risk. *(Unlocks: D8.)*
→ you: **✅ ANSWERED (2026-07-19): "ok, but we need a way to make sure that obsidian across devices (ios, laptop, cubi) are always in sync."** That guarantee is exactly what remains once pCloud steps back: **Obsidian Sync becomes the single sync authority on all three devices** — the app on your laptop and iPhone, and the official headless client (`ob`) on the Cubi, flipped to continuous mode so it's always current, not nightly. One authority = no conflicts, and every device sees every change within seconds. pCloud then holds a scheduled one-way backup copy (plus the Cubi's git archive as deep history). Sync health gets a visible check: the Cubi writes a dated heartbeat note after each sync cycle, so "is everything in sync?" is answerable at a glance from any device.

**Q12. (NEW, from your comment) Conversation records: digest-only in the vault, or full transcripts too?** Recommended: digest-only (distilled session notes in the AI lane; full transcripts stay in Claude Code's searchable, resumable history). Alternative: also archive complete transcripts into the vault — everything in one place, at the cost of bulk and noise. *(Unlocks: P1 item 5.)*
→ you: **✅ ANSWERED (2026-07-19): "ok"** — digest-only, locked in.

**Q13. (NEW, 2026-07-19) Where do tasks actually live?** `TaskNotes\Tasks\` (the plugin folder you've been using since July 17) or `02_tasks` (this plan's designed lane) — pick the single source of truth; the other becomes a view or gets migrated. Right now the same task note exists in both places. *(Unlocks: P1 item 6.)*
→ you: **✅ ANSWERED (2026-07-19): `02_tasks`.** Locked in: `02_tasks` is the single source of truth; the TaskNotes plugin gets re-pointed at it (its kanban/calendar/agenda views work over any folder), and the few task notes in `TaskNotes\Tasks\` migrate over in P1's sitting.

**Q14. (NEW, 2026-07-19) Which Zotero-vault bridge is the real one?** `research-hub` (a CLI tool, untouched since May), `zotflow` (an Obsidian plugin, installed but never configured), or the enrichment work being built alongside the new WebDAV service? *(Unlocks: D12.)*
→ you: *"i don't know, check for me"* — **✅ CHECKED (research completed 2026-07-19). Recommendation ready:**
- **Key insight: these aren't three rivals — they're three layers.** `zenrich` (the WebDAV-side work) only enriches the Zotero library itself, never writes to the vault — it complements any bridge. `research-hub` turns out to be a *third-party* open-source tool (not custom-built for you), two major versions behind your local copy, wired to your old pre-adlerOS vault — reviving it would violate the firewall and duplicate zenrich. **ZotFlow is the only actual live bridge candidate** — and your own ops repo already chose it (decision record ADR-014, June 25): very actively maintained (new release *yesterday*), works over the Zotero Web API + your new WebDAV store, does two-way annotation sync.
- **Recommendation: confirm ZotFlow as the bridge — but gated on a small pilot first**, because it's unproven at your library's scale (28k items; there's an open bug about slow startup on big libraries): point it read-only at the library, check speed, check it can reproduce your existing `@citekey` note names, check attachments open on laptop *and* iPhone. Only then does it touch your reference notes — and only on-demand per item, never bulk-generating 28k notes. Meanwhile zenrich gets deployed to the Cubi as the library-side enrichment layer (its own status file already defines the sequence — including one critical test first: whether its file-attach path still works now that Zotero cloud storage expired). `research-hub` is retired as infrastructure; we salvage its two best ideas (the frozen-summary "crystal" discipline, and its NotebookLM automation code as reference for your daily digest).
- Say "confirmed" (or object) and this becomes the decision.

**Q15. (NEW, 2026-07-19) Is `C:\adleros` the real ops repo now?** A note from another session says the old `P:\adlerOS\ops` is superseded and shouldn't be edited anymore. Should the revised architecture spec and this plan's decisions live in `C:\adleros` going forward, with `P:\adlerOS\ops` turned into a pointer? *(Extends Q9.)*
→ you: **✅ ANSWERED (2026-07-19): "i honestly don't know. my intention is to work seamlessly either from my laptop or ios, with all files and all statuses always in sync. since cubi is on 24/7, cubi should at least be able to access all of them."** That requirement decides more than the question asked: it means anything you personally need to *read or decide on* must live **in the vault** (the only layer that reaches your iPhone natively), while machine-side code/config can live in a git repo the Cubi holds. The step-0 reconciliation pass will propose the concrete split along exactly that line.

**Q16. (NEW, 2026-07-19) Should the Zotero/WebDAV project get its own tracked line in this plan, or stay fully separate?** It's mid-decision (a storage-layout choice was deferred to keep your phone syncing) and it's running on the same Cubi this plan is trying to right-size. We don't need to run it — just decide whether to coordinate its Cubi footprint and backup choice here, or leave it alone entirely.
→ you: *"what does this entail"* — **plainly:** "its own tracked line" means this plan lists the Zotero project's open items (the deferred storage-layout choice, the zenrich deployment, its backup) as one visible row in the build order, so (a) its Cubi services and backup use the SAME toolchain decided here instead of a second parallel one, and (b) its remaining work gets scheduled deliberately instead of silently eating sittings. It does **not** mean merging the projects or redoing its decisions — its own repo stays in charge of its own choices. "Fully separate" means we only touch the one overlap (the D8 backup merge) and otherwise ignore it. **Recommended: tracked line** — it's already sharing your server, your attention, and now (per Q14) your research system. Blank = we go with the recommendation.

**Q17. (NEW, 2026-07-19) Who owns the website?** The `adleryang.com` consolidation (retiring the old WordPress site, one canonical site, a `/lab/` section) was decided the evening of the audit. Which system should own it when you answer Q2 — outreach, career, or its own line? *(Extends Q2/D11.)*
→ you: **✅ ANSWERED (2026-07-19): "perhaps a design/programming system for artifacts? what i do know is that the website construction system should work closely especially with systems 2 & 4."** Recorded as a proposed **System 10 — Design & artifact engineering**: builds and maintains the things the other systems ship through (the website first; later dashboards, slide decks, interactive artifacts), tightly interlocked with System 2 (outreach supplies the content and voice, S10 supplies the vessel) and System 4 (bizdev's pitches and portfolio live on it). The revised spec will draft its one-page definition for your ratification alongside Q2 — making the carve-up potentially ten systems, not nine.

---

# Part 4 — What stays exactly as it is (not asking, just informing)

1. The vault as the one shared coordination surface — everything reads/writes there, systems never call each other directly (this *is* your design).
2. AI writes quarantined into their own lanes; only you promote things into trusted notes (your entropy-firewall rule).
3. The capture → sort → draft → approve loop (your adopted governance model, unchanged).
4. The lane permission table (once D4's error is fixed).
5. The model-router cost policy (cheap models for bulk, big models where it matters).
6. "Grow it, don't build it" — no big-bang builds, each increment must pay for itself (this becomes the plan's spine).
7. The ~1 hour/week ceiling on your total review load, with the stop-and-shrink rule.

→ you (only if something here bothers you):

---

# After you comment

0. **(NEW, 2026-07-19) A reconciliation pass first.** Before revising anything, we read `C:\adleros`'s decision log (ADR-001..023) and whichever `vault-map.md` copy it's actually built against, so the spec revision isn't built on a stale `P:\adlerOS\ops` file (per Q9/Q15).
1. I fold your comments in and revise the architecture document — **one canonical copy** (per your Q9 choice) — in plain language this time, with every factual claim re-verified on disk or online.
2. The architecture map gets redrawn to match.
3. Then building starts — **reordered by your 2026-07-19 "V2 ASAP" call**: **P2-V2 core (deny rules + Remote Control on Cubi + `/bizdev-coach` + digest pipeline) → P1 vault usability (incl. Q13 task migration) → P2-V1 capture polish → P3 Cubi right-sizing → P4 scorer**, one increment per sitting, each with its own pass/fail check, never starting increment N+1 until N passes.
4. This plan file gets copied into your vault (`08_global-audit`) so you can comment from your phone; comments there or here both count.

# How we'll verify each piece (pass/fail checks)

- **P1:** you create one note of each common type — on the laptop *and* the phone — using nothing but the guide, and the right template auto-fills every time. If you hesitate about where a note goes, the guide failed, not you.
- **P2 v1:** a phone capture takes under 10 seconds, lands in the inbox with correct metadata, and is visible on the Cubi within a minute (continuous sync). **V2:** you send one message from the chosen front door and the note appears in the inbox — and the front-door agent is *blocked* when told to write outside its lanes. **iPhone discussion test:** from your iPhone, you attach to the Cubi session, run `/bizdev-coach`, hold a short real coaching conversation — and its digest appears in `06_agent-out/bizdev-career/` with linked action items, without you filing anything.
- **P3:** `qwen3.5:4b` measures ≥7 words/sec on the Cubi with thinking off; one real overnight queued job completes and its result is readable from your phone in the morning; RAM stick count answered.
- **D2:** an AI agent in a test session tries to write into a protected lane and is *blocked by the deny rule*, not by its own good manners — tested against BOTH vault paths; the manual checklist catches a planted violation until then.
- **Spec revision:** the revised document is diffed against your `vault-map.md` — anywhere they disagree, either the document changes or you've explicitly said the design changed. (First confirm, per Q9/Q15, whether the current `vault-map.md` lives in `P:\adlerOS\ops` or `C:\adleros`.)
