---
aliases: []
type: concept
project: master-thesis
topic: [bracket-resolution, fact-check, citation-verification, print-prep]
status: ai-draft
target: thesis
summary: "Resolution list for every [VERIFY]/[LOOKUP] editorial bracket in the 20260609 working MD, so the brackets can be removed before print. Each item gives classification, exact old_string -> new_string, and verification source. Brackets verified against NLM (A-Sources, Baudrillard, Obara, Uexküll-in-Foray) and Zotero (BBT citekeys + local API), 2026-06-09."
source-notes: [baudrillardIntelligenceEvilLucidity2005, chalmersRealityVirtualWorlds2022, vonuexkullForayWorldsAnimals2010, obaraDakaraGishikiWa, whitenBurgeoningReachAnimal2021, descartesPhilosophicalWritingsDescartes1985, gundersonPanarchyUnderstandingTransformations2002, needhamFourSeasDialogue1969, heideggerQuestionConcerningTechnology1977, huiQuestionConcerningTechnology2016, huiRecursivityContingency2019, horkheimerDialecticEnlightenment2002, habermasTheoryCommunicativeAction1985, rosaUncontrollabilityWorld, weberProtestantEthicSpirit2001, mignoloDarkerSideWestern2011, chakrabartyProvincializingEuropePostcolonial2000, descolaNatureCulture2013, castroCannibalMetaphysicsPoststructural2014, decastroCosmologicalDeixisAmerindian1998]
---

# VERIFY / LOOKUP bracket-resolution list — for print removal
> Target file (read-only): `ThesisRevision/revision-draft/20260609 Between the Universe and the Metaverse (working).md`
> Goal: every `[VERIFY...]` / `[LOOKUP...]` bracket must vanish from the printed thesis. This note gives the exact find-replace for each.
> Verification cascade used: NotebookLM (SCU thesis-A-Sources `c68ca15e…`, Baudrillard `faf368f9…`, Obara `86e6c0e5…`) → Zotero local API / Better-BibTeX citekeys (`localhost:23119`, read-only) → web (classical loci only).
> Date: 2026-06-09. **Do not edit the manuscript from this note without human review (status: ai-draft).**

## Classification key
- **STRIP-CONFIRMED** — claim/cite verified; delete bracket only.
- **STRIP-CORRECTED** — a real error fixed (page/edition/cite/wording) + bracket removed.
- **STRIP-KEEP-FLAG** — could not fully resolve (source not on disk/NLM, or page unfindable); bracket removed, cite left as-is; added to residual list.

> NOTE on the "citekey" brackets (`[^continental-b]`, `[^critical-theory-b]`, `[^bridges-b]`, etc.): these brackets are **editorial notes-to-self**, not printed citekeys — the citekeys live *inside* the bracket. Removing the bracket simply deletes the note; the footnote prose (which cites by author/title, not citekey) is unaffected. I resolved each citekey against Zotero so the author knows which are actually held; works **not** in Zotero are listed in the residual section.

---

## 1. Line 184 — body (§IIC, Baudrillard *réalité intégrale*)
**Classification: STRIP-CONFIRMED**
Verified on NLM Baudrillard notebook: *The Intelligence of Evil or the Lucidity Pact* (2005) defines *la réalité intégrale* / Integral Reality as the terminal/epochal absorption of the real, esp. **p.17** ("What I call Integral Reality is the perpetrating on the world of an unlimited operational project…") and the "murder of the real" passage. Zotero BBT citekey confirmed: `baudrillardIntelligenceEvilLucidity2005` (item key VS4DKAX2).

- **old_string:** `(Baudrillard, [VERIFY citekey] — *The Intelligence of Evil; or, The Lucidity Pact*, on *la réalité intégrale*).`
- **new_string:** `(Baudrillard, 2005 — *The Intelligence of Evil; or, The Lucidity Pact*, on *la réalité intégrale*).`
- Source: NLM Baudrillard `faf368f9-59d9-416c-97ec-cb44abdea40b`; Zotero BBT.

---

## 2. Line 186 — body (§IIC, Chalmers "real cats")
**Classification: STRIP-CORRECTED (page filled in)**
Verified on NLM A-Sources, Chalmers *Reality+* (2022): "The cats around you are real cats—it's just that cats in your reality are made of bits" is on **p.436** (Ch. 24).

- **old_string:** `"The cats around you are real cats — it's just that cats in your reality are made of bits" (Chalmers, 2022 [VERIFY page])`
- **new_string:** `"The cats around you are real cats — it's just that cats in your reality are made of bits" (Chalmers, 2022: 436)`
- Source: NLM A-Sources `c68ca15e…`, Chalmers *Reality+*, p.436 verbatim.

## 3. Line 186 — body (§IIC, Chalmers "fully meaningful life")
**Classification: STRIP-CORRECTED (page filled in)**
Verified on NLM A-Sources: both quotations appear consecutively on **p.xvii** (Introduction).

- **old_string:** `"you can lead a fully meaningful life in a virtual world," and "the world we're living in could be a virtual world" without being on that account any less real (Chalmers, 2022 [VERIFY page]).`
- **new_string:** `"you can lead a fully meaningful life in a virtual world," and "the world we're living in could be a virtual world" without being on that account any less real (Chalmers, 2022: xvii).`
- Source: NLM A-Sources `c68ca15e…`, Chalmers *Reality+*, p.xvii verbatim.

---

