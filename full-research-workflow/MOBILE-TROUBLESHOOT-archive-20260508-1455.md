# MOBILE-TROUBLESHOOT — out-of-band diagnostic channel

> **Purpose:** when LIVE-mode (Claude Code remote-control) is broken and you need me to fix or diagnose from PC-side, write your entry below.
> **The watcher script polls this file every 30 seconds.** When it sees changed content, it spawns a headless Claude on PC that reads the entry, diagnoses, takes action if safe, and writes a response to `MOBILE-TROUBLESHOOT-RESPONSE.md` (which syncs to your iPhone via pCloud).
> **Response time:** typically 60–120 seconds after you save.
> **After processing:** this file gets archived (renamed `MOBILE-TROUBLESHOOT-archive-YYYYMMDD-HHMM.md`) so the next entry starts fresh.

---

## Format (replace this section with your entry)

```
## YYYY-MM-DD HH:MM
**What happened:** [what you observed — e.g., "tapped session in Code tab, got 'session offline' badge, waited 5 min, no green dot"]
**What I want:** [diagnose / restart / advise / something else]
```

---

## TEST 2026-05-08 14:55
**What happened:** smoke-test entry from iPhone (initial setup test); previously the watcher fired but the headless Claude couldn't write a response because of a permission prompt. Re-run after fix.
**What I want:** confirm the watcher → headless-Claude → response → archive loop works end-to-end now.
