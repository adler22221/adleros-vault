---
type: concept
project: master-thesis
status: ai-draft
topic: [editing, pre-print, ai-residue, drafting-artifacts]
target: thesis
summary: "Pre-print scan of the working thesis MD (Intro–Conclusion body prose) for drafter-facing meta-commentary, scaffold residue, and clear AI stylistic tells. Conservative flagging — RESIDUAL items must be fixed before print; STYLE items optional. References/footnote citations out of scope."
---

# AI-Residual & Drafting-Artifact Scan — Pre-Print
**File scanned:** `ThesisRevision/revision-draft/20260609 Between the Universe and the Metaverse (working).md`
**Scope:** BODY prose, Introduction → Conclusion. References section and footnote citation apparatus **out of scope for style**; in-body bracketed drafting markers ARE in scope (they print as visible prose).
**Date:** 2026-06-09
**Posture:** Conservative. This is the faithful baseline — the prose is dense, voice-consistent scholarship throughout. Only genuine tells are flagged.

---

## Headline counts
- **RESIDUAL (must-remove before print):** 9 (all are in-body bracketed `[VERIFY]` / `[LOOKUP]` drafting markers + 2 author "reference needed" notes embedded in running prose)
- **STYLE (optional polish):** 2

> NOTE ON SCOPE BOUNDARY: There are ~30 additional `[VERIFY: …]` markers living inside the **footnote apparatus** (lines ~549–578) and a handful of inline `(Baudrillard, [VERIFY citekey])`-type citation stubs. Those are the author's own citation-verification workflow per CLAUDE.md §2.5/§7 and are **citation apparatus, out of style scope** — but every one of them is still raw drafting text that must be resolved or stripped before a printed copy. They are listed in an appendix below as a checklist, NOT as style flags. The 9 RESIDUAL items below are only those that sit in the *running body prose a reader reads as argument*.

---

# [RESIDUAL] — MUST be removed/resolved before print
These are drafter-facing instructions or "still-to-do" notes embedded in sentences the reader will otherwise read as finished argument. Each is an instruction to the author/editor, not prose addressed to the reader. None is the author's voice; all are scaffolding that leaked into the body.

### R1 — Line 113 — "(multiple references needed)"
Drafter-facing TODO inside a body sentence.
- **old_string:** `is already widely observed across animal species (Whiten, 2021; multiple references needed).`
- **new_string:** `is already widely observed across animal species (Whiten, 2021).`
- (or supply the additional citekeys; but the parenthetical instruction must not print)

### R2 — Line 113 — "(reference needed)"
Second drafter-facing TODO in the same paragraph.
- **old_string:** `and such discrepancy suggests different extents of commensurability (reference needed).`
- **new_string:** `and such discrepancy suggests different extents of commensurability.`
- (or supply the citekey)

### R3 — Line 184 — "(Baudrillard, [VERIFY citekey] — …)"
Citation-verification stub sitting inside running prose, with a drafter note ("on *la réalité intégrale*").
- **old_string:** `an "integral reality" that has finally displaced the real (Baudrillard, [VERIFY citekey] — *The Intelligence of Evil; or, The Lucidity Pact*, on *la réalité intégrale*).`
- **new_string:** resolve to `(Baudrillard, <citekey>: <page>)` — strip the `[VERIFY citekey]` token and the editorial "on *la réalité intégrale*" note.

### R4 — Line 186 — two "[VERIFY page]" tokens inside Chalmers quotations
Both sit in the body, attached to direct quotations the reader sees.
- **old_string (a):** `"The cats around you are real cats — it's just that cats in your reality are made of bits" (Chalmers, 2022 [VERIFY page])`
- **old_string (b):** `"the world we're living in could be a virtual world" without being on that account any less real (Chalmers, 2022 [VERIFY page]).`
- **new_string:** supply the page number; remove the `[VERIFY page]` token in each.

### R5 — Line 189 — "([LOOKUP cite — Whiten et al. … ; add to Zotero])"
The most conspicuous one: a full drafter work-order ("add to Zotero") printed mid-sentence.
- **old_string:** `as a growing body of animal-culture studies shows ([LOOKUP cite — Whiten et al. on animal culture; de Waal; Hobaiter & Byrne on great-ape gestural meaning; add to Zotero]), such meaning`
- **new_string:** `as a growing body of animal-culture studies shows (<resolved citations>), such meaning`

### R6 — Line 189 — "(Uexküll, [VERIFY citekey])"
Citation stub in body prose.
- **old_string:** `in Jakob von Uexküll's sense (Uexküll, [VERIFY citekey]):`
- **new_string:** resolve to `(Uexküll, <citekey>: <page>):`

### R7 — Line 190 — "(Obara, [VERIFY citekey])"
Citation stub in body prose.
- **old_string:** `(だから儀式はなくならない, *Dakara Gishiki wa Nakunaranai*) (Obara, [VERIFY citekey]) traces human ritual`
- **new_string:** resolve to `… (Obara, <citekey>) traces human ritual`

