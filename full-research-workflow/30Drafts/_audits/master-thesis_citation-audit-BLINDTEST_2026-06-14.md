---
type: concept
project: master-thesis
status: ai-draft
summary: "Blind citation-audit of 楊逸帆碩士論文_2026-06-14 - test.docx (author planted errors; auditor not told where). Findings committed BEFORE any diff against the clean 0614, every verdict carries an external artifact (reference list / CrossRef record / NLM verbatim source+page). For the author to score against the answer key."
---

# Citation audit — BLIND TEST on `楊逸帆碩士論文_2026-06-14 - test.docx`

> **Integrity conditions of this run**
> 1. Auditor was NOT told where the planted errors are.
> 2. Findings below were committed BEFORE diffing the test file against the clean 0614 (a diff would bypass the audit instead of testing it).
> 3. Every verdict carries an **external artifact** — the author's own reference list, a CrossRef record, or an NLM verbatim passage with source title + page. The auditor's prose is never the evidence.
> 4. Default-to-flag: anything not confirmable against an artifact is flagged, not passed.

Extraction: 892 body paragraphs · 85 footnotes · 172 reference entries · 282 in-text citations parsed.

---

## Coverage (what was run, and to what depth)

| Layer | Method | Coverage |
|---|---|---|
| L1a Reconciliation (in-text ↔ reference list) | deterministic script, CJK romaji↔kanji author map | **FULL** (all 282 cites) |
| L1b Fabrication / existence | CrossRef bibliographic resolution | **FULL** (142 resolvable Latin entries) |
| L2 Quote + page fidelity | NLM verbatim retrieval, string-compared by hand | **SAMPLED** — 13 quotations across 7 source notebooks (NOT all ~25+ quotes) |

The L2 sample is the honest gap in this pass; see "Residual" below.

---

## FLAGS (committed before diff)

### Tier 1 — In-text citation YEAR mismatches
Artifact = the author's own reference list. Each cited year has **no** matching reference entry, while the work the sentence describes is in the list under a **different** year.

| # | Location | Cited as | Reference list has | Why the cited year is wrong | Confidence |
|---|---|---|---|---|---|
| 1 | fn11 | **Scott, 2006** | Scott 2009; Scott 2017 | Sentence is about *slow, partly unintended* domestication → Scott **2017** *Against the Grain* | High |
| 2 | P280 | **Foucault, 1973** | Foucault 1988 | Sentence names *"technologies of the self"* = the reflist's Foucault **1988** entry; 1973 = *Birth of the Clinic* | High |
| 3 | P280 | **Weber, 1965** | Weber 1946; Weber 1978 | "bureaucracy as a technology of rule" → *Economy and Society* (**1978**) or *From Max Weber* (1946); no Weber 1965 | High |
| 4 | P356 | **Harvey, 2009** | Harvey 2003 | Enclosure / dispossession / Global South → *The New Imperialism* (**2003**) | High |
| 5 | P279 | **Franssen…2016** | Franssen 2023 | SEP "Philosophy of technology"; reflist standardizes to the **2023** edition | Medium (SEP is re-dated per edition; body & reflist must agree) |

### Tier 2 — Page discrepancy (quote text authentic, page suspect)
Artifact = NLM source PDF.

| # | Location | Finding | Confidence |
|---|---|---|---|
| 6 | P356 | Illich "That motor traffic curtails the right to walk, not that more people drive Chevies than Fords, constitutes radical monopoly" — **quote is verbatim-authentic**, but cited **p.85** while NLM's Fontana edition shows it at **p.65** (mid-book Ch.3, consistent with ~65, not 85). Possible digit-swap 65→85. Sits in the **same paragraph as flag #4**. | Medium-high (pending the author's print copy; Illich editions repaginate) |

### Tier 3 — Reference-label / completeness (likely pre-existing housekeeping, not necessarily plants)

