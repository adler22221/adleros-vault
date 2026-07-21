---
author: agent:v2-setup
status: ai-draft
date: 2026-07-21
tags: [handoff, config-sync, action-needed]
---
# 🔑 One 2-minute step: paste the Cubi read-only deploy key on GitHub

Claude config (write-firewall + coaching skills) now lives in the **adleros-ops** repo and auto-installs on every machine. The Cubi checks every 30 minutes but cannot see the repo until you grant it read access:

1. Open: https://github.com/adler22221/adleros-ops/settings/keys/new
2. Title: `cubi-readonly`
3. Key — paste this exactly (it is a public key, safe to handle anywhere):

```
ssh-ed25519 AAAAC3NzaC1lZDI1NTE5AAAAIDLjvnL5WKxnekJHnm75iyvRVkvN8/Q8H8HEasPfuwia cubi-adleros-ops-readonly
```

4. Leave **"Allow write access" UNCHECKED** (read-only is the point).
5. Done. Within 30 minutes the Cubi clones the repo, installs the firewall + skills from it, and from then on every config edit you (or a session) push to the repo reaches both machines automatically.

*Log to check later if curious: `~/adleros-ops-autopull.log` on the Cubi — it should flip from "waiting for deploy key access" to "BOOTSTRAP: cloned + installed".*
