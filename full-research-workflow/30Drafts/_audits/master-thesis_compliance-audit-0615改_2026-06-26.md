---
aliases: []
type: draft
project: master-thesis
topic: [audit, formatting, citations, scu-compliance]
status: ai-draft
target: thesis
source-notes: []
summary: "Independent formatting + citation compliance audit of 楊逸帆碩士論文_2026-06-15-改.docx against the Claude-in-Word handout + SCU master-format. Method: deterministic XML pass + 4-agent independent re-derivation + adversarial refute of every FAIL + completeness critic. 17 confirmed to-fix items; everything else PASS."
---

# Compliance audit — `楊逸帆碩士論文_2026-06-15-改.docx`

**Audited:** 2026-06-26 (file last saved 22:22). **Against:** the Claude-in-Word handout + `ThesisRevision/thesis-formatting/master-format.pdf`.
**Method (trust architecture):** deterministic XML pass (mine) → **4 independent agents re-derived each dimension from the raw bytes** (no anchoring on my numbers) → **a skeptic adversarially tried to refute every FAIL/PARTIAL** → a **completeness critic** hunted for missed dimensions. Where my regex disagreed with the agents, I re-verified by hand (3 cases — all resolved in the document's favour).

> ⚠️ **Two framing facts that change how to read the handout.**
> 1. **The edits are already ACCEPTED, not tracked redlines.** `w:ins=0, w:del=0`, Track Changes OFF. Everything in the handout about "pending redlines / check both states / accept-all" is moot — and **there is no redline left to review or roll back.** The doc *is* the final state.
> 2. **The "199 HIGH-risk font runs" are benign.** 0 CJK runs and **0 accented-Latin runs** are mis-fonted. The remaining ASCII runs carrying `hint="eastAsia"` inherit `ascii = Times New Roman` from the Normal style, so they render TNR. The genuine pinyin risk is fully fixed.

---

## 1. Bottom line

The document is **substantially compliant.** Of ~45 checks, the overwhelming majority **PASS** (fonts, headings, body/footnote sizes, front-matter order, TOC depth, List-of-Tables indents, page-numbering scheme, footnote numbering, all in-text citation forms, the Chicago→author-date conversions, 《》 marks, retrieval-date uniformity, English/Chinese quote rules, margins/A4/spacing, abstracts+keywords, title page, chapter structure, no reviewer-identity leak).

**17 items need action**, grouped below by priority. Only **two are substantive** (an embedded set of authoring comments + one genuinely uncited footnote); the rest are reference-formatting, footnote-style, cleanliness, and deposit-readiness items.

---

## 2. To-fix list (confirmed; survived adversarial verification)

### A. Substantive — do before deposit
| # | Item | Location | Fix |
|---|------|----------|-----|
| A1 | **4 unresolved Word comments still embedded** (authoring TODOs, dated 2026-06-26; all `w15:done=0`) | `comments.xml` ids 184–187, anchored near fn67 | Resolve A2, then **delete all comments** (Review ▸ Delete All Comments). Committee/library must not see TODOs. *(Privacy OK: all authored by 楊逸帆; no committee names leak.)* |
| A2 | **fn67 strings together ~4 direct Hui quotations with NO citation** — the real content gap the `[VERIFY]` comment flags | `footnotes.xml` fn id=67 | **Verify each quote against the source, supply work + page, insert the citation.** Do **not** invent pages (the author explicitly refused). See §4 — I can run this against NotebookLM/Zotero. |

### B. Reference formatting
| # | Item | Location | Fix |
|---|------|----------|-----|
| B1 | **Manik & Wang (2026)** mis-alphabetized (sits after Mignolo) | ref entry after "Mignolo, W. D." | Move to **after Lyons, T. W. / before Matthews, B.** |
| B2 | **"James Watson and Edward O. Wilson: An intellectual entente. (2009)"** stranded in the **W** block | ref entry between Wiener & "World, n." | It's title-led (no author) → file under **J**: move to **after Illich, I. (1975) / before Kant, I.** |
| B3 | **Kant, *Critique of the Power of Judgment*** — book title **not italicized** | Kant (1790/2000) entry | Italicize only `Critique of the Power of Judgment` (leave translator/publisher roman) |
| B4 | **Manik arXiv title** not italicized (sibling Hardjono entry is) | Manik (2026) entry | Italicize `OpenClaw agents on Moltbook: … agent-only social network` (up to `. arXiv:`) for consistency |

### C. Footnote citation normalization (file's own SCU colon form is `(Author, year: page)`)
| # | Item | Location | Fix |
|---|------|----------|-----|
| C1 | `(Bhaskar, 2008, p. 46)` — comma-p. form | fn3 | → `(Bhaskar, 2008: 46)` |
| C2 | bare `p.41 … p.49 … p.51` | fn64 (already opens "Bhaskar (1998):") | → colon form: `(1998: 41) … (1998: 49) … (1998: 51)` |
| C3 | full Chicago note for Lotka (`… Human Biology 17, no. 3 (1945): 167–194, at 188`) | fn54 | → `Lotka (1945: 188)` (1945 already in refs; add a **Lotka 1925** entry only if the note keeps citing 1925) |

### D. Cleanliness (cosmetic, but worth a pass)
| # | Item | Location | Fix |
|---|------|----------|-----|
| D1 | **"SEP" used before it's defined** (full form appears ~119 paras later; never bound) | fn4 (first use) | → `Stanford Encyclopedia of Philosophy [SEP]` at fn4 |
| D2 | **5 doubled spaces** | body: "Stiegler  calls", "1995)  reaches", "of  secreting", "possibilities  —"; fn: "58):  "" | collapse to single space. **Leave** "World   世界" (intentional table alignment) |
| D3 | **4 space-before-punctuation** | "soul ; and", "last . But", "substrate ; for", "flesh . Here" | remove the space. **Don't touch** ".docx" or "!Kung" (false positives) |
| D4 | **9 straight quotes/apostrophes** vs the doc's curly norm | fn12 (Polanyi: "Life's…", "dual control,", apostrophes) + body "one's" | convert to curly “ ” ’ |
| D5 | **Table 4-1 header "Period" set to 1pt** (renders invisible) | Table 4-1 header cell | set the run **and** paragraph mark back to 12pt |

### E. Deposit-readiness (not text edits — File/Info + export)
| # | Item | Location | Fix |
|---|------|----------|-----|
| E1 | **`dc:title` and `cp:keywords` are EMPTY** — deposit forms/PDF read these | `docProps/core.xml` | File ▸ Info: set title + the 5 keywords (both already in the abstract) |
| E2 | **CJK fonts not embedded** (DFKai-SB/PMingLiU are Windows-only) | package | **Deposit as PDF** (embeds glyph outlines) — or embed fonts if a .docx is required |
| E3 | *(optional)* Grammarly custom property; stale `app.xml` word-count cache (231 p / 71,905 w) | `docProps/custom.xml`, `app.xml` | remove the property; ignore the cached count (real ≈ 69.8k words) |

### F. Recto chapter starts (MANDATORY per author) — CORRECTED 2026-06-27
| # | Item | Notes |
|---|------|-------|
| F1 | **Recto chapter starts.** ~~Earlier (and the workflow) read this as "only 3/9 start recto."~~ **That was wrong** — re-reading per OOXML §17.6.22 + page orientation: **Chapters I, II, III, IV, V, VI, Conclusion, References ALL already start recto** (identical `oddPage` section heads; the `nextPage` sections are landscape tables + portrait returns *between* chapters). **Only the Introduction does not** — it shares its section with the List of Tables. | One fix only (also fixes the numbering): split the List-of-Tables/Introduction section → Introduction gets an Odd-Page break + arabic "Start at 1"; List of Tables stays roman. **Do not touch I–VI/Conclusion/References.** Steps in handout **GROUP 10**. |

---

## 3. Corrections to my own preliminary read (transparency)

The independent agents caught me three times — twice I was too harsh, once too lenient:

| My preliminary call | Verified reality |
|---|---|
| Odd-page chapter starts = **PASS**, then "**PARTIAL** 3/9" | **Both wrong → actually 8/9 already recto.** My first pass said PASS; the workflow "corrected" it to 3/9; *both* mis-attributed each section's `w:type` to the wrong section. Verified 2026-06-27 (OOXML §17.6.22 + orientation): I–VI/Conclusion/References all start recto; only the **Introduction** doesn't (shares a section with the List of Tables). The author's question surfaced the error. → handout GROUP 10. |
| Retrieval dates = **FAIL** (6 bare "Retrieved from") | **PASS** — all uniform "Retrieved June 10, 2026"; the lone date-less entry is a DOI (correctly no date). My regex split the string. |
| 3 Chinese glosses still quoted = **FAIL** | **PASS** — they're direct classical quotations/translations (fn22–23), not glosses; real glosses use `(理, lǐ)` correctly. |

This is the value of the cross-check: the deterministic pass and the four agents converged on everything material, and the disagreements were resolved against the raw file — not against anyone's recollection.

---

## 4. fn67 — RESOLVED (verified verbatim against P:\books PDFs, 2026-06-26)

fn67's six direct Hui quotes were checked against the source. **Five are verbatim; one (Q1) is a paraphrase wearing quote marks.** They split across **two** Hui works, and one isn't in the reference list:

- "planetarization … invasion of technology into all beings, rendering them standing reserves" → **Hui, 2019: 233–234** (*Recursivity and Contingency*) ✅
- "hybridism … gigantic system … nature ended and ecology began" + ecology "a concept of cybernetics" → **Hui, 2024a: 49** ("Machine and Ecology," *Cybernetics for the 21st Century* Vol. 1, Hanart) ✅
- livestock "fertility and sterility … modulate the behaviour…" → **Hui, 2024a: 54** ✅ (fn67 slips: "intervene **into**"→"in"; "behavior"→"behaviour")
- "a second nature that envelops the earth" → **Hui, 2019: 186** ✅
- "largely determines the relation between human and non-human beings, human and cosmos, and nature and culture" → ⚠️ **not verbatim in any Hui work** → de-quote as paraphrase (or supply a real source).

**Consequences (now in handout GROUP 1.5 + GROUP 7):** (a) add `Hui, Y. (2024a). Machine and Ecology…` to references; (b) relabel the existing *Machine and Sovereignty* entry → `2024b` and its in-text cites → (2024b); (c) apply the fn67 rewrite; (d) then delete the 4 Word comments (A1). Anchor cites (Hui, 2021: 224–227) and (2019: 28) were independently re-verified — **correct, no change.**

---

## Appendix — what was checked and PASSES (so it's on record)
Fonts (CJK=DFKai-SB ×545; 0 accented-Latin mis-pinned; ASCII hint=eastAsia benign) · Headings 20/16/14pt bold · body 12pt / footnotes 10pt · front matter Ack→摘要→Abstract · TOC `\o "1-2"` · List of Tables 9 entries w/ 0.5″ hanging indent · page numbering (roman front / continuous arabic body — conventional) · footnotes numbered 1–81 continuous · in-text forms (no `(year): page`; parentheticals; multi-source intact; block-quote placement; secondary-source form) · Chicago→author-date done (Stiegler/Simondon/Hui) · `ML`→`machine-learning` · no draft residue (F4/v2/note-v2/TL;DR) · no footnote restates its paragraph · 173 refs · 《》 13/13 · retrieval dates uniform · added entries present · DOI complete · English quotes intact · Chinese glosses no-quote ×103 · IoT spelled out first · no bracketed placeholders · A4 + margins (3.5/3.0 cm) + 1.5 spacing · both abstracts + keyword lines · title page · chapter structure · 9 tables = 9 List-of-Tables entries · no reviewer-identity leak.
