# Archived MOBILE-TROUBLESHOOT entry

Archived: 2026-05-08 17:07 (response written to MOBILE-TROUBLESHOOT-RESPONSE.md the same minute).

---

# MOBILE-TROUBLESHOOT Ã¢â‚¬â€ out-of-band diagnostic channel

> **Purpose:** when LIVE-mode (Claude Code remote-control) is broken and you need me to fix or diagnose from PC-side, write your entry below.
> **The watcher script polls this file every 30 seconds.** When it sees changed content, it spawns a headless Claude on PC that reads the entry, diagnoses, takes action if safe, and writes a response to `MOBILE-TROUBLESHOOT-RESPONSE.md` (which syncs to your iPhone via pCloud).
> **Response time:** typically 60Ã¢â‚¬â€œ120 seconds after you save.
> **After processing:** the watcher archives this file (renames to `MOBILE-TROUBLESHOOT-archive-YYYYMMDD-HHMM.md`) and resets it to this stub so the next entry starts fresh.

---

## Format (replace this section with your entry)

```
## YYYY-MM-DD HH:MM
**What happened:** [what you observed Ã¢â‚¬â€ e.g., "tapped session in Code tab, got 'session offline' badge, waited 5 min, no green dot"]
**What I want:** [diagnose / restart / advise / something else]
```

---

## (your entry goes below Ã¢â‚¬â€ replace this line and everything below it)

KILL-WRAPPER-AND-DIAGNOSE
Action: 
1. Kill process: remote-control-wrapper.ps1 (use Get-Process + Stop-Process)
2. Run: claude remote-control --help | head -20 (show me the actual flag syntax)
3. Check available models: claude list-models (if that command exists)
4. Report back what you find about -m vs --model vs other flags