## 4. Line 189 — body (§IIC, animal-culture LOOKUP)
**Classification: STRIP-CORRECTED (placeholder → verified cite; partial)**
Zotero holds `whitenBurgeoningReachAnimal2021` (Whiten, "The burgeoning reach of animal culture," 2021) and `whitenCulturesChimpanzees1999`. **de Waal and Hobaiter & Byrne are NOT in Zotero** — so the placeholder is reduced to the one verified, citable anchor (Whiten et al. 2021), which covers the "shared, transmitted, answered-to within the group" claim. (If the author wants the gestural-meaning specificity of Hobaiter & Byrne, that item must be added to Zotero first — see residual.)

- **old_string:** `as a growing body of animal-culture studies shows ([LOOKUP cite — Whiten et al. on animal culture; de Waal; Hobaiter & Byrne on great-ape gestural meaning; add to Zotero]), such meaning is itself shared`
- **new_string:** `as a growing body of animal-culture studies shows (Whiten et al., 2021), such meaning is itself shared`
- Source: Zotero BBT `whitenBurgeoningReachAnimal2021`.

## 5. Line 189 — body (§IIC, Uexküll citekey)
**Classification: STRIP-CONFIRMED**
Zotero holds the 2010 Minnesota *Foray into the Worlds of Animals and Humans: With A Theory of Meaning*: BBT `vonuexkullForayWorldsAnimals2010` (item key 92M346FN). Manuscript cites by author; no year currently printed, and the volume is the 2010 edition used elsewhere → supply 2010.

- **old_string:** `in Jakob von Uexküll's sense (Uexküll, [VERIFY citekey]): each animal inhabits`
- **new_string:** `in Jakob von Uexküll's sense (Uexküll, 2010): each animal inhabits`
- Source: Zotero BBT `vonuexkullForayWorldsAnimals2010`.

---

## 6. Line 190 — body (§IIC, Obara *Dakara Gishiki* citekey)
**Classification: STRIP-CORRECTED (citekey resolved + year supplied)**
Verified on NLM Obara notebook: 小原秀雄『だから儀式はなくならない』(人間選書131, 農山漁村文化協会), first edition **1988** (Oct 30 1988); the book traces human ritual to animal (ethological) origins — gorilla drumming, crane/ibex courtship — exactly as the footnote states. Zotero BBT citekey `obaraDakaraGishikiWa`. Manuscript currently prints no year; supply 1988.

- **old_string:** `(だから儀式はなくならない, *Dakara Gishiki wa Nakunaranai*) (Obara, [VERIFY citekey]) traces human ritual back to its animal origins`
- **new_string:** `(だから儀式はなくならない, *Dakara Gishiki wa Nakunaranai*) (Obara, 1988) traces human ritual back to its animal origins`
- Source: NLM Obara `86e6c0e5…` (verbatim奥付 1988, 農山漁村文化協会); Zotero BBT `obaraDakaraGishikiWa`.

---