| # | Location | Finding |
|---|---|---|
| 7 | fn42, fn43 | **"Bhaskar, 2008a" / "Bhaskar, 2008b"** cited, but the reference list has only an unlettered **Bhaskar (2008)** = *A Realist Theory of Science*. The 2008a ontic-fallacy quote is in fact from *Dialectic: The Pulse of Freedom*, which the reflist dates **1993**. The a/b labels are unresolved. (Quotes themselves authentic — see Clean.) This matches the known 2008/2008a/2008b housekeeping item. |
| 8 | fn80 | Adorno, "The Idea of Natural-History," *Telos* 60 (1984) cited in the footnote but **absent from the reference list**. |

---

## VERIFIED CLEAN (the audit is not merely flagging everything)

**Quotations matched verbatim against the source PDF, correct page:**

| Location | Source (NLM) | Page | Result |
|---|---|---|---|
| fn2 | Bhaskar, *A Realist Theory of Science* | p.46 | exact ✓ |
| fn42 | Bhaskar, *RTS* (epistemic fallacy) | p.25–26 | exact ✓ (US "analyzed" for UK "analysed") |
| fn43 | Bhaskar, *Dialectic* (ontic fallacy) | — | exact ✓ (label issue = #7) |
| fn43 | Bhaskar, *Scientific Realism & Human Emancipation* | p.16 | exact ✓ |
| fn31 | Durante, *Oxford Handbook of Phil. of Technology* | p.318–319 | exact ✓ |
| fn14 | Whiten et al., *Cultures in chimpanzees* (Nature) | p.685 | exact ✓ (US "behavioral" for UK "behavioural") |
| fn39 | Rosa, *Uncontrollability of the World* (four dimensions) | p.15–16 | faithful gloss ✓ |
| fn45 | Rosa, *Uncontrollability* (games) | p.3 | exact ✓ |
| fn80 | Adorno, "Idea of Natural-History" / *Negative Dialectics* | p.357 | exact ✓ ("total mediation" = gloss) |
| P356 | Illich, *Tools for Conviviality* (text) | (page = #6) | text exact ✓ |
| fn55 | Stiegler, *Automatic Society 1* (grammatization) | p.19–20 | exact ✓ |
| fn56 | Stiegler, *Automatic Society 1* (tertiary retention) | p.31 | exact ✓ |
| fn54 | Lotka "exosomatic" coinage | p.188 | corroborated ✓ |

**No fabricated references.** All 142 CrossRef-resolvable entries map to real works. The 60 CrossRef "year-off" hits are **reprint / translation / review-year noise** (e.g. CrossRef indexes a 2013 Routledge reprint of Bhaskar's 1975 RTS; the 1973 original of Illich, which the reflist's own note already states; a 1976 reprint of Polanyi 1968). These are **explicitly NOT counted as errors**. The 4 CrossRef "NO-MATCH" hits are title-parser artifacts (Adorno/Brentano/Scheler "1966/1973" slash-years) plus Tang's self-published *Plurality* (no DOI) — none are fabrications.

---

## Residual (honest coverage gap in THIS pass)

- L2 verified **13 of ~25+** quotations. A planted altered-quote **outside that sample** would not have been caught here — candidates not yet machine-checked: fn35 (Scheler, German), fn36 (Bacon), fn37 (Descartes), fn78 (Aristotle, *Physics* II.8), fn57/58 (Simondon), fn69 (Hui). Scaling L2 to 100% closes this.
- A few **classical primary texts** (Bacon *Novum Organum*, Descartes *Discourse*, Aristotle *Physics*) are not in the NLM corpus → genuine "verify by hand / web" residual.

---

## For the author to score

Compare the flags above to your answer key:
1. Which planted errors did the audit **catch**? (Expected: the Tier-1 year mismatches; possibly the Illich page.)
2. Which did it **miss**? A miss almost certainly sits in the **L2 quote layer that was sampled, not exhausted** → tells us to run L2 at 100%.
3. Any **false positive** above? (i.e., a flag that is actually correct in your manuscript.)

Then, as an independent cross-check, the auditor can diff the test file against the clean 0614 to compute the exact catch-rate — but only now that these findings are committed.
