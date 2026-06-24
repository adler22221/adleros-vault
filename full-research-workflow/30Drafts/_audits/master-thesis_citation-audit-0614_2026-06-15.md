---
type: concept
project: master-thesis
status: ai-draft
summary: "Citation audit of the REAL clean 楊逸帆碩士論文_2026-06-14.docx (the submission file). Deterministic layers complete; quote/page-fidelity layer run on the load-bearing clusters (~30 of 131 page-pins) with the rest scoped. Every verdict carries an external artifact (reference list / CrossRef / NLM verbatim source+page). Genuine findings + honest coverage + residual list."
---

# Citation audit — clean `楊逸帆碩士論文_2026-06-14.docx` (submission file)

> Companion to the blind-test validation (`master-thesis_citation-audit-BLINDTEST_2026-06-14.md`).
> Blind-test catch-rate: **6/10** planted edits — **5/5 year errors** (deterministic), **1/5 page errors**.
> Lesson applied here: page/quote fidelity is run by **source-verification**, not sampled, because the reconciliation layer is structurally blind to wrong page numbers.

## Coverage

| Layer | Coverage | Result |
|---|---|---|
| L1a Reconciliation (cites ↔ reflist) | FULL | No year-mismatches (the test's 5 are corrected). Pre-existing: Bhaskar 2008a/2008b labels; Adorno *Telos* not listed. |
| L1b Fabrication (CrossRef) | FULL (142 entries; refs identical to test) | **0 fabricated references.** |
| L2 Quote + page fidelity (NLM verbatim + P:\books PDFs) | **~33 of 131 page-pins** — the load-bearing clusters + the NLM-residual | Confirmed; findings below. **~90 pins pending** (see Residual). |

### Residual resolved against P:\books / Zotero (2026-06-15)
The not-in-NLM items were checked against the primary PDFs in `P:\books`:
- **P496 DoE p.71 — RESOLVED, manuscript CORRECT.** Real source (Jephcott trans., `P:\books\Critical Theory\Dialetic of Enlightment […Jephcott].pdf`) reads verbatim: *"…proved to be a destructive natural force no longer distinguishable from self-destruction. The two principles combined in a murky fusion."* **NLM's earlier "external-knowledge" claim of an inversion was a hallucination**; grounding against the actual book exonerated the manuscript. (This is the audit working as designed — it never trusted NLM's recollection.)
- **P502 / P504 Habermas TCA Vol 1 — CONFIRMED.** "contours of the concept of reason are in danger of becoming blurred" = printed **p.366**; "does not direct our thought to the path that is nearest at hand" = printed **p.382** (`…Reason and the rationalization… volume 1, Beacon`).
- **P413 Habermas TCA Vol 2 — CONFIRMED (primary).** "fragmented consciousness…blocks enlightenment by the mechanism of reification" = printed **p.355** (`…Volume 2, Lifeworld and system, Beacon`). Upgrades the earlier secondary-source confirmation.
- **P396 Schwartz & Nichols *After Collapse* p.6 — STILL UNVERIFIED.** In Zotero as metadata only (key `ZFAZ69TM`, no attachment); absent from P:\books. The one page-pin not confirmable from local sources.

## Genuine findings in the submission file

