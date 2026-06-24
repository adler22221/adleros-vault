# Claude Code Research Pipeline — Setup Guide
### Customized for Thesis Revision + Long-term Research Workflow
*Scope: Lenovo ThinkBook (Windows 11) · Zotero · Obsidian · NotebookLM · Claude Code*
*Deferred: DeDRM, audiobooks, multi-output publishing, Mac/Hermes agent, DAS*

---

## Before You Start — What You Need

- [ ] **Claude Code** installed (`npm install -g @anthropic-ai/claude-code` or via https://claude.ai/code)
- [ ] **Zotero 7** desktop app installed
- [ ] **Obsidian** installed, vault already set up (your `2ndbrain` or new vault)
- [ ] **Python 3.10+** on your PATH (`python --version` to check)
- [ ] **Git** installed (`git --version` to check)
- [ ] A terminal open in Windows — use **PowerShell** or **Git Bash** (recommended)
- [ ] GitHub account with a private repo ready for your vault (or create one now)

> **If you're doing the thesis revision this weekend:** Complete Steps 1–4 today (≈1.5 hours total). That's all you need to start working.

---

## Step 1 — Enable Zotero Local API

This is the only thing you must configure inside Zotero before any skills work.

1. Open Zotero 7 desktop
2. Go to **Edit → Settings → Advanced**
3. Check **"Allow other applications on this computer to communicate with Zotero"**
4. Leave the port at default `23119`
5. Keep Zotero running in the background whenever you use Claude Code

**Verify it works:**
```powershell
curl http://localhost:23119/api/users/0/items?limit=1
```
You should see JSON. If you see a connection refused error, Zotero isn't running or the setting wasn't saved.

---

## Step 2 — Install Claude Code Skills

Open a terminal (PowerShell or Git Bash). Run these commands in order.

### 2a. Install `research-hub-pipeline` (the core engine)

```bash
pip install research-hub-pipeline
```

Then run the interactive setup. Choose persona **`humanities`** — it uses Zotero + qualitative-friendly defaults, which fits your interpretive/theoretical work:

```bash
research-hub setup --persona humanities
```

The setup wizard will ask you:
- **Zotero default collection** — type the name of your main collection (e.g., `Thesis` or just press Enter to skip and use the root library)
- **NotebookLM login** — type `yes` if you want to connect it now; `no` to skip (you can always re-run `research-hub setup` later)

This installs **9 skills** into `~/.claude/skills/`:
`research-hub`, `literature-triage-matrix`, `notebooklm-brief-verifier`,
`zotero-library-curator`, `research-design-helper`, `research-context-compressor`,
`research-project-orienter`, `research-hub-multi-ai`, `paper-memory-builder`

### 2b. Install `academic-writing-skills`

```bash
git clone https://github.com/WenyuChiou/academic-writing-skills ~/.claude/skills/academic-writing-skills
```

### 2c. Install `zotero-skills` (deep CRUD — for housekeeping tasks)

```bash
git clone https://github.com/WenyuChiou/zotero-skills ~/.claude/skills/zotero-skills
```

### 2d. Install `gemini-delegate` (for CJK output and long-context tasks later)

```bash
git clone https://github.com/WenyuChiou/gemini-delegate-skill ~/.claude/skills/gemini-delegate-skill
```

### Verify everything installed

```bash
ls ~/.claude/skills/
```

You should see these folders:
```
academic-writing-skills/
gemini-delegate-skill/
paper-memory-builder/
research-context-compressor/
research-design-helper/
research-hub/
research-hub-multi-ai/
research-project-orienter/
zotero-library-curator/
zotero-skills/
literature-triage-matrix/
notebooklm-brief-verifier/
```

> **Windows path note:** On Windows, `~/.claude/` resolves to `C:\Users\<YourName>\.claude\`. If Git Bash doesn't expand `~` correctly, use the full path explicitly.

---

## Step 3 — Create Your Vault Structure

If you already have an Obsidian vault, add these folders to it. If starting fresh, create the vault folder first.

```
your-vault/
├── 00Inbox/          ← mobile captures, unsorted refs, quick notes
├── 10Literature/     ← populated ONLY by Zotero Integration plugin
├── 20Wiki/           ← permanent concept pages, theory pages, project hubs
├── 30Drafts/         ← ALL AI-generated outputs land here first
├── .research/        ← auto-created by Claude Code skills (manifests)
└── CLAUDE.md         ← your rules file (created in Step 4)
```

**In Obsidian**, also install these plugins (Settings → Community plugins):
- **Zotero Integration** (by mgmeyers) — required for 10Literature sync
- **Dataview** — required for live wiki pages
- **Obsidian Git** — required for Windows ↔ iOS sync via GitHub
- **Canvas** — usually pre-installed; needed for concept mapping

---

## Step 4 — Create Your CLAUDE.md Rules File

This is the most important customization. `CLAUDE.md` tells Claude Code how your vault works, what statuses mean, and what it is and isn't allowed to do autonomously. Create it at the **root of your vault**.

```bash
# Navigate to your vault root first, e.g.:
cd "C:/Users/YourName/Documents/your-vault"
```

Then create the file with this content (edit the capitalized fields to match your actual project names):

---

```markdown
# CLAUDE.md — Rules of the Library
# Read this file before touching anything in this vault.

## Vault Layout
- 00Inbox: raw captures, unsorted. Agent may read + process. Never write directly here.
- 10Literature: literature notes only. Populated by Zotero Integration plugin template.
  Agent may write here ONLY via `agent compile`.
- 20Wiki: permanent knowledge base. Agent may SUGGEST edits but must show diff first.
  Only notes with status: canonical or status: published may feed future syntheses.
- 30Drafts: ALL agent-generated outputs go here. Always status: ai-draft on creation.
- .research/: manifest files auto-written by research-context-compressor. Do not edit manually.

## YAML Frontmatter Schema
Every note must begin with this frontmatter (use only relevant fields):

---
aliases: []
type: literature | concept | draft | project-hub | daily-digest
project: allocation-dependence | japan-study-tour-2026 | ronbun-hakase | master-thesis
topic: []          # e.g. [allocation, dependency-mode, prefigurative-academia]
status: ai-draft | revision-staging | human-review | canonical | published
target: academic-journal | grant-proposal | sns | thesis
source-notes: []   # citekeys or note filenames this draft draws from
summary: ""        # 1-2 sentence human-written description
---

## Status Rules (ENFORCE STRICTLY)
- ai-draft: Agent output. NOT a reliable source. Never cite in future syntheses.
- revision-staging: Gemini/NLM audit material already read at meta-level by human.
  Agent MAY read as candidate material. Must flag every factual claim for Zotero verification before inserting into thesis.
- human-review: Human has read + assessed. Agent may use as reference with caution.
- canonical: Human has verified and accepted. Agent may use freely as a source.
- published: Finalized and released externally.

## Allowed Status Transitions (AGENT ENFORCES)
- ai-draft → human-review (human only, never agent)
- revision-staging → human-review (human only)
- human-review → canonical (human only)
- canonical → published (human only)
- FORBIDDEN: ai-draft → canonical (must pass through human-review)
- FORBIDDEN: Agent using ai-draft or revision-staging as source without flagging

## The Four Canonical Commands
When user says one of these phrases, execute the corresponding workflow:

**agent ingest**
- Sweep 00Inbox for new captures
- Use vision/text extraction to identify candidate DOIs/ISBNs
- Push to Zotero "Needs Review" collection (tag: needs-review)
- DO NOT auto-file into main library
- Create summary note in 00Inbox with candidate matches for human review

**agent compile [citekey or note name]**
- Read the specified Zotero item or 10Literature note
- Extract: research question, methods, key findings, relevance to active projects
- Write structured note to 10Literature/ with status: ai-draft
- Append "Candidate Links" section (suggestions only, do not modify existing notes)
- Format: markdown with YAML frontmatter per schema above

**agent digest [today | week]**
- Parse vault for notes updated in the specified period
- Summarize new literature by project
- List candidate concept-concept links for human review
- Write output to 00Inbox/DailyDigest-YYYY-MM-DD.md with status: ai-draft
- Append one line to .research/automation-log.md with timestamp + status

**agent draft --type [academic | grant | thesis] --topic [topic or note list]**
- Read style guide note for the specified type from 20Wiki/Style-[type].md if it exists
- Read ONLY canonical or human-review status notes as source material
- If using revision-staging material, flag every factual claim inline with [VERIFY: citekey]
- Write output to 30Drafts/ with status: ai-draft
- Include source-notes list in frontmatter linking back to all source material used

## Thesis Revision Special Rules (active until: 2026-05-03)
- Gemini/NLM audit notes in the ThesisRevision/ folder have status: revision-staging
- Agent MAY read these as candidate material for thesis revision tasks
- Every factual claim or citation sourced from revision-staging MUST be tagged [VERIFY]
- The thesis manuscript itself (status: canonical) is the ground truth
- Viva comments and reviewer comments are authoritative change instructions

## Style Guides (to be created in 20Wiki/)
- Style-academic.md: formal peer-review register, citation format, JASA conventions
- Style-thesis.md: thesis voice, committee conventions, discipline-specific norms
- Style-grant.md: government/youth innovation proposal format, persuasive structure
- Style-sns.md: Daoist/Zen framing, Zhuangzi references, response-able awareness voice
  (Deferred — create when social media publishing workflow is activated)

## What Agent Must NEVER Do Without Asking First
- Modify any note with status: canonical or published
- Delete any file
- Add backlinks to existing notes in 20Wiki (suggest only, show diff)
- Submit anything to Zotero main library without human review of metadata
- Infer citations not present in Zotero or the provided source bundle
```

---

Save this file as `CLAUDE.md` at your vault root.

---

## Step 5 — Set Up Thesis Revision Folder

For this weekend's task specifically, create a dedicated folder structure:

```
your-vault/
└── ThesisRevision/
    ├── 00-manifest.md           ← YOU fill this in (see template below)
    ├── manuscript-viva-passed/  ← paste or link your passed manuscript
    ├── reviewers-comments/      ← viva comments + proposal comments
    ├── snippets/                ← your free-writing, bullets, placeholders
    └── audit-notes/             ← Gemini/NLM audit material (status: revision-staging)
```

### Revision Manifest Template

Create `ThesisRevision/00-manifest.md` and fill it in:

```markdown
---
type: project-hub
project: master-thesis
status: canonical
summary: "Revision manifest for post-viva thesis submission. Deadline: 2026-05-04."
---

# Thesis Revision Manifest

## Chapters and Change Map
| Chapter | Viva Comment | Change Type | Placeholder Type | Priority | Status |
|---------|-------------|-------------|-----------------|----------|--------|
| Ch1 Intro | [paste comment] | expand | generative | high | todo |
| Ch2 Lit Review | [paste comment] | cite | lookup | high | todo |
| Ch3 Method | [paste comment] | prose-conversion | none | medium | todo |
| ... | | | | | |

## Placeholder Type Key
- **generative**: Vague direction — agent expands using theory + sources
- **lookup**: Specific theory/evidence — agent finds exact passage + citekey in Zotero
- **prose-conversion**: Near-complete argument — agent converts to grammatical prose

## Active References (NotebookLM Bundle)
List the filenames in your NotebookLM folder that are relevant to this revision:
- [list them here]

## Zotero Citekeys Confirmed Present
List any citekeys you already know you need:
- [list them here]

## Revision-Staging Sources
Gemini/NLM audit notes in audit-notes/ folder.
Status: revision-staging. All claims require [VERIFY] tagging before insertion.
```

Fill in the chapter table yourself — this takes about 30–45 minutes and is the most important single investment you can make before asking Claude to do anything.

---

## Step 6 — Open Claude Code and Run First Session

Navigate to your vault in the terminal, then start Claude Code:

```bash
cd "C:/Users/YourName/Documents/your-vault"
claude
```

Claude Code will read your `CLAUDE.md` automatically. Test that the skills loaded:

```
> Orient me — what is this repo about?
```

This triggers `research-project-orienter`. If it responds with a coherent summary of your vault structure, the skills are working.

**For the thesis revision, your first real command should be:**

```
> Use paper-memory-builder on the viva-passed manuscript in ThesisRevision/manuscript-viva-passed/
```

This extracts `.paper/claims.yml` from your existing manuscript — a map of what arguments are already established — so all subsequent drafting doesn't contradict or redundantly restate them.

Then, chapter by chapter:

```
> Use academic-writing-skills on Chapter 2. Source material is ThesisRevision/snippets/ch2-snippets.md.
  Reviewer comments are in ThesisRevision/reviewers-comments/ch2-comments.md.
  All lookup placeholders must be verified against Zotero before insertion.
  Output to 30Drafts/ch2-revised.md with status: ai-draft.
```

---

## Step 7 — GitHub Sync (Obsidian ↔ iOS)

*Do this after the thesis revision if time is short. The vault works without sync for desktop-only use.*

1. Create a **private GitHub repository** for your vault
2. In Obsidian, install **Obsidian Git** plugin
3. Configure it: Settings → Obsidian Git → set repo URL, commit interval (e.g., every 10 min auto-commit)
4. Add `.gitignore` to your vault root:

```gitignore
.obsidian/workspace.json
.obsidian/workspace-mobile.json
.obsidian/plugins/obsidian-git/data.json
ThesisRevision/manuscript-viva-passed/**/*.pdf
.DS_Store
```

For iOS sync, install **Working Copy** app and connect it to your GitHub repo. The Obsidian iOS app can open the synced vault folder.

---

## Quick Reference — Skills by Task

| When you say... | Skill triggered | What it does |
|---|---|---|
| "Orient me — what is this repo about?" | `research-project-orienter` | Fast vault summary from .research/ manifests |
| "Compress this project context" | `research-context-compressor` | Writes .research/*.yml manifests |
| "Compare these papers by method and claim" | `literature-triage-matrix` | Comparison matrix without rereading PDFs |
| "Verify this NotebookLM brief against sources" | `notebooklm-brief-verifier` | Cross-checks brief against source bundle |
| "Build paper memory from my manuscript" | `paper-memory-builder` | Extracts claims.yml + figures.yml |
| "Audit my paragraph for banned words / overclaim" | `academic-writing-skills` | Writing audit, humanize pass |
| "Build reviewer response for these comments" | `academic-writing-skills` | Point-by-point rebuttal table |
| "Audit my Zotero for duplicates and orphan tags" | `zotero-library-curator` | Read-only audit + cleanup proposals |
| "agent ingest" | custom (CLAUDE.md) | 00Inbox sweep → Zotero Needs Review |
| "agent compile [item]" | custom (CLAUDE.md) | Zotero item → structured 10Literature note |
| "agent digest today" | custom (CLAUDE.md) | Daily summary of vault changes |
| "agent draft --type thesis --topic ch3" | custom (CLAUDE.md) | Draft from canonical sources → 30Drafts |

---

## What's Deferred (Don't Set Up Yet)

| Component | Why deferred | When to activate |
|---|---|---|
| Mac / Hermes agent | Different machine, separate deployment | After thesis revision |
| DAS cold storage | Hardware not yet set up | After DAS arrives |
| `agent draft --type sns` | Style-sns.md not yet written | When social media workflow begins |
| `agent draft --type grant` | Style-grant.md not yet written | Before next grant deadline |
| `codex-delegate` | No code-heavy tasks in current scope | When quantitative/coding work resumes |
| DeDRM + audiobook pipeline | Separate toolchain | Separate setup session |
| Multi-output publishing | Needs sns/grant style guides first | After thesis |
| `research-hub notebooklm login` | Optional; manual fallback works | Can add anytime |

---

## Troubleshooting

**Skills not triggering:**
Run `ls ~/.claude/skills/` to confirm folders exist. If empty, re-run the git clone commands from Step 2.

**Zotero API not responding:**
Make sure Zotero desktop is open. Re-check Edit → Settings → Advanced for the local API checkbox.

**`research-hub setup` fails:**
Try `pip install --upgrade research-hub-pipeline` first. If Python isn't on PATH in PowerShell, use `py -m pip install research-hub-pipeline` instead.

**Claude Code not reading CLAUDE.md:**
The file must be at the root of the directory where you run `claude`. Confirm with `ls` that CLAUDE.md is in the current folder before launching.

**Windows path issues with `~/.claude/skills/`:**
Replace `~` with `$HOME` in PowerShell, or use the full path `C:\Users\YourName\.claude\skills\`.