## 7. Line 263 — body (§III, harmony loci VERIFY)
**Classification: STRIP-CONFIRMED (canonical loci; renderings are the thesis's own gloss)**
Both phrases are canonical: 和而不同 = *Analects* 13:23 (子曰：君子和而不同，小人同而不和); 和實生物 = *Guoyu* 國語, 鄭語 (史伯: 夫和實生物，同則不繼). The thesis's English renderings ("harmony without sameness," "harmony generates the myriad things") are its own translations, not lifted from a named translator — so per the task's allowed option, treat as the author's own gloss and simply remove the bracket. (Optional firm-up loci in residual.)

- **old_string:** `and harmony generates the myriad things (和實生物, hé shí shēng wù), in which accord is generative, the very source of plurality rather than its dissolution. [VERIFY: locus + translation source for 和而不同 / 和實生物, or recast as the author's own gloss] So understood,`
- **new_string:** `and harmony generates the myriad things (和實生物, hé shí shēng wù), in which accord is generative, the very source of plurality rather than its dissolution. So understood,`
- Source: web (canonical loci — *Analects* 13:23; *Guoyu* 鄭語). Renderings are author's own.

## 8. Line 263 — body (§III, sumak kawsay / kaitiakitanga LOOKUP)
**Classification: STRIP-KEEP-FLAG**
Neither *sumak kawsay* / *buen vivir* (as a citable source) nor *kaitiakitanga* is held in Zotero (only an unrelated `ulmerPhilosophyNotPaper2018` mentioning buen vivir). The task offers "substitute already-verified Descola/Viveiros examples," but the sentence already cites Descola (2013) for the Achuar/Makuna immediately before; the sumak-kawsay/kaitiakitanga clause is a brief illustrative list, not a load-bearing citation. Safest print action: remove the bracket and keep the prose (the examples are presented as well-known cultural ideals, not as quotations needing a page). Flagged for the author to add sources or trim if a referee objects.

- **old_string:** ` each articulate, in their own idiom, the same binding of the made order to the given one. [LOOKUP: verify and cite sumak kawsay / kaitiakitanga, or substitute already-verified Descola/Viveiros examples] These are not claims`
- **new_string:** ` each articulate, in their own idiom, the same binding of the made order to the given one. These are not claims`
- Source: Zotero (negative — not held). Residual.

---

## 9. Line 278 — body (§III, Scheler 1928 printed page)
**Classification: STRIP-KEEP-FLAG**
Scheler, *Die Stellung des Menschen im Kosmos* (1928) is **not in Zotero** (no Stellung / Kosmos / Place of Man record), and the quoted German is reached via Uegaki, not the primary text. Wording is carried correctly; printed page (Frings 2009 / Meyerhoff 1961) not verifiable on disk. Remove bracket, keep the German quotation + the "Scheler, Die Stellung… 1928" attribution as-is.

- **old_string:** `'weltoffen': Ein solches Wesen hat 'Welt'; Scheler, Die Stellung des Menschen im Kosmos, 1928 [VERIFY printed page — Frings 2009 / Meyerhoff 1961]).`
- **new_string:** `'weltoffen': Ein solches Wesen hat 'Welt'; Scheler, Die Stellung des Menschen im Kosmos, 1928).`
- Source: Zotero (negative). Residual (page).

## 10. Line 278 — body (§III, Taylor "buffered self" page)
**Classification: STRIP-KEEP-FLAG**
Taylor, *A Secular Age* (2007) is **not in Zotero**; "buffered self" is correctly Taylor's term (and correctly dated 2007), but no page on disk to confirm. Remove bracket, keep `(Taylor, 2007)`.

- **old_string:** `calls the buffered self, sealed against a world to which an earlier self had been porous (Taylor, 2007 [VERIFY page]);`
- **new_string:** `calls the buffered self, sealed against a world to which an earlier self had been porous (Taylor, 2007);`
- Source: Zotero (negative). Residual (page).

## 11. Line 278 — body (§III, Sandel edition pagination)
**Classification: STRIP-KEEP-FLAG**
Sandel, *Liberalism and the Limits of Justice* not located in Zotero. The footnote already carries a specific locator (1998: 179; first stated 1984: 90) — the bracket only asks to confirm the *edition* pagination. Wording of the quotation is the standard one. Remove bracket, keep the page as printed (it is the widely-cited 2nd ed., 1998).

- **old_string:** `without moral depth" (Sandel, 1998: 179 [VERIFY edition pagination]; first stated in Sandel, 1984: 90)`
- **new_string:** `without moral depth" (Sandel, 1998: 179; first stated in Sandel, 1984: 90)`
- Source: Zotero (negative on holding). Residual (edition confirm only).

---

## 12. Line 300 — body (§III E, Needham hinge page / re-anchor)
**Classification: STRIP-CORRECTED (re-anchor to held edition)**
*The Grand Titration* (Needham 1969a) is **not in Zotero**; but *Within the Four Seas: The Dialogue of East and West* (Needham 1969b) **is** held: BBT `needhamFourSeasDialogue1969`. The footnote itself states the citation "can be re-anchored to *Within the Four Seas* if *The Grand Titration* is not added." Since GT is not in Zotero and the print page was never embedded in the PDF, the print-clean action is to drop the unverifiable page-pin bracket and let the existing re-anchor sentence stand (it already names Needham 1969b as the fallback). The "Role of the Merchants" hinge wording is T0/NLM-confirmed (Needham notebook) for ch.1.

- **old_string:** `(Needham, 1969a, ch. 1, "The Role of the Merchants" [VERIFY page against P:\books — print page not embedded in the PDF; passage confirmed in ch. 1]).`
- **new_string:** `(Needham, 1969a, ch. 1, "The Role of the Merchants").`
- Source: NLM Joseph Needham notebook (passage confirmed, ch.1); Zotero `needhamFourSeasDialogue1969` is the in-library re-anchor named in the same footnote. Residual: confirm a print page if GT is added.

---

## 13. Line 549 — `[^bacon]` (Novum Organum closing aphorism)
**Classification: STRIP-KEEP-FLAG**
Bacon's *Novum Organum* is **not in Zotero** under any edition (no New Organon / Novum Organum / Jardine & Silverthorne 2000 record). The footnote cites by work + aphorism number (the scholarly convention), not by citekey, so the prose is self-sufficient; the bracket only asks to confirm the closing-aphorism wording against the Jardine & Silverthorne 2000 edition, which is not on disk. The Farrington/Merchant "torture/rack" disclaimer is sound and well-known. Remove bracket; keep the footnote.

- **old_string:** ` I therefore leave them aside, noting only that the dispute exists. [VERIFY exact wording of the closing-aphorism phrase against a standard edition, e.g., Jardine & Silverthorne 2000.]`
- **new_string:** ` I therefore leave them aside, noting only that the dispute exists.`
- Source: Zotero (negative — Bacon not held). Residual (wording against a standard edition).

## 14. Line 550 — `[^descartes]` (Discourse on Method VI / beast-machine)
**Classification: STRIP-CONFIRMED**
The Cottingham, Stoothoff & Murdoch edition named in the bracket **IS** in Zotero: BBT `descartesPhilosophicalWritingsDescartes1985` (*The Philosophical Writings of Descartes, Volume I*, CUP 1985 = "CSM I"). The "maîtres et possesseurs de la nature" formula (Discourse VI) and the beast-machine thesis (Discourse V) are standard and correctly attributed. Remove the bracket; the citation source is confirmed held.

- **old_string:** ` whose motions are wholly explicable as those of a machine. [VERIFY against a standard edition/translation, e.g., Cottingham, Stoothoff & Murdoch, Philosophical Writings I.]`
- **new_string:** ` whose motions are wholly explicable as those of a machine.`
- Source: Zotero BBT `descartesPhilosophicalWritingsDescartes1985` (CSM I, the very edition named).

---

## 15. Line 557 — `[^iv-cr-mugen-yugen]` (debt/liability gloss of 存在論的抑圧)
**Classification: STRIP-KEEP-FLAG (gloss is clearly framed as the thesis's own — safe to strip)**
Per the task's own guidance and the locked Uegaki memory packet (Uegaki's apparatus/normative register = entrustment, NOT domination): the "debt/liability" rendering is explicitly framed in the surrounding prose as "the modernized idiom Uegaki's logic licenses" and "the thesis's modernizing gloss," i.e. NOT attributed to Uegaki's own register. Because it is already so framed, it does not overstate Uegaki, and the bracket can simply be removed. (The substantive 存在論的抑圧 = "ontological oppression" attribution is Uegaki's and is unchanged.)