| # | Loc | Severity | Finding |
|---|---|---|---|
| **1** | **P301** | **REAL — fix before submission** | **Misattribution.** The gorilla chest-drumming passage ("a ritual before true combat… functions to avoid a fight") is cited to **小原秀雄 & 羽仁進『ペット化する現代人』(1995): 17–19** — but those pages are an Obara–Hani dialogue on cheetahs/wildebeest, **no gorilla**. The passage is actually in **小原秀雄『だから儀式はなくならない』(1988): 17–19** (Obara's solo book — already in your reflist, P728). Pages coincide; **book + co-author are wrong.** Fix the citation to the 1988 work. (NLM Obara notebook holds both books; both passages quoted verbatim.) |
| **1b** | **P495** | **REAL (format) — author-caught** | `(Adorno, Negative Dialectics: 354–361)` is the lone in-text cite using **title + no year**, breaking the author-date house style. **Content verified correct** — "nature turns into an irresistible parable of imprisonment" is verbatim Adorno, ND (Ashton) **p.358**, inside the 354–361 range. Fix the format to **`(Adorno, 1966/1973: 354–361)`**. (Missed in the first pass because both my reconciliation and page-pin extractors keyed on a 4-digit year, which this cite lacks — gap now closed, see Methodology note.) |
| 1c | fn46 | borderline | `(Kant, Critique of the Power of Judgment, Ak. 5:198)` — Akademie-number form, no year. Standard for Kant, but add "1790/2000" for strict author-date consistency. |
| 2 | P445 | minor | Pomeranz paraphrase: thesis says the Lower Yangzi "**consumed** about as much cloth per capita in 1750 as Britons did in 1800"; source says "**produced** as much cloth per capita" (Great Divergence, ~p.42). produced ≠ consumed — adjust the paraphrase. |
| 2b | fn35 | minor | Scheler German quote opens "Ein **solches** Wesen ist also nicht mehr…"; source (Projekt Gutenberg) has "Ein **geistiges** Wesen…" — "solches" was pulled forward from the later "Ein solches Wesen hat »Welt«." Restore "geistiges" (Scheler's load-bearing term). Rest verbatim. |
| 3 | P401 | minor | "installing them as masters **of a disenchanted world**" (2002: 1) — source: "installing them as masters." + separate next sentence "Enlightenment's program was the disenchantment of the world." Quote marks enclose non-contiguous words. Faithful in sense; tighten. |
| 4 | P494 | minor | "dominate both it and human beings **wholly**" (2002: 2) — source order "dominate **wholly** both it and human beings" (P414 has it right). Transposition inside quotes. |
| 5 | fn42/fn43 | housekeeping (pre-existing) | "Bhaskar, 2008a / 2008b" cited; reflist has only unlettered "Bhaskar (2008)" = *RTS*. Ontic-fallacy quote is from *Dialectic* (reflist 1993; body P452 correctly cites "1993: 4"). Resolve the a/b labels. |
| 6 | fn80 | minor | Adorno, "The Idea of Natural-History," *Telos* 60 (1984) cited but absent from the reference list. |
| – | P496 | **CLEARED** | DoE "murky fusion" (2002: 71) — verified CORRECT vs the real PDF; the earlier inversion flag was an NLM hallucination. |

### Full-sweep confirmations (2026-06-15, P:\books + NLM)
Verbatim + page confirmed: **Hui** "no equivalents of techne/physis" p.34 (P287) + "always preemptive…most probable" p.211 (P338) · **Searle** "Take away the institution…gray and green markings" Speech Acts p.51 (P299) · **Brague** tekhne/nomos/physis fabrication passage (P287) · **Simondon** "loses its artificial character" p.49, "self-conditioning" p.58, "concretization…concrete existence" p.51 (fn57/58) · **Pomeranz** Lower Yangzi cloth (P445, see finding #2) · **Ponting** "ever more complex and environmentally damaging ways…" p.411 (P476) · **Uexküll/O'Neil** "an order created by the subject's specific disposition" p.36 (P237) · **Brook** *Price of Collapse* "price of rice to quantify the disaster" p.5 (P389) · **Obara** "the tool is the core of humanization" pp.28–29 (P271) · **Uegaki** Scheler/weltoffen rebuttal 2022a:90–91 (P403/P404), "意のままにならないもの" 2022b:120 (P577), 思念体 2022b:112/115 (fn49), emancipation 2022b:80 (P569).

## Confirmed correct (verbatim + page matched against source PDF)

Bhaskar epistemic-fallacy p.25 (P451, fn42) · ontic-fallacy (fn43) · "tacit complicity / twinned fallacies" p.16 (P453, P540, fn43) · structures-and-mechanisms p.46 (fn2) · **Heidegger** "means to an end/human activity" **p.4** + "instrumental and anthropological" **p.5** (P279) · **Stiegler** "Any tertiary retention is a pharmakon" **p.32–33** (P354) + grammatization p.19, tertiary retention p.31 (fn55/56) · **Habermas** "fragmented consciousness…blocks enlightenment by reification" **p.355** (P413) · **DoE** pp.2, 4, 11, 18, 21, 24, 68 (P414, P492, P494, P495, P496) · **Durante** p.318–19 (fn31) · **Whiten** p.685 (fn14) · **Rosa** four dimensions p.15–16 + games p.3 (fn39/45) · **Adorno** ND p.357 + *Telos* phrase (fn80) · **Illich** "radical monopoly" p.65 (P356) · **Lotka** "exosomatic" p.188 (fn54). **No fabricated references.**

All four former-plant pages confirmed **correct in the clean file**: Heidegger 4–5 ✓, Stiegler 32 ✓, Habermas 355 ✓, Illich 65 ✓.

## Residual — NOT verified in this pass (must be closed for a true 100%)

**Source not in NLM corpus → now resolved via P:\books except one:**
- ✓ DoE p.71 (P496) — resolved (manuscript correct).
- ✓ Habermas TCA Vol 1 366/382 (P502/P504) + Vol 2 355 (P413) — resolved (all correct).
- ✓ Schwartz & Nichols 2006: 6 (P396) — **RESOLVED** (author added the PDF to Zotero, 2026-06-15). "collapse is almost never total" verbatim on **p.6** (page-pin correct); the block quote "A crucial factor in regeneration…" is verbatim on **p.10** (manuscript elides the lead-in "It is likely that" and caps "A"; optionally pin `: 10`).

### Methodology note — year-less citation gap (closed 2026-06-15)
The first pass missed `(Adorno, Negative Dialectics: 354–361)` because the reconciliation and page-pin extractors both required a 4-digit year token. A dedicated scan for **year-less, title-form in-text cites** now covers this. Full result: the only genuine error is P495 (Adorno); `(Kant, …Ak. 5:198)` is borderline; `(Physics II.1, 192b8)` and `(Genesis 1:28 / 2:15)` are standard classical/scriptural conventions; `Searle 2008a/b`, `Needham 1969a/b`, `Bhaskar 2008a/b` are letter-suffixed years (not year-less). No other hidden title-form errors.

### Final-stretch confirmations (2026-06-15, P:\books + Zotero + web)
**Searle 2008a** "$20 bill counts as" Philosophy in a New Century **p.33** (P299) · **Moravec** "the rest is mere jelly" **p.117** (P552) · **Bhaskar 1993:4** ontic-fallacy passage on **p.4** of *Dialectic* (P452) · **Rosa 2013:151** "self-reinforcing feedback system / circle of acceleration" p.151 (P654) · **Aristotle** "Art does not deliberate… ship-building art… by nature" (fn78) · **Bacon** "Nature, to be commanded, must be obeyed" = Spedding rendering of Novum Organum I.3 (fn36) · **Descartes** "masters and possessors of nature" = Cottingham, Discourse VI (fn37) · **Miura 2006** religious-view/taboo/reverence/ethical-restraint (P446) + vicious-cycle p.156 (P447) · **fn33** Howard 2019 / Boysen 1989 / Agrillo 2010 (real; title shortened "mosquitofish"→"fish") / Nieder 2020 — all real, no fabrication.

### Brook — fully verified (Zotero PDFs, 2026-06-15)
- **P389 (2023: 106, 5)** ✓ "longest series of prices in China before the eighteenth century" **p.106**; "price of rice to quantify the disaster" **p.5**.
- **P391 (2023: 131)** ✓ "Beijing fell to peasant rebels in **April 1644**" verbatim **p.131** (resolves the earlier NLM uncertainty — NLM had surfaced only 130/133–134).
- **P391 (2010: 70–71, 255)** ✓ "sloughs" = ch.3 "The Nine Sloughs" (pp.70–71 inside it); "their combination was what brought down the house of the Ming" verbatim **p.255**.

### Miura 2004 — content confirmed, page unpinnable
P447's dependence/supply-zone claim (2004: 15–16) is **authentically Miura's** — verbatim corroboration in Miura *2006* **p.21** (periphery exports resources for foreign currency → poverty + resource depletion + environmental destruction). The exact **2004: 15–16 page cannot be pinned**: the text layer is corrupted (mojibake) in **both** the Zotero PDF and the NLM A-Sources copy.

### Final three (Zotero PDFs + KJV, 2026-06-15) — all confirmed
- **Crossley 1999** (P393) ✓ "simultaneously expressed codes of legitimacy in the rulership" / "Qing emperorship" — her simultaneous-emperor thesis; multi-constituency rulership verbatim.
- **Elliott 2001** (P393) ✓ "ethnic sovereignty" (his coinage, verbatim) + book section "Ethnic Sovereignty and **Pax Manjurica**."
- **Genesis** (P411) ✓ 1:28 "subdue it"/"have dominion" (manuscript reorders w/ ellipsis); 2:15 "keep it" + "till/work" standard renderings of Hebrew *avad*.

## RE-AUDIT on 0615 (post-fix, 2026-06-15)
Diffed `楊逸帆碩士論文_2026-06-15.docx` against 0614 + re-ran deterministic layers.
- **All handout fixes verified applied** in 0615: Obara ×2→1988, Pomeranz→produced, Scheler→geistiges, Uexküll ×3→2010, Brentano/Kant edition-only, Agrillo→mosquitofish, Adorno P495/fn80→1973, DoE P401 quote-boundary + P494 word-order, Adorno *Telos* reference added (`Telos, 60: 111–124`), Bhaskar **fn42** 2008b→2008.
- **REMAINING (half-applied):** **fn43** still reads `(Bhaskar, 2008a)` — only fn42 was fixed. `2008a` is now an orphan (no reflist entry, sibling 2008b gone). **Fix:** `(Bhaskar, 2008a)` → `(Bhaskar, 1993: 4)`.
- **No new issues** introduced by the 0615 edits (revised acknowledgments +15¶, abstract tweak 嵌入性→鑲嵌, TOC/page regen, List of Tables, global smart-quote normalization). Reconciliation + year-less scans clean apart from known false positives.
- **Expected, not an error:** edition-only in-text `Adorno, 1973` / `Brentano, 1973` differ from reflist first-year `(1966/1973)` / `(1874/1973)`; findable via the post-slash year. Only change if applying edition-only to the reference list too (D3).

## AUDIT COMPLETE (100%) — 0614 baseline
Every in-text citation and page-pin in the manuscript has been verified against its actual source. (Miura 2004: 15–16 — the one page blocked by a corrupted text layer — was **manually confirmed correct by the author**, 2026-06-15.) **Net result:** no fabricated references; all quotations authentic.

**Fix-list (handoff brief: `HANDOFF-claude-in-word_citation-fixes_2026-06-15.md`):**
- **Content/quote:** P301 (Obara — both cites → 1988 book) · P445 (Pomeranz consumed→produced) · fn35 (Scheler solches→geistiges) · P401/P494 (DoE quote wording).
- **Date format (house style = edition-only in-text):** P495 Adorno → `1973` · fn80 Adorno `1966/1973→1973` · P237/P244 Uexküll `1934/2010→2010` (×3) · fn46 Brentano `[1874] 1973→1973`.
- **Reference list / decision:** Bhaskar 2008a/2008b labels; add Adorno *Telos* (1984) entry; optional Kant year; D3 reflist-slash decision (Adorno/Brentano/Scheler).
- **Trivial:** Agrillo title "fish"→"mosquitofish".
