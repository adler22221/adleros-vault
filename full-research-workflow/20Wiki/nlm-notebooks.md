---
aliases: [NLM Notebooks, NotebookLM Registry]
type: concept
project: master-thesis
status: canonical
summary: "Human-readable registry of all NotebookLM notebooks used in the thesis research pipeline. Machine-readable source-of-truth: .research/manifests/nlm-notebooks.yml (copied from .research/nlm-notebooks.yml)."
---

# NotebookLM Notebook Registry

> Auth: run `nlm login` in `.venv-nlm` if queries fail.
> Machine-readable config: `.research/nlm-notebooks.yml`

## Thesis-Critical Notebooks

| Notebook | UUID | Purpose | Privacy gate |
|----------|------|---------|-------------|
| **SCU Thesis A-Sources** | `c68ca15e-5a07-4598-a5e0-dd68b9fa73b9` | Citation verification (third-party PDFs from `thesis-sources` Zotero collection) | Zotero `thesis-sources` collection membership only |
| **B-Self** | *(see nlm-notebooks.yml)* | Self-consistency (own published work) | Own published abstracts + OA chapters only |
| **C-Audits** | *(see nlm-notebooks.yml)* | AI audit feedback | AI-generated audit reports only — NEVER reviewer comments |

## Author Notebooks (Thinker-Specific)

| Thinker | UUID | Key query topics |
|---------|------|-----------------|
| **小原秀雄 (Obara Hideo)** | `86e6c0e5-3270-45d3-9844-bf6578c33937` | 人工食物連鎖, 加工の二重性, evolutionary history, artificial world |
| **John R. Searle** | `8186ca58-1448-4746-8967-1fbc7fffbe62` | collective intentionality, status functions, Background, institutional reality |
| **Bernard Stiegler** | `a98a96fc-e308-4ec8-9e91-d04cdfc1dd87` | tertiary retention, grammatization, epiphylogenesis, Epimetheus myth |
| **Yuk Hui** | `47ee1eac-14c6-4500-a776-b8e3daff900b` | cosmotechnics, technodiversity, organizing inorganic, algorithmic governmentality |
| **Watsuji Tetsuro** | *(in A-Sources via c68ca15e)* | 風土 (fūdo), 間柄 (aidagara), climate + human self-objectivation |
| **Husserl** | *(in A-Sources or knowledge-base)* | Lebenswelt, Crisis, Galilean idealisation |

## Hard Exclusions (NEVER upload)
- `ThesisRevision/reviewers-comments/` — local-only; never to Google
- `ThesisRevision/audit-notes/` content mentioning reviewer identities
- Anything NOT in Zotero `thesis-sources` collection

## NLM Citation Format
```
[VERIFY: confirmed | <citekey> | UUID <source-id> | nlm-excerpt:"<short passage>"]
```

---

*Full UUID list and privacy config: see [[.research/manifests/nlm-notebooks.yml]]*
*(Note: .research/ files are accessible in vault but excluded from Obsidian's full-text index for performance.)*