### R8 — Line 263 — "[VERIFY: locus + translation source for 和而不同 / 和實生物, or recast as the author's own gloss]"
A full editorial decision-instruction printed in the middle of the harmony paragraph.
- **old_string:** ` [VERIFY: locus + translation source for 和而不同 / 和實生物, or recast as the author's own gloss]`
- **new_string:** DELETE (after supplying the loci or recasting as the author's gloss).

### R9 — Line 263 — "[LOOKUP: verify and cite sumak kawsay / kaitiakitanga, or substitute already-verified Descola/Viveiros examples]"
Second editorial decision-instruction in the same paragraph.
- **old_string:** ` [LOOKUP: verify and cite sumak kawsay / kaitiakitanga, or substitute already-verified Descola/Viveiros examples]`
- **new_string:** DELETE (after resolving the citations or substituting examples).

> Also in body prose but borderline / lower-confidence (Scheler/Taylor/Sandel cluster, line 278; Needham, line 300): `[VERIFY printed page — Frings 2009 / Meyerhoff 1961]`, `(Taylor, 2007 [VERIFY page])`, `(Sandel, 1998: 179 [VERIFY edition pagination]; …)`, and `[VERIFY page against P:\books — print page not embedded in the PDF; passage confirmed in ch. 1]`. These are page-locator stubs rather than reader-facing instructions, and read more like citation apparatus than meta-commentary — but they are still raw `[VERIFY …]` tokens inside body sentences and **must not print**. Resolve the page numbers and strip the brackets. (Grouped here rather than as separate RESIDUAL items because they are citation-completeness, not stylistic residue.)

---

# [STYLE] — optional polish (not blocking print)
The body is overwhelmingly the author's own measured, first-person scholarly voice. I found **no** inflated-diction AI vocabulary ("tapestry," "delve," "navigate the landscape," "multifaceted," etc. — zero hits), no mechanical "Firstly/Secondly/Finally" cadence, no empty hedging, and no near-verbatim repeated sentences that read as AI duplication. The two items below are mild and discretionary.

### S1 — Em-dash density (whole document) — [STYLE]
The em-dash is the author's signature connective and is used heavily and, mostly, well. A few sentences stack three or more dash-set asides and become hard to parse on a single read (e.g., Introduction §C, line 52, the long transdisciplinary-sources sentence; the four "not X but Y" tricolon sentences in Ch VI §A criteria list, lines 593–597). This is the author's own norm, not an AI tell — flagged only as optional readability polish for a print pass: in the densest 4–5 sentences, convert one dash-pair to a comma-pair or a separate sentence. **No specific rewrite mandated.**

### S2 — Recurring two-sentence "X. This is the Nth diagnosis of a pre-metaverse squeeze." cadence (Ch II §E, lines 233–237) — [STYLE]
Five paragraphs each close on a near-identical formula: "This is the first/second/third/fourth/fifth diagnosis of a pre-metaverse squeeze …". This is deliberate rhetorical anaphora tied to Table 2-3 (clearly intentional, not accidental AI repetition), so it is **not** a RESIDUAL repetition flag. But because the wording is so close across five consecutive paragraphs, a reader may feel the template; if a lighter touch is wanted, vary two of the five closers. Optional only — the parallelism is defensible as authorial structure.

---

# Appendix — Footnote/citation `[VERIFY]` checklist (OUT OF STYLE SCOPE; print-blocking as citation apparatus)
Per the brief, footnote citations are out of scope for *style*. Listed here only so the print pass does not ship raw verification tokens. These are in the footnote block, lines ~549–578, and a few inline citation stubs:
- L549 `[VERIFY exact wording of the closing-aphorism phrase …]`
- L550 `[VERIFY against a standard edition/translation …]`
- L557 `[VERIFY: this "debt/liability" rendering …]`
- L560 `[VERIFY page against Zotero PDF …]`
- L562 `[VERIFY: confirm and cite each account …]`
- L566 `[VERIFY: page numbers (139, 143, 144, 145, 150) …]`
- L567 `[VERIFY: confirm the exact volume and page for "tertiary protention" …]`
- L568 `[VERIFY: quotations and pages confirmed via NLM Yuk Hui notebook …]`
- L569 `[VERIFY: locate exact page; Japanese verbatim …]`
- L570 `[VERIFY: folio — 2008 Routledge edition …]`
- L571 `[VERIFY: confirm verbatim from Zotero/NLM …]`
- L572 `[VERIFY: Heidegger citekey + texts …]`
- L573 `[VERIFY: citekeys — Weber, Adorno & Horkheimer …]`
- L574 `[VERIFY …]` (omitted long line)
- L575 four `[VERIFY: …]` tokens (synthetic-anthropology / Obara / Uegaki source locators)
- L576 `[VERIFY: cross-reference the Ch IV "vantage from the seam" …]`
- L577 `[LOOKUP: verify the exact citekey, edition, and a page …]`
- L578 `[VERIFY: the wording and locators of the classical passages …]`

These are the author's legitimate citation-verification schema (CLAUDE.md §2.5), not AI residue — but they are unresolved and would print as bracketed tokens. Resolve or strip all before final.

---

## Editor's bottom line
This baseline is clean. The only genuinely print-blocking residue is **bracketed drafting/verification tokens that leaked into running body prose** — 9 items (R1–R9), all in the Introduction and Chapter II/III, plus the line-278/300 page-locator stubs and the footnote-block checklist. There is essentially **no AI-vocabulary or AI-cadence problem**: the prose is the author's own voice end to end. Fix R1–R9 (drafter-facing notes) without fail; resolve the citation `[VERIFY]`/`[LOOKUP]` tokens (body and footnote) as a citation-completeness pass; the two STYLE notes are discretionary.
