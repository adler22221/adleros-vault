---
author: agent:v2-setup
status: ai-draft
date: 2026-07-20
tags: [handoff, backup, pcloud]
---

# pCloud backup — staged, not yet active

I've set up (but not turned on) automatic nightly backups from adleros-cubi to your pCloud account. Nothing will back up anything, and nothing is scheduled, until you run one command yourself.

## What's staged

- `rclone` and `restic` are installed on the Cubi, under your own user account (no admin/root access was used or needed).
- `~/pcloud-setup.sh` — a script only you should run. It walks you through connecting pCloud, sets a backup passphrase, and turns on the nightly job.
- `~/backup-sensitive.sh` — the actual nightly backup job. It does nothing until the setup script has run.

## The one command to run

SSH or Termius into the Cubi and run:

```
~/pcloud-setup.sh
```

It will ask you questions and pause for your input at each step — nothing runs automatically in the background.

## Connecting to pCloud: two options

The script will ask which one you want:

- **Path A (recommended, easier): from your Windows laptop.** Install rclone on your laptop, run `rclone authorize "pcloud"`, log into pCloud in the browser window that opens, then copy the token it prints and paste it into the script when prompted.
- **Path B: directly on the Cubi via Termius.** Run rclone's interactive config in the same SSH session, name the remote `pcloud`, choose pCloud as the storage type, and follow rclone's on-screen instructions for a browser-less login.

Path A is simpler because your laptop already has a normal browser for the pCloud login page.

## Your pCloud credentials never touch an AI

Your pCloud username/password (or the OAuth token that stands in for them) is typed by you directly into rclone's own prompts. No AI assistant sees, stores, or transmits it — I only wrote the scripts that call rclone; I never ran the authorization step myself.

## What the nightly backup covers

Once you finish the setup script, a cron job runs every night at 3:30am and backs up:

- The Zotero WebDAV attachment store (from the `zotero-webdav` Docker container)
- `~/sensitive/` on the Cubi, if and when that folder exists (safe to skip for now — it's optional)

Old snapshots are pruned automatically (keeping 7 daily, 4 weekly, 6 monthly), so storage doesn't grow forever.

## Where to check on it

Every run appends a dated entry to:

```
~/backup-sensitive.log
```

on the Cubi. Tail that file anytime to confirm backups are actually happening.

---
**UPDATE — easiest path from the phone (PATH C):** run `~/pcloud-webdav-setup.sh` in Termius first (asks for your pCloud email+password directly on the Cubi — no browser, no AI in the loop), then `~/pcloud-setup.sh` finishes the encrypted-backup setup automatically. Note: this path fails if your pCloud account has two-factor auth — then use PATH A from the laptop.

---
**FINAL STATE (2026-07-22, per Adler's decision):** backups are **plain (unencrypted)** for now — encryption is a per-data choice deferred to later. What runs: a nightly 3:30 mirror of the Zotero WebDAV store to `pcloud:adleros-backups/zotero-webdav/current` (browsable in pCloud apps; changed/deleted files are kept in dated `changed/` folders rather than lost). First full mirror started 2026-07-22; ~15k files; progress in `~/backup-nightly.log`. The `~/sensitive` folder is deliberately NOT auto-backed-up — when that data class exists, Adler decides plain vs encrypted (restic + `~/pcloud-setup.sh` remain staged and ready for the encrypted option; no passphrase was created). The pCloud connection itself (EU region) is done and needs nothing further — except rotating the OAuth token that was pasted into chat: pCloud → Settings → Security → Apps → revoke rclone, then run `rclone authorize "pcloud"` on the laptop and update the Cubi with `rclone config update pcloud token ... --non-interactive` (paste the new token only into the Cubi terminal, never into chat).
