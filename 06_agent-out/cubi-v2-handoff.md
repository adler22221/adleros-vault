---
author: agent:v2-setup
status: ai-draft
date: 2026-07-19
tags: [handoff, v2, cubi]
---
# 📱 V2 is live on the Cubi — how to use it from your iPhone

*(Written 2026-07-19 by the laptop session, just before you left. Everything below runs on the Cubi — the laptop can be off.)*

## One-time pairing (do this once, ~2 minutes)
1. On your iPhone, open **Termius** and SSH to the Cubi (same connection you used for the Zotero handoff).
2. Run: `tmux attach -t coach`
   You'll see Claude Code's **Remote Control** screen with a QR code / pairing link.
3. Open the **Claude app** on the iPhone and pair (scan or tap the link).
4. Detach from tmux: `Ctrl-b` then `d`. Done — you never need Termius for this again.

## Daily use (after pairing)
- Open the **Claude app** → your Cubi session is there → type `/bizdev-coach` and start talking.
- When you wrap up, the coach writes a digest to `06_agent-out/bizdev-career/` — it syncs to your phone's Obsidian within moments.
- The digest is a draft (`status: ai-draft`). Promote it into your notes only if it's worth keeping.

## What's now running on the Cubi (no laptop needed)
- **Remote Control session** in tmux (`coach`) — your phone attaches to it.
- **Continuous vault sync** (systemd service) — phone captures and digests move in seconds, not nightly.
- **Write-deny firewall** — agents on this machine physically cannot write into your canon lanes (journal, tasks, projects, ideas, people, reference…; only the inbox + AI lanes are writable). Same rules are live on the laptop.
- Nightly **git archive** of the vault continues (03:00, push to GitHub).

## If something's stuck
- Session gone? In Termius: `tmux new-session -d -s coach -c ~/adleros-sessions "~/.npm-global/bin/claude remote-control"` then attach and re-pair.
- Sync status: `systemctl --user status obsidian-sync` · log: `tail ~/obsidian-sync-continuous.log`

*Next build steps (when you're back or from the phone): the remaining plan items — P1 vault usability sitting, more system skills, qwen3.5:4b on ollama, restic backup. The plan: `08_global-audit/adleros-decision-plan.md`.*

---
**UPDATE (right after setup):** pairing turned out even simpler. The Remote Control server is already connected to your account — just open the **Claude app** on your iPhone (or claude.ai/code) and the **adleros-sessions** environment should be listed; tap it and you are in. The Termius/tmux QR route above is the fallback if it does not appear. Survives Cubi reboots (auto-restarts ~45s after boot).
