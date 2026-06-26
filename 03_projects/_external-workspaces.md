---
type: project-hub
author: ai
status: ai-draft
created: 2026-06-25
summary: Index of external Claude-Code working dirs under P:\_AI agents — knowledge pulled in vs code left in place.
tags: [external-ai, index]
---
# External AI-agent workspaces (`P:\_AI agents`)

> Built by the overnight integration pass. These dirs live OUTSIDE the vault (used by other live Claude Code threads). Per the firewall + single-writer rules: knowledge is **copied** out (originals untouched); code/heavy dirs are **left in place** and linked here. Never copy `.env` / `.conversation-archives` / build outputs.

## Knowledge copied into the vault
- Career strategy (Perplexity) → [[career-strategy (perplexity)]] · in `06_agent-out`, `author: ai` — review & promote
- Awakening rebranding (Adler×Claude) → [[awakening-rebranding 2026-06-20]]
- Author website + domain research → [[author-website-strategy]], [[website domain-cost research]]

## Code / heavy workspaces — LEFT IN PLACE (link, don't absorb)
- **translation/** — PPTX→JA translation tool (Python + ~146 MB assets). Reusable: the glossary `翻訳対照表`.
- **fellowship-applications/** — multi-agent application pipeline (Python + `.env` secrets — never copy). Reusable: `profile/references/` theory papers (配分依存論), bio.
- **115推拿考試/** — tui-na exam-prep generator (Python + 377 audio cards). Reusable study notes: `複習系統/00_導讀與9天排程.md`, `01_背誦聖經_逐字稿與口訣.md`.
- **interviews/2026g0vsummit/** — g0v Summit talk. Human note worth pulling in: `楊逸帆_講綱_公民行動的永續性.md`.
- **full-research-workflow/** — already symlinked into the vault.

## To decide (morning)
Which reusable knowledge to pull in + where: theory papers → `11_myconcepts` or Zotero; talk outline → `03_projects`; 115 study notes → `03_projects`.