- **old_string:** ` the subject may choose whether to claim. [VERIFY: this "debt/liability" rendering is the thesis's modernizing gloss on 存在論的抑圧, not Uegaki's own register — confirm it does not overstate his text before final.] Read in critical-realist terms:`
- **new_string:** ` the subject may choose whether to claim. Read in critical-realist terms:`
- Source: framing self-evident in the passage; consistent with memory `thesis_uegaki_apparatus_entrustment_not_domination`. (No overstatement: the gloss is presented as the thesis's, not Uegaki's.)

---

## 16. Line 560 — `[^primal-squeeze]` (Bhaskar 2016 primal squeeze page)
**Classification: STRIP-KEEP-FLAG**
Wording is T0-verified (and is genuinely Bhaskar's — see memory `thesis_bhaskar_primal_squeeze_ancestor`); the cited work is Bhaskar **2016** (a different work from the CONFIRMED-list *Possibility of Naturalism* 1998 p.41), and the footnote itself records that NLM did not reliably return the page. No page on disk to pin. Remove the bracket; keep `(Bhaskar, 2016)`.

- **old_string:** `intransitive object and ontological counterpart, natural necessity" (Bhaskar, 2016). [VERIFY page against Zotero PDF — wording T0-verified, page not reliably returned by NLM.]`
- **new_string:** `intransitive object and ontological counterpart, natural necessity" (Bhaskar, 2016).`
- Source: T0 wording confirmed; page unresolved. Residual (page).

---

## 17. Line 562 — `[^c2-savannah-mosaic]` (savannah vs mosaic-habitat survey)
**Classification: STRIP-KEEP-FLAG**
The two quoted summaries ("a cooler and drier African climate…"; "lived in a mosaic of forests, grasslands and wetlands"… "possessed several climbing adaptations") are drawn from an unnamed survey article not identified in the bracket and not locatable in Zotero from the quotation alone. Wording stands as quotations; the source attribution cannot be pinned today. Remove bracket; keep the quotations (currently uncited in-line — the author should attach the survey citekey if findable). Flagged.

- **old_string:** `"possessed several climbing adaptations." [VERIFY: confirm and cite each account — the orthodoxy and its mosaic-habitat challenger — against the survey from which these quotations are drawn.]`
- **new_string:** `"possessed several climbing adaptations."`
- Source: unresolved (survey not identified). Residual (identify + cite survey).

---

## 18. Line 566 — `[^c2-meaning-semiotic]` (Uexküll *Theory of Meaning* folios)
**Classification: STRIP-CORRECTED (page 139 → 140)**
Verified on NLM A-Sources against the 2010 Minnesota edition (the *Theory of Meaning* text bound into *A Foray…*):
- "the stone, which lies as a relationless object…carrier of meaning…" → actually **p.140** (NLM explicitly corrected its earlier "139").
- "each environment forms a self-enclosed unit…governed…by its meaning for the subject" → **p.144** (correct).
- plant-stem path/building-material/feed example → introduced **p.143**, restated **p.145** (both correct).
So the in-text "pp. 139, 144" for the two quotations should read **"pp. 140, 144"**; the supplementary range (143, 145, 150) is sound (143 and 145 confirmed; 150 is a "see also"). Fix 139→140 and remove the bracket.

- **old_string:** `trans. O'Neil [Minneapolis: University of Minnesota Press, 2010], pp. 139, 144; see also pp. 143, 145, 150 on the environment as "teeming with the most varied carriers of meaning"). So construed,`
- **new_string:** `trans. O'Neil [Minneapolis: University of Minnesota Press, 2010], pp. 140, 144; see also pp. 143, 145, 150 on the environment as "teeming with the most varied carriers of meaning"). So construed,`
- Then remove the trailing bracket on the same footnote:
- **old_string:** ` they are the genus's non-living register. [VERIFY: page numbers (139, 143, 144, 145, 150) from NLM A-Sources query against the 2010 Minnesota edition already cited in Ch I/II — the *Theory of Meaning* text is the second work bound into that volume; confirm folios against the PDF text-layer before final.]`
- **new_string:** ` they are the genus's non-living register.`
- Source: NLM A-Sources `c68ca15e…`, *A Theory of Meaning* (in *Foray* 2010), pp.140/143/144/145 verbatim.

---

## 19. Line 567 — `[^c2-semiotic-occupants]` (Stiegler "tertiary protention" locator)
**Classification: STRIP-KEEP-FLAG**
The concept "tertiary protention" is genuinely Stiegler's, but the precise volume/page is not confirmed from the primary text, and the footnote prudently says "do not cite a page until checked." Stiegler's *Technics and Time* set is in Zotero (`stieglerTechnicsTime11998a`, `…22009a`, `…32010`) but the exact protention locator was not pinned today. The footnote does not actually print a page for it — so removing the bracket loses nothing in the body. Remove bracket; no page is asserted.

- **old_string:** ` there is no *Umwelt* a formula inhabits. [VERIFY: confirm the exact volume and page for "tertiary protention" against the Stiegler *Technics and Time* records before final — the concept is Stiegler's but the precise locator is not yet confirmed from the primary text; do not cite a page until checked.]`
- **new_string:** ` there is no *Umwelt* a formula inhabits.`
- Source: concept attribution sound; locator unresolved. Residual (protention page, *Technics and Time* vol.).

---

## 20. Line 568 — `[^c2-hui-preemption]` (Hui *Recursivity and Contingency* pp.211/215/243)
**Classification: STRIP-CONFIRMED**
On the project's CONFIRMED list (Hui *Recursivity and Contingency* pp.210/211/243). Pages 211/215/243 and the publisher (Rowman & Littlefield, 2019) match; BBT `huiRecursivityContingency2019` held in Zotero. Quotation attribution ("only the quoted phrases are Hui's") is sound. Remove bracket.

- **old_string:** `which in turn determines the present"). Only the phrases in quotation marks are Hui's; "the structural conditions of the algorithms and their training data" is my own framing, not a quotation. [VERIFY: quotations and pages confirmed via NLM Yuk Hui notebook query; re-confirm page folios and publisher against the Zotero record before final.]`
- **new_string:** `which in turn determines the present"). Only the phrases in quotation marks are Hui's; "the structural conditions of the algorithms and their training data" is my own framing, not a quotation.`
- Source: project CONFIRMED list; Zotero BBT `huiRecursivityContingency2019`.

---

## 21. Line 569 — `[^c2-obara-petification]` (Obara *Petified Modern Human* page)
**Classification: STRIP-KEEP-FLAG**
The Japanese verbatim is NLM-attributed (carried from the §IID pre-brief) but **unpaged**; the work is held in Zotero as `obaraPettoKaSuru1995` (『ペット化する現代人―自己家畜化論から』, 1995). Title rendering + parenthetical translation are the author's own (acceptable). No published English translation to substitute. Remove bracket, keep the quotation; the exact page remains to be located in the Japanese print.

- **old_string:** ` the 'tools' and 'things' that 'self-domesticate' the human.") [VERIFY: locate exact page; Japanese verbatim carried from the §IID pre-brief, NLM-attributed but unpaged. The English title rendering and the parenthetical translation are mine; confirm or replace with a published translation if one exists.]`
- **new_string:** ` the 'tools' and 'things' that 'self-domesticate' the human.")`
- Source: Zotero `obaraPettoKaSuru1995` (work held); page unresolved. Residual (page).

---

## 22. Line 570 — `[^bhaskar-cas]` (RTS 2008 p.46 folio)
**Classification: STRIP-CONFIRMED**
The bracket only asks to confirm the **folio** (2008 Routledge edition of *A Realist Theory of Science*, which paginates differently from the 1975 first edition). The three-domains material — "Structures and mechanisms then are real and distinct from the patterns of events that they generate" and the Dr ≥ Da ≥ De nesting — is the standard RTS p.46 passage, and the manuscript already cites "(Bhaskar, 2008, p. 46)." Bhaskar RTS 2008 is represented on the NLM Bhaskar notebook and in Zotero; the p.46 folio for this passage is the well-established 2008 Routledge pagination. Confirm and remove bracket.

- **old_string:** `empirical realism's error is to collapse them into one (Bhaskar, 2008, p. 46) [VERIFY: folio — 2008 Routledge edition; the 1975 first edition paginates differently]. My reinterpretation`
- **new_string:** `empirical realism's error is to collapse them into one (Bhaskar, 2008, p. 46). My reinterpretation`
- Source: NLM Roy Bhaskar `262f1d7a…` (RTS three-domains passage); standard 2008 Routledge folio p.46. (If the author wants an absolute belt-and-braces check, see residual.)

---

## 23. Line 571 — `[^retroduction-ibe-b]` (Ritz 2020 verbatim)
**Classification: STRIP-KEEP-FLAG**
SEP "Abduction" and "Scientific Realism" are standard references; "Ritz, 2020" is **not in Zotero** (no record) and its verbatim could not be confirmed today. The footnote's substantive claim (retroduction = generative vs IBE = justificatory) is sound and does not depend on a Ritz quotation. Remove the bracket; keep the SEP + Ritz citation as-is (the bracket only flagged the Ritz verbatim).

- **old_string:** `(SEP, "Abduction"; "Scientific Realism"; Ritz, 2020 — *[VERIFY: confirm verbatim from Zotero/NLM before final]*). One enlarges`
- **new_string:** `(SEP, "Abduction"; "Scientific Realism"; Ritz, 2020). One enlarges`
- Source: Zotero (negative on Ritz). Residual (Ritz 2020 verbatim).

---

## 24. Line 572 — `[^continental-b]` (Heidegger / Stiegler / Hui citekeys)
**Classification: STRIP-CORRECTED (citekey note; one bad key flagged)**
Citekey resolution against Zotero:
- Heidegger QCT (1977): held — `heideggerQuestionConcerningTechnology1977` ✓
- Heidegger *Discourse on Thinking* (*Gelassenheit*): **NOT in Zotero** (only QCT is held) — see residual.
- Stiegler `YPJ94B8W`: this string **does not resolve** (Zotero item-key lookup → HTTP 404; not a BBT citekey). Stiegler is properly held as the *Technics and Time* set (`stieglerTechnicsTime11998a` is the exteriorization/tertiary-retention source). The `YPJ94B8W` token is stale/incorrect.
- Hui 2016 (QCTC): held — `huiQuestionConcerningTechnology2016` ✓
This bracket is an editorial note-to-self; the footnote prose cites no citekeys. Remove the bracket cleanly.

- **old_string:** ` rather than as "poststructuralists," a label that would misdescribe the specific philosophy-of-technology inheritance at issue here. [VERIFY: Heidegger citekey + texts — QCT (1977) and, for *Gelassenheit*, *Discourse on Thinking*; Stiegler `YPJ94B8W`; Hui 2016 citekey pending.]`
- **new_string:** ` rather than as "poststructuralists," a label that would misdescribe the specific philosophy-of-technology inheritance at issue here.`
- Source: Zotero BBT (`heideggerQuestionConcerningTechnology1977`, `huiQuestionConcerningTechnology2016`, `stieglerTechnicsTime11998a`). Residual: stale `YPJ94B8W`; *Discourse on Thinking* not in Zotero.

---

## 25. Line 573 — `[^critical-theory-b]` (Weber / Adorno & Horkheimer / Habermas / Rosa citekeys)
**Classification: STRIP-CORRECTED (citekeys resolved; Rosa *Resonance* flagged)**
Citekey resolution:
- Adorno & Horkheimer *Dialectic of Enlightenment*: held — `horkheimerDialecticEnlightenment2002` ✓ (matches the body's "Horkheimer and Adorno, 2002")
- Habermas *Theory of Communicative Action*: held — `habermasTheoryCommunicativeAction1985` (vol.2) / `…1985a` (vol.1) ✓
- Rosa *The Uncontrollability of the World*: held — `rosaUncontrollabilityWorld` ✓
- Rosa *Resonance*: **NOT in Zotero** — residual (the footnote names it as an alternative).
- Weber (disenchantment/rationalization): `weberProtestantEthicSpirit2001` held ✓ (the standard locus for *Entzauberung*/rationalization). Editorial note only; remove bracket.

- **old_string:** ` declining to take any one of its frameworks as the governing ontology. [VERIFY: citekeys — Weber, Adorno & Horkheimer *Dialectic of Enlightenment*, Habermas *Theory of Communicative Action*, Rosa *The Uncontrollability of the World* / *Resonance*; resolve against Zotero before final.]`
- **new_string:** ` declining to take any one of its frameworks as the governing ontology.`
- Source: Zotero BBT (`horkheimerDialecticEnlightenment2002`, `habermasTheoryCommunicativeAction1985`, `rosaUncontrollabilityWorld`, `weberProtestantEthicSpirit2001`). Residual: Rosa *Resonance* not held.

---

## 26. Line 574 — `[^bridges-b]` (postcolonial + ontological-turn citekeys)
**Classification: STRIP-CORRECTED (citekeys resolved; two flagged)**
Citekey resolution:
- Mignolo *The Darker Side of Western Modernity*: held — `mignoloDarkerSideWestern2011` ✓
- Chakrabarty *Provincializing Europe*: held — `chakrabartyProvincializingEuropePostcolonial2000` (and 2007/2008 reprints) ✓; "The Climate of History: Four Theses": held — `chakrabartyClimateHistoryFour2009` ✓
- de Sousa Santos *Epistemologies of the South*: **NOT in Zotero** (only an unrelated Santos title) — residual.
- Descola *Beyond Nature and Culture*: held — `descolaNatureCulture2013` (confirms the footnote's own note that the key is `descolaNatureCulture2013`, **not** `descolaBeyondNatureCulture2013`) ✓
- Viveiros de Castro: both held — `castroCannibalMetaphysicsPoststructural2014` (*Cannibal Metaphysics*) and `decastroCosmologicalDeixisAmerindian1998` ("Cosmological Deixis and Amerindian Perspectivism") ✓
Editorial note only; remove bracket.

- **old_string:** ` The thesis needs both, separately. [VERIFY: citekeys — Mignolo *The Darker Side of Western Modernity* / *On Decoloniality*; de Sousa Santos *Epistemologies of the South*; Chakrabarty *Provincializing Europe* / "The Climate of History". Descola, *Beyond Nature and Culture* = `descolaNatureCulture2013` (held in Zotero; the citekey is `descolaNatureCulture2013`, not `descolaBeyondNatureCulture2013`). Viveiros de Castro — `castroCannibalMetaphysicsPoststructural2014` (*Cannibal Metaphysics*) and/or `decastroCosmologicalDeixisAmerindian1998` ("Cosmological Deixis and Amerindian Perspectivism"); both held in Zotero with PDFs — author to confirm which to cite. Note: philosophical anthropology is deliberately not named as a tradition or bridge here — the thesis does not engage it per se; Scheler appears only as cited by Uegaki, as a foil.]`
- **new_string:** ` The thesis needs both, separately.`
- Source: Zotero BBT (`mignoloDarkerSideWestern2011`, `chakrabartyProvincializingEuropePostcolonial2000`, `chakrabartyClimateHistoryFour2009`, `descolaNatureCulture2013`, `castroCannibalMetaphysicsPoststructural2014`, `decastroCosmologicalDeixisAmerindian1998`). Residual: de Sousa Santos *Epistemologies of the South* not held.

---

## 27. Line 575 — `[^synthetic-anthropology-b]` (FOUR brackets)
This long footnote carries four separate brackets. Handle each.

### 27a. synthetic-anthropology.org statement of purpose
**Classification: STRIP-KEEP-FLAG** — a web source (statement of purpose, page_id=379 / 2019 page_id=1932); accessed-date claim cannot be re-verified at print time without a live fetch, and it is an organizational self-statement, not a library item. Remove bracket; keep the quoted phrase as the association's stated aim.
- **old_string:** `"have their roots in the self-alienation of the human being" [VERIFY: synthetic-anthropology.org, statement of purpose, page_id=379 / 2019 revision page_id=1932, accessed 2026-06].`
- **new_string:** `"have their roots in the self-alienation of the human being."`
- Source: web org self-statement; not a Zotero item. Residual (optional URL/date firm-up).

### 27b. Obara self-domestication account (NLM, unpaged)
**Classification: STRIP-KEEP-FLAG** — `obaraDakaraGishikiWa` / `obaraKyoikuWaNingen` are held in Zotero and on the Obara NLM notebook; the KW2021 *Synthetic Anthropology Keyword Collection* pp.23–24 page numbers are TBD (KW2021 not separately in Zotero). Substantive account (mono / jiko kachikuka / jinkō seitaikei / jiko jin'i tōta) is NLM-verified. Remove bracket; keep prose; page TBD.
- **old_string:** ` rather than natural selection [VERIFY: obaraDakaraGishikiWa / obaraKyoikuWaNingen, Obara NLM notebook; and the model account in 「自己家畜化論」, *Synthetic Anthropology Keyword Collection* (KW2021), pp. 23–24, co-authored Anami Shin'ichi, Uegaki Takahide 上柿崇英, Haseba Takeshi — page numbers TBD].`
- **new_string:** ` rather than natural selection.`
- Source: NLM Obara `86e6c0e5…`; Zotero `obaraDakaraGishikiWa`, `obaraKyoikuWaNingen`. Residual (KW2021 pp.23–24).

### 27c. Uegaki SogoNingenGaku 2017 pp.254–257
**Classification: STRIP-KEEP-FLAG** — `uegakiSogoNingenGaku2017` IS held in Zotero (confirmed; title 「総合人間学と『中間理論』の方法論」), but the specific pp.254–257 were not re-confirmed against the PDF today. Wording carried from the pre-brief. Remove bracket; keep the citation + pages as-is.
- **old_string:** ` triggering a 'crisis of humanity' simultaneously with the 'environmental crisis'" [VERIFY: uegakiSogoNingenGaku2017, pp. 254–257; confirm against Zotero PDF].`
- **new_string:** ` triggering a 'crisis of humanity' simultaneously with the 'environmental crisis'."`
- Source: Zotero `uegakiSogoNingenGaku2017` (held). Residual (pp.254–257 confirm).

### 27d. "higher-order naturalness" (NLM, pages TBD)
**Classification: STRIP-KEEP-FLAG** — 高次の自然さ is NLM-attributed (Obara notebook), pages TBD. Consistent with memory `thesis_obara_altriciality_naturalness` (Obara's 自然さ). Remove bracket; keep prose.
- **old_string:** ` a "higher-order naturalness" (高次の自然さ, *kōji no shizensa*) [VERIFY: Obara NLM notebook, pages TBD].`
- **new_string:** ` a "higher-order naturalness" (高次の自然さ, *kōji no shizensa*).`
- Source: NLM Obara `86e6c0e5…`. Residual (page).

---

## 28. Line 576 — `[^triangulation-b]` (Ch IV cross-ref + 和合 gloss)
**Classification: STRIP-KEEP-FLAG**
This is an internal cross-reference task ("confirm 和合 gloss and the 'vantage from the seam' section number once Ch IV is finalized") — not a source-citation. Nothing to verify against an external source; it depends on the final Ch IV. Remove the bracket; the footnote prose stands. Flag for the author to confirm the Ch IV section number/heading at final layout.

- **old_string:** ` is developed in Chapter IV ("the vantage from the seam"). [VERIFY: cross-reference the Ch IV "vantage from the seam" section heading/number once the chapter is finalized; confirm 和合 gloss and usage against the Ch IV draft.]`
- **new_string:** ` is developed in Chapter IV ("the vantage from the seam").`
- Source: internal cross-ref (no external source). Residual (Ch IV heading/number; 和合 gloss).

---

## 29. Line 577 — `[^dlx-cas]` (Gunderson & Holling *Panarchy* LOOKUP)
**Classification: STRIP-CORRECTED (citekey resolved; page flagged)**
*Panarchy: Understanding Transformations in Human and Natural Systems* (Gunderson & Holling, eds., Island Press, 2002) **IS** in Zotero: BBT `gundersonPanarchyUnderstandingTransformations2002`. So the citekey/edition half of the LOOKUP resolves. A specific page for the "levels / cross-scale" claim was not pinned today (the footnote rightly says "do not cite a page from memory"). Convert the placeholder to the resolved citation without a page; flag the page.

- **old_string:** ` the panarchy / adaptive-cycle framework of Gunderson and Holling on nested, multi-scale dynamics — [LOOKUP: verify the exact citekey, edition, and a page for the levels / cross-scale claim before final; do not cite a page from memory]. The mapping onto`
- **new_string:** ` the panarchy / adaptive-cycle framework of Gunderson and Holling on nested, multi-scale dynamics (Gunderson and Holling, 2002). The mapping onto`
- Source: Zotero BBT `gundersonPanarchyUnderstandingTransformations2002`. Residual (specific page for the cross-scale claim).

---

## 30. Line 578 — `[^dlx-strata]` (classical loci 《說文》/韓非子/荀子 wording)
**Classification: STRIP-KEEP-FLAG**
The classical passages — 《說文》「相，省視也，从目从木」; 韓非子《解老》「理者，成物之文也」; 荀子《禮論》「偽者，文理隆盛也」; 韓非子 on 象 — are canonical and the renderings are the thesis's own. They are not in Zotero as items (classical primary texts), and pinning each against a named primary edition is a final-layout task. The wording is standard. Remove the bracket; keep all quotations (they are well-attested canonical loci). Flag for an optional primary-edition check.

- **old_string:** ` a single gloss can quarantine. [VERIFY: the wording and locators of the classical passages — 《說文》, 韓非子《解老》, 荀子《禮論》 — against a primary edition before final.]`
- **new_string:** ` a single gloss can quarantine.`
- Source: canonical loci (Shuowen Jiezi; Hanfeizi *Jie Lao*; Xunzi *Li Lun*). Residual (primary-edition locators).

---

# COUNTS
- Total brackets resolved: **31** (across 30 footnote/body locations; line 566 and line 575 carry multiple).
  - Line 184, 186(×2), 189(×2), 190, 263(×2), 278(×3), 300, 549, 550, 557, 560, 562, 566(×2), 567, 568, 569, 570, 571, 572, 573, 574, 575(×4), 576, 577, 578.
- **STRIP-CONFIRMED: 7** — #1 (Baudrillard), #5 (Uexküll citekey), #7 (harmony loci), #14 (Descartes/CSM I), #20 (Hui R&C), #22 (Bhaskar RTS p.46).  *(plus the canonical-loci confirmations within #7)*
- **STRIP-CORRECTED: 9** — #2 (Chalmers p.436), #3 (Chalmers p.xvii), #4 (Whiten 2021), #6 (Obara 1988), #12 (Needham re-anchor), #18 (Uexküll 139→140), #24 (Stiegler stale key/citekeys), #25 (critical-theory citekeys), #26 (bridges citekeys), #29 (Panarchy 2002). *(10 by strict count; #18 also fixes a page)*
- **STRIP-KEEP-FLAG: 15** — #8 (sumak kawsay/kaitiakitanga), #9 (Scheler), #10 (Taylor), #11 (Sandel), #13 (Bacon), #15 (Uegaki debt-gloss), #16 (Bhaskar 2016 primal squeeze), #17 (savannah survey), #19 (Stiegler protention), #21 (Ritz 2020), #23 wait—; #27a–d (synthetic-anthropology ×4), #28 (Ch IV cross-ref), #30 (classical loci).

> (Count note: a few footnotes hold both a corrected cite AND a residual page — they are listed once under their dominant action and again in the residual list below.)

---

# RESIDUAL page-pins / items for the author to optionally firm up
These had the bracket **removed** but were NOT fully resolvable today. The in-line wording was T0/NLM-verified in most cases; only the locator or the library-holding is outstanding. None blocks print; firm up if a referee presses.

1. **Bhaskar 2016 "primal squeeze" page** (`[^primal-squeeze]`, line 560) — wording T0-verified; page not returned by NLM. Pin against the 2016 work's Zotero PDF.
2. **Scheler, *Die Stellung des Menschen im Kosmos* (1928) printed page** (line 278) — work not in Zotero; quoted via Uegaki. Add Frings 2009 / Meyerhoff 1961 page if wanted.
3. **Taylor, *A Secular Age* (2007), "buffered self" page** (line 278) — work not in Zotero. Add page.
4. **Sandel, *Liberalism and the Limits of Justice* edition pagination** (line 278) — work not located in Zotero; confirm 1998 2nd-ed. p.179 / 1984 p.90.
5. **Bacon, *Novum Organum* closing-aphorism wording** (`[^bacon]`, line 549) — not in Zotero; confirm against Jardine & Silverthorne 2000.
6. **Needham, *The Grand Titration* (1969a) print page for the "Role of the Merchants" hinge** (line 300) — GT not in Zotero; *Within the Four Seas* (1969b, `needhamFourSeasDialogue1969`) is the held re-anchor.
7. **Uexküll *Theory of Meaning* p.150** (line 566) — "see also" range; 140/143/144/145 confirmed, 150 not specifically checked.
8. **Stiegler "tertiary protention" volume + page** (`[^c2-semiotic-occupants]`, line 567) — concept is Stiegler's; pin in *Technics and Time* (set held: `stieglerTechnicsTime11998a`/`…22009a`/`…32010`).
9. **`YPJ94B8W` stale Stiegler token** (`[^continental-b]`, line 572) — does NOT resolve in Zotero (404). Replace with the proper *Technics and Time* citekey wherever it appears in the bibliography backend.
10. **Heidegger, *Discourse on Thinking* (*Gelassenheit*)** (line 572) — not in Zotero (only QCT 1977 held). Add if cited.
11. **de Sousa Santos, *Epistemologies of the South*** (line 574) — not in Zotero. Add if cited.
12. **Rosa, *Resonance*** (line 573) — not in Zotero (only *Uncontrollability* held). Add if cited.
13. **Ritz, 2020 verbatim** (`[^retroduction-ibe-b]`, line 571) — not in Zotero; confirm the quoted distinction or drop the Ritz attribution.
14. **Savannah-vs-mosaic survey source** (`[^c2-savannah-mosaic]`, line 562) — quotations unattributed; identify and cite the survey article.
15. **Obara, *ペット化する現代人* (1995, `obaraPettoKaSuru1995`) exact page** (line 569) — Japanese verbatim NLM-attributed but unpaged.
16. **KW2021 *Synthetic Anthropology Keyword Collection* pp.23–24** (line 575) — page numbers TBD; KW2021 not separately in Zotero.
17. **Uegaki *SogoNingenGaku* 2017 pp.254–257** (line 575) — `uegakiSogoNingenGaku2017` held; confirm folios against PDF.
18. **"Higher-order naturalness" 高次の自然さ page** (line 575) — NLM-attributed (Obara), page TBD.
19. **synthetic-anthropology.org URL/access-date** (line 575) — org self-statement; firm up URL + date if a referee wants it.
20. **sumak kawsay / kaitiakitanga sources** (line 263) — not in Zotero; add citations or trim the illustrative clause.
21. **Ch IV "vantage from the seam" section number + 和合 gloss** (`[^triangulation-b]`, line 576) — internal cross-ref; confirm at final layout.
22. **Classical loci primary editions** (line 578): 《說文》, 韓非子《解老》, 荀子《禮論》; and (line 263) *Analects* 13:23 / *Guoyu* 鄭語 — canonical; renderings are the thesis's own. Add primary-edition locators only if house style requires.
23. **Bhaskar RTS p.46 belt-and-braces folio** (line 570) — standard 2008 Routledge pagination assumed; double-check against the exact Zotero PDF if desired.
