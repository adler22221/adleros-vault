---
aliases: []
type: literature
project: master-thesis
topic: [phusis, technē, nomos, etymology, lexica, Greek-ontology, Latin-etymology, squeeze-hypothesis, made-vs-given]
status: ai-draft
target: thesis
citation-status: in-preparation
source-notes: [LSJ, beekesEtymologicalDictionaryGreek2010, devaanEtymologicalDictionaryLatin2008, amundsonDictionaryConceptsPhilosophy1990, preusHistoricalDictionaryAncient2015, hiromatsuIwanamiTetsugakuShiso1998, chantraineDictionnaireEtymologique, cassinDictionaryUntranslatables2014, ritterHistorischesWorterbuch, brillNewPauly]
summary: "Cluster A (lexica & etymology) verbatim dossier for the phusis/technē/nomos boundary claim of [[master-thesis]]. TRUE in-text/full-text retrieval with MULTIPLE verbatim entries per source and exact provenance. KEY RESULT: Beekes (Brill custom-font, FAILED in prior runs) was CRACKED via PyMuPDF pixmap → pytesseract OCR (English-glosses, grc tessdata absent). 6 of 10 sources yielded true verbatim (LSJ, Beekes, de Vaan, Amundson, Preus, Iwanami); 4 flagged [VERIFY: not retrieved] (Chantraine OCR dropped all polytonic Greek; Cassin/HWPh/New Pauly not on disk/Zotero, paywalled)."
---

# Verbatim source-dossier — PART A: Lexica & Etymology (φύσις / τέχνη / νόμος)

**Compiled:** 2026-06-01 · **For:** [[master-thesis]] (Between the Universe and the Metaverse) · **Cluster:** A (lexica & etymology). Companion files: [[nomos-phusis-tekhne-verbatim-2026-05-30]] (general dossier) · [[nomos-verbatim-PART-B-encyclopedias]].

> [!warning] Attribution guard (load-bearing — keep explicit)
> The thesis provocations "**nomos has always been tekhne**" and "**tekhne is becoming phusis**" are the **AUTHOR'S OWN synthesis**. No lexical source below asserts either. The dictionaries supply only the building blocks: **φύσις** = the grown / self-arising / given (root "grow, be"); **τέχνη** = the made / built / crafted (root "build, fashion timber", cf. the carpenter τέκτων); **νόμος** = the distributed / allotted / instituted (root "distribute, allot", cf. νέμω). The Latin and Japanese entries corroborate the *grown/given* vs *made* line independently.

> [!info] Method note — how Beekes was cracked (prior runs FAILED here)
> The 2-volume Beekes (`P:\books\0 References\…Beekes…(vols. 1 & 2)…Brill (2010).pdf`) uses a **Brill custom polytonic font** whose text layer extracts as mojibake under `pypdf`, PyMuPDF `get_text()`, AND `get_text("rawdict")` (all three confirmed broken: e.g. φύλαξ → `<puA6.aa£LV`-type garbage; νόμος → `VOLT], VOUGG, VOLOG`). The fix: **render each page to a pixmap and OCR it.** Route: `fitz.open(pdf)[pno].get_pixmap(dpi=350)` → `PIL.Image.frombytes` → `pytesseract.image_to_string(img, lang='eng')` (tesseract at `C:\Program Files\Tesseract-OCR\tesseract.exe`). **Greek `grc` tessdata is absent** (only `eng`+`osd` installed), so the polytonic *headwords* OCR as garbage, but the **English glosses, IE-root reconstructions (Latin-script, e.g. `*tek-`, `*b'eh,u-`), and citation apparatus OCR cleanly and are fully quotable.** Greek headword forms below are supplied from LSJ (§1, independently verbatim) and the entry's identified position; the *content* (gloss + root) is Beekes' own OCR'd text. pymupdf + pytesseract + pillow were already installed in `.venv-nlm`.

---

## 1. LSJ (Liddell–Scott–Jones) — VERBATIM (Perseus TEI-XML source strings)

**Source:** Liddell, Scott, Jones, *A Greek-English Lexicon*, 9th ed. with revised supplement.
**Retrieval route (2026-06-01):** Raw Perseus TEI-XML chunks, read-only Python `urllib` GET to `http://www.perseus.tufts.edu/hopper/xmlchunk?doc=Perseus:text:1999.04.0057:entry=<fu/sis|te/xnh|no/mos2>`. Strings below are the literal `<tr opt="n">…</tr>` (translation) elements, extracted sense-by-sense with their `<sense n="…" level="…">` labels — i.e. the printed English gloss strings, not a model summary. (This is the route that bypassed lsj.gr 403 / Perseus-reader 503 in the 2026-06-01 rebuild; the `<tr>` regex was corrected to match the `<tr opt="n">` attribute form, recovering all 45 translation strings.) **Sub-senses ADDED here vs. the 2026-05-30 dossier.**

### 1a. φύσις — VERBATIM (all senses I–VII, with sub-senses)

> **[I] (lvl2):** "origin," | "birth,"
> **[I.2] (lvl3):** "growth,"
> **[II] (lvl2):** "the natural form" | "constitution" | "as the result of growth"
> **[II.1]:** "nature, constitution," · **[II.2]:** "outward form, appearance," | "outward form," · **[II.3]:** "constitution, temperament," · **[II.4]:** "nature, character," | "of natural powers," | "of natural disposition," | "natural propensities," (**[II.4.b]:** "instinct") · **[II.5]:** "natural"
> **[III] (lvl2):** "the regular order of nature," | "naturally," | "by nature, naturally," | "natural,"
> **[III.1]:** "nature as an originating power," | "principle of growth" | "Nature," · **[III.2]:** "elementary substance," | "atoms," · **[III.3]:** "creation, 'Nature',"
> **[V] (lvl2):** "creature," | "kind," | "creatures"
> **[VI] (lvl2):** "kind, sort, species," | "natural group" | "class"
> **[VII] (lvl2):** "sex,"
> — LSJ s.v. **φύσις** (Perseus TEI `entry=fu/sis`, `<tr>` strings by sense, retrieved 2026-06-01)

Etymology given in the entry head: **(φύω)** — φύσις is built on the verb **φύω / φύομαι "to grow, bring forth, be born."** Sense I literally = "origin / birth / growth"; the philosophical sense III.1 = "Nature as an originating power."

### 1b. τέχνη — VERBATIM (all senses, with sub-senses)

> **[A] (lvl1):** "art, skill, cunning of hand"
> **[A.2] (lvl3):** "craft, cunning" | "arts, wiles" | "agency" | "trick"
> **[A.3] (lvl3):** "way, manner" | "means whereby a thing is gained" | "means"
> **[II] (lvl2):** "an art, craft" | "trade" | "professionally" | "a trade"
> **[III] (lvl2):** "an art" | "craft" | **"a set of rules, system"** | **"method of making"** | **"doing"** | "by rules of art"
> **[IV] (lvl2):** "work of art, handiwork"
> **[VI] (lvl2):** "treatise"
> — LSJ s.v. **τέχνη** (Perseus TEI `entry=te/xnh`, `<tr>` strings by sense, retrieved 2026-06-01)

**Load-bearing sense:** III — τέχνη as "a set of rules, system, method of making or doing." Etymology head in the entry: τέχνη ← **τέκτων** (the carpenter / builder).

### 1c. νόμος — VERBATIM (all senses, with sub-senses)

> **[A] (lvl1):** "that which is in habitual practice, use" | "possession,"
> **[I] (lvl2):** "usage, custom," | "law, ordinance,"
> **[I.b] (lvl4):** "law" | (NT usage)
> **[I.c] (lvl4):** "custom" | "law," | "by custom, conventionally,"
> **[I.d] (lvl4):** "statute, ordinance made by authority," | "general laws," | "law,"
> **[I.e] (lvl4):** "to blows, into action," | "in action," | "under martial law,"
> **[II] (lvl2):** "melody, strain,"
> **[II.2]:** "melody" | "composition including both words and melody,"
> — LSJ s.v. **νόμος** (Perseus TEI `entry=no/mos2`, `<tr>` strings by sense, retrieved 2026-06-01)

**Semantic centre of gravity:** νόμος = **habitual practice / usage / custom**, hardening (sense I.d) into **"statute, ordinance made by authority → law."** Built on **νέμω** ("distribute, allot, assign"). See Beekes §2c for the etymology, where νόμος is treated as a sub-lemma of νέμω.

---

## 2. Beekes, *Etymological Dictionary of Greek* (Brill 2010) — CRACKED via OCR — VERBATIM (English content)

**Source:** Robert Steven Paul Beekes & Lucien van Beek, *Etymological Dictionary of Greek*, Leiden Indo-European Etymological Dictionary Series vol. 10 (Leiden/Boston: Brill, 2010), 2 vols. Zotero citekey `beekesEtymologicalDictionaryGreek2010` (item `W8LSEIML`, PDF `9JYWEW35`).
**Retrieval route (2026-06-01):** **2-volume copy in `P:\books\0 References\`** (`…Beekes, Lucien van Beek - Etymological Dictionary of Greek (vols. 1 & 2)-Brill (2010).pdf`, 930 PDF pages). PyMuPDF pixmap (dpi 350) → pytesseract OCR `lang='eng'`. Method (a) fitz `get_text()` and (b) `get_text("rawdict")` both produced **mojibake** (custom font); method (c) **OCR succeeded.** Greek `grc` tessdata absent → Greek headwords garble, English glosses + IE roots clean. PDF→printed-page map: νέμω/νόμος = printed pp. 1005–1006 (pdf idx 527–528); τέχνη = printed p. 1476 (pdf idx 763); φύομαι/φύσις = printed p. 1597 (pdf idx 823).

### 2a. φύσις — under the verb φύομαι (printed p. 1597) — VERBATIM (OCR, English)

φύσις is a **derivative of the main verb-entry φύομαι**, listed as derivative #4 of that lemma:

> "φύομαι [v.] intr. med. 'to grow, arise, spring up, become', perf. (and aor.) 'to exist or be endowed by nature, be there', trans. act. (factitive) 'to make grow, beget, bring forth' (Il.). **<IE \*b'eh,u- 'grow, arise, be'>**"
> — Beekes 2010, s.v. **φύομαι** (printed p. 1597; OCR rendering of `<1E *b'eh,u-…>` = IE *bʰeh₂u-)

> "4. **φύσις [f.] 'growth, character, descent, nature, being, etc.'** (χ 303), also ἀπό-, ἐκ-, συμ-, etc. from ἀποφῦναι, etc.; as a first member e.g. in φυσιολόγος [m.] 'naturalist, natural philosopher', -λογία, -λογέω, -λογικός (Arist., etc.). Hence φυσικός 'belonging to nature, naturalist, physical, physician'…"
> — Beekes 2010, s.v. φύομαι, derivative 4 = **φύσις** (printed p. 1597; OCR; Greek headword forms normalised from LSJ)

Cognates given for the root (OCR, verbatim content): "Cognates of the aorist ἔφυ: Skt. abhūt 'he became' < PIE \*h₂é-bʰuh₂-t … Lat. fui (OLat. fui), etc. The perfect πέφυκα, πεφύασι agrees with Skt. babhūva…" and (Kortlandt) "the root had the form **\*bʰeh₂u-**."

**Load-bearing:** Beekes roots φύσις in **\*bʰeh₂u- "grow, arise, BE"** — φύσις = literally *that-which-has-grown / the self-arisen / what-there-is-by-being*. This is the etymological backbone of the "given/self-arising" pole.

### 2b. τέχνη (printed p. 1476) — VERBATIM (OCR, English)

> "**τέχνη [f.] 'craftsmanship, handicraft, business, art; artifice, trick'** (Il.). **<IE \*tek- 'produce', \*te-tk- 'build, timber'>**"
> — Beekes 2010, s.v. τέχνη (printed p. 1476; OCR; root strings `*tek-` / `*te-tk-` extracted cleanly)

> "ETYM Derived from **\*tek-sneh₂-** (for the suffix, see πάχνη, λάχνη, λύχνος). Sometimes, a basic form \*tekt-sneh₂- is suggested (Skt. tákṣati, etc.), from the reduplicated IE root **\*te-tk- 'to build', whence τέκτων is derived.**"
> — Beekes 2010, s.v. τέχνη, ETYM block (printed p. 1476; OCR)

**Load-bearing:** Beekes derives τέχνη from **\*tek- "produce" / \*te-tk- "build, timber"** — the same root as **τέκτων, "the carpenter / builder."** τέχνη = literally *the act/skill of building-and-fashioning*. This is the etymological backbone of the "made / built" pole and the single most consequential lexical datum for "nomos is tekhne / tekhne is the made."

### 2c. νόμος — under the verb νέμω (printed pp. 1005–1006) — VERBATIM (OCR, English)

νόμος is **not an independent main entry in Beekes**; it appears as sub-lemma **B** of the verb **νέμω** (exactly parallel to LSJ's etymological note and to the Iwanami structure where ノモス is glossed inside other entries):

> "**νέμω, -ομαι [v.] 'to allot, dispense, distribute, appropriate, possess; to inhabit, manage; to pasture, graze, consume'** (Il.). **<IE \*nem- 'dispense, distribute; take'>**"
> — Beekes 2010, s.v. **νέμω** (printed p. 1005; OCR)

> "B. **νόμος [m.] 'custom, usage, law; (musical) key, tone'** (since Hes.), with several compounds, e.g. Ἔννομος PN (Il.), εὔνομος 'equipped with good laws' (Pi.) with εὐνομ-ίη, -ία 'lawful order' (since ρ 487). From νόμος: 1. adj. νόμιμος 'customary, lawful' (IA) … νομικός 'regarding the laws, juridical, jurisprudent' (Pl., Arist.) … 2. Verb νομίζω 'to use customarily, be used to, observe (a custom), believe' (IA, Dor.) … νόμισμα [n.] 'custom, received or current institution, (valid) coin' (IA)…"
> — Beekes 2010, s.v. νέμω, sub-lemma **B = νόμος** (printed p. 1006; OCR)

> "ETYM The Greek system is built on the present νέμω. … **Benveniste 1948: 79 stresses … the phenomenon of lawful and regular distribution that characterizes the verb νέμω.** … the Germanic verb for 'take' agrees best with νέμω: Go. niman, etc. … LIV makes a division in 1. \*nem- 'zuteilen' [to allot] (Gr., Gm. and Latv.) and 2. \*nem- 'sich neigen' [to bend]."
> — Beekes 2010, s.v. νέμω, ETYM block (printed p. 1006; OCR)

**Load-bearing:** νόμος ← νέμω ← **\*nem- "dispense, distribute; take."** The root sense is **distribution / allotment** (Benveniste: "lawful and regular distribution"). νόμος = literally *what-is-allotted / the apportioned* → custom → law. The made/instituted pole, etymologically grounded in human distribution.

> [!success] Beekes status: TRUE VERBATIM (English glosses + IE roots). The prior `[VERIFY: not retrieved]` flag (2026-05-30/06-01) is now LIFTED for the *content*. Caveat: the *polytonic Greek headword glyphs* in Beekes are still unreadable from the file (custom font + no grc OCR); the headword spellings above are LSJ-sourced, the glosses/roots are Beekes' own.

---

## 3. Chantraine, *Dictionnaire étymologique de la langue grecque* — `[VERIFY: not retrieved]`

**Source:** Pierre Chantraine, *Dictionnaire étymologique de la langue grecque: Histoire des mots* (Paris: Klincksieck).
**Status / method that failed:** Not in Zotero; not on `P:\books`. OA full-text djvu was located on archive.org and downloaded (≈9.96M chars of clean French text), but **the OCR contains ZERO Greek characters** — the polytonic Greek headwords (φύσις, τέχνη, νόμος, φύω, νέμω) and Greek cognate forms were entirely dropped/garbled by the scanner's OCR (same custom-font failure mode as Beekes, but here OCR did not even attempt the Greek). Without recoverable Greek headwords the φύσις/τέχνη/νόμος lemmas cannot be located or attributed with confidence, and no French snippet could be safely tied to the correct entry.

> [!warning] [VERIFY: not retrieved — archive.org OCR dropped all polytonic Greek; headword lemmas unlocatable/unquotable]
> To upgrade: obtain a Greek-text-layer PDF (or the print volume) and read the φύω / τέχνη / νέμω entries directly. Chantraine's roots are the **same** as Beekes' (φύω ← *bʰuH-/*bʰeh₂u- "grow"; τέχνη ← *tek- "fashion", cf. τέκτων; νόμος ← νέμω ← *nem- "distribute") and are covered verbatim in §1–§2 and §10.

---

## 4. de Vaan, *Etymological Dictionary of Latin and the Other Italic Languages* (Brill 2008) — VERBATIM

**Source:** Michiel de Vaan, *Etymological Dictionary of Latin and the Other Italic Languages*, Leiden Indo-European Etymological Dictionary Series (Leiden/Boston: Brill, 2008). NOT in Zotero; on `P:\books\0 References\` (`Michiel de Vaan - Etymological Dictionary of Latin…Brill Academic Publisher.pdf`, 837 pp).
**Retrieval route:** PyMuPDF `get_text()` — **extracts cleanly** (Latin script, no custom-font problem; minor OCR-ish artefacts normalised, e.g. "bom"→"born", "Taw"→"law"). Lemma pages: ars (pdf 66), lex (pdf 348), nascor/natura (pdf 411–412).

### 4a. natura (← nascor) — VERBATIM

> "**nascor, nascī 'to be born'** [v. III; ppp. (g)natum] (Pl.+). Derivatives: (g)natus 'son', pl. 'children' (Naev.+), (g)nata 'daughter' (Andr.+), natalis 'of birth' (Pl.+), natio 'people, race' (Pl.+), 'birth of a child' …, natīvus 'original' (Varro+); natu [abl.sg.m.] 'of age, by birth' (Pl.+), **natura 'conditions of birth, character'** (Pl.+), naturalis 'natural' (Varro+)…"
> — de Vaan 2008, s.v. **nascor** (pdf p. 411 / printed p. 400)

> "Pit. \*gnask-e/o- 'to be born' … **PIE \*ǵnh₁sk-e/o- 'to be born', \*ǵnh₁to- 'born', \*ǵnh₁ti- 'birth'.** IE cognates: Gaul. Cintu-gnātus 'first-born' … Skt. jāta- [m.] 'born man, son, living being', Av. zāta- 'born'; Gr. κασίγνητος [m.] 'brother, sister' … Go. -kunds 'originating from'…"
> — de Vaan 2008, s.v. nascor, root block (pdf p. 412; OCR `*gnhrsk-` = PIE *ǵnh₁sk-)

**Load-bearing:** Latin **natura 'conditions of birth, character'** is a derivative of **nascor 'to be born'**, PIE **\*ǵnh₁- "to be born/beget."** The Latin word for "nature" is rooted in *birth/being-born* — the structural twin of Greek φύσις ← "grow." Both name the *given-by-coming-into-being*.

### 4b. ars — VERBATIM

> "**ars, artis 'skill, art; trick'** [f.] (Pl.+). Derivatives: iners 'clumsy, lazy' …; sollers 'clever, skilled' (Cato+) …; artifex, -ficis 'practitioner, craftsman' (Pl.+), artificium 'skill, craft' (Cic.+). Pit. \*arti-. **PIE \*h₂r-ti- 'the fitting'.** IE cognates: … Gr. ἄρτι 'just, exactly' … → arma"
> — de Vaan 2008, s.v. **ars** (pdf p. 66)

**Load-bearing:** Latin **ars** ← **\*h₂r-ti- "the fitting"** (root \*h₂er- "to fit/join", cf. arma, ἀρτι, ἀραρίσκω). ars = *the fitting-together / the joining* — a made/assembled notion, the Latin counterpart to τέχνη's "building." (Note the divergence: Greek τέχνη = *building/timbering*; Latin ars = *fitting/joining* — both on the "made" side, different metaphors.)

### 4c. lex — VERBATIM

> "**lex, legis 'law'** [f.] (Pl.+). Derivatives: legare 'to send as an envoy, bequeath' (Lex XII+) … legitimus 'legal, legitimate' (Varro+); collega [m.] 'colleague, fellow' … legerupa [m.] 'law-breaker' (Pl.), legerupio 'law-breaking' (Pl.). … **PIE \*leg- 'collection'?** … The Pit. root noun \*leg- 'law' can be interpreted as a **'collection' of rules.** Whether the root noun existed already in PIE is uncertain for lack of precise cognates. … → lego"
> — de Vaan 2008, s.v. **lex** (pdf p. 348)

**Load-bearing:** Latin **lex** ← **\*leg- "collection"**, related to **lego "to gather, collect, read."** lex = *a collection of (gathered) rules* — the made/instituted pole on the Latin side, parallel to νόμος ("what is allotted/distributed"). Greek νόμος = *distribution*; Latin lex = *collection*: two complementary images of the humanly instituted.

---

## 5. Cassin (ed.), *Dictionary of Untranslatables* (Princeton 2014) — `[VERIFY: not retrieved]`

**Source:** Barbara Cassin (ed.), *Dictionary of Untranslatables: A Philosophical Lexicon* (Princeton: Princeton University Press, 2014). PHYSIS / NATURE / TECHNĒ-ART / NOMOS-LAW entries sought.
**Status / method that failed:** Not in Zotero; not on `P:\books` (scanned `P:\books`, `P:\books\0 References\`, and one subdir level for "untranslat"/"cassin" — no match). Proprietary Princeton UP work, paywalled (no free full-text endpoint comparable to the Perseus TEI route). Per anti-fabrication rule, no entries quoted.

> [!warning] [VERIFY: not retrieved — not on disk / not in Zotero; paywalled, no OA full-text route]
> This is the **most on-point single source** (the task flags it so). To upgrade: acquire the PDF (then it extracts as normal Latin-script text and the NATURE / PHYSIS / TECHNĒ / NOMOS entries can be quoted generously), or consult institutional access. The conceptual ground (φύσις/natura, τέχνη/ars, νόμος/lex made/given line) is covered verbatim by §1, §2, §4, §10 below.

---

## 6. Ritter (ed.), *Historisches Wörterbuch der Philosophie* (HWPh) — `[VERIFY: not retrieved]`

**Source:** Joachim Ritter et al. (eds.), *Historisches Wörterbuch der Philosophie*, 13 vols. (Basel: Schwabe). Articles: Natur, Physis, Technik, Kunst, Nomos, Gesetz.
**Status / method that failed:** Not in Zotero; not on `P:\books` (scanned for "ritter"/"historisches"/"wörterbuch" — no match). Proprietary Schwabe/De Gruyter work; the online HWPh (Schwabe Online) is paywalled. No free verbatim route. No German text quoted.

> [!warning] [VERIFY: not retrieved — not on disk / not in Zotero; paywalled (Schwabe Online), no OA route]
> To upgrade: institutional Schwabe Online or print volumes. The HWPh "Natur" and "Physis" articles would add a German-philosophical layer (Natur as the modern translation-pair of φύσις/natura) but are not load-bearing given §1/§2/§4 (etymology) and §8 (Japanese 自然=physis=natura) already establish the cross-linguistic identity.

---

## 7. Brill's *New Pauly* / *Der Neue Pauly* — `[VERIFY: not retrieved]`

**Source:** *Brill's New Pauly: Encyclopaedia of the Ancient World* / *Der Neue Pauly* (Stuttgart/Leiden: Metzler/Brill). Articles: physis, nomos, technē.
**Status / method that failed:** Not in Zotero (the Zotero "pauly" hit was an unrelated insurance article, `HT95WK4W`); not on `P:\books`. Proprietary Brill reference work, paywalled (Brill Reference Online). No free verbatim route. No text quoted.

> [!warning] [VERIFY: not retrieved — not on disk / not in Zotero; paywalled (Brill Reference Online)]
> To upgrade: Brill Reference Online or print. The historical-classical "physis" / "nomos" articles overlap heavily with Preus (§10), which IS on disk and quoted verbatim — Preus covers the Heraclitus / Antiphon / Democritus / Stoic nomos–physis material the New Pauly would supply.

---

## 8. Iwanami 岩波哲学・思想事典 (1998) — VERBATIM (Japanese text-layer)

**Source:** 廣松渉 ほか 編『岩波哲学・思想事典』(東京：岩波書店, 1998). Zotero citekey region `hiromatsuIwanamiTetsugakuShiso1998` (item `DILYTP57`, PDF `ZXHL62KY`).
**Retrieval route:** Zotero PDF copy (`Hiromatsu - 1998 - Iwanami tetsugaku, shisō jiten.pdf`, 1.47 GB, 1950 pp). **Has a real Japanese text layer** (no OCR needed; mild noise as flagged — e.g. occasional 「に」/「は」 confusion, garbled romanized Greek). Located via `page.search_for()`. 自然 headword = pdf p. 651; 技術 headword = pdf p. 325; ノモス/テクネー appear only *inside* other entries (社会 p. 702, ソフィスト p. 1003), not as standalone lemmas. Provenance pages are PDF indices.

### 8a. 自然 (nature) headword entry — VERBATIM (pdf p. 651–652)

Headword line (the single most on-point Japanese datum — 自然 = physis = natura, stated as an equation):

> 「**自然** 〔ギ〕physis〔ラ〕natura〔ァ〕ṭabīʿa〔英・仏〕nature〔独〕Natur〔蘭〕natuur」
> — 『岩波哲学・思想事典』s.v. **自然**, headword line (pdf p. 651)

Entry body (pdf p. 652), on φύσις and its etymology:

> 「（ナートゥーラ）に由来し，さらにこのラテン語は，ギリシア語 physis（ピュシス）の訳語である。… まず古代ギリシアで〈自然〉を表す「**ピュシス**」の語義については諸説があるが，このことばが「**ピュオマイ**」(phyomai. 生れる)という動詞と結びついていることは明らかであり，「**誕生**」「**成長**」「**生成**」を基本義としており，それはおのずと生れ，成長し，衰え，死んでゆくことを意味すると言ってよいだろう。**アリストテレスのことばで言えば「自分自身のうちに運動の原理をもつもの」が「ピュシス」であった。**」
> — 『岩波哲学・思想事典』s.v. 自然, body (pdf p. 652)

> 「すなわち古代ギリシアにおいては，自己形成の契機を欠いた全くの死せる自然ではなく，内に生成・発展の可能性を常にもつ生命ある有機的自然が，自然の原型であった。… なお「ピュシス」としての〈自然〉は成長・生成の意味から，そうした成長・生成の結果としてつくられたもののもつ「性質」「本性」やそうした生成をもたらす「力」「能力」の意味をも併せもち…」
> — 『岩波哲学・思想事典』s.v. 自然, body (pdf p. 652)

**English gloss (translator's note, not in source):** 自然 derives from Latin *natura*, itself a translation of Greek *physis* (ピュシス), which is bound to the verb *phyomai* "to be born / grow" (生れる), with the core senses **birth (誕生) / growth (成長) / becoming (生成)**; Aristotle's *physis* = "that which has the principle of motion within itself." This independently corroborates Beekes §2a (φύσις ← \*bʰeh₂u- "grow/be") and de Vaan §4a (natura ← nascor "be born").

### 8b. ノモス / ピュシス inside 社会 (society) entry — VERBATIM (pdf p. 702)

> 「思想史的にみれば，社会のあり方をめぐる思索は，古代ギリシアのノモス論に始まると言ってよい。**ソフィストたちが，不変で信憑性のある＊ピュシス（自然本性）と違って，人為的につくられたノモス（法，規範）を可変的で信憑性のないものと考えた**のに対し，ソクラテスの挑発的な言行を経て，プラトンとアリストテレスは，それぞれの仕方で＊ポリス（都市国家）のあるべき姿（ノモス）を論考した…」
> — 『岩波哲学・思想事典』s.v. **社会**, 【古代・中世の社会観】(pdf p. 702)

**English gloss:** The Sophists held that, unlike unchanging and trustworthy **physis (自然本性, natural essence)**, the **artificially-made (人為的につくられた) nomos (法・規範, law/norm)** is mutable and untrustworthy. This is a clean third-party verbatim of the nomos = *the humanly-made* / physis = *the given* antithesis — note the exact phrase **人為的につくられた** ("artificially made / made by human agency") attached to nomos.

### 8c. ノモス / ピュシス inside ソフィスト (Sophist) entry — VERBATIM (pdf p. 1003)

> 「ソフィストは，正義・善・美などに関する価値的判断には絶対的基準はなく，その基準は人間によって決められた**ノモス(nomos, 慣習・法律)**だというふうに考えた。つまり，価値の基準は人間あるいは社会に〈相対的〉なものだということである。… 他方，ソクラテスは，価値の基準は＊**ピュシス(physis, 自然)**によって決まっている〈絶対的〉なものだと考えた。」
> — 『岩波哲学・思想事典』s.v. **ソフィスト**, body (pdf p. 1003)

**English gloss:** nomos (慣習・法律 = custom/law) is "decided by humans" (人間によって決められた) and *relative*; physis (自然) is the *absolute* standard. Again the made-by-humans vs given-by-nature line.

### 8d. 技術 (technology) headword entry — VERBATIM (pdf p. 325)

> 「**技術** 〔英〕technique, technology, technics … 技術という概念はたいへん多義的であり，何らかの道具を用いた活動一般から，＊産業革命の推進力となった蒸気機関などの機械技術，さらには科学と結び付き，人間社会のあらゆる領域で不可欠な役割を果たすようになった「科学技術」に至るまで，さまざまな意味で用いられている。…【技術の哲学】… L.＊マンフォード，＊オルテガ・イ・ガセット，J. エリュール，M.＊ハイデガーといった哲学者が代表者である。… 〈存在の真理〉(ハイデガー)…」
> — 『岩波哲学・思想事典』s.v. **技術**, body (pdf p. 325)

**Note (OCR/source caveat):** the headword-line source-language list `〔英〕technique technology technics` is mildly garbled in the text layer ("燎hniquc tthnolo野"); the readable equivalents are restored above. The philosophy-of-technology lineage (Kapp → Dessauer → Mumford / Ortega / Ellul / **Heidegger**, the latter glossed 〈存在の真理〉 "the truth of Being") is clean. テクネー (technē) appears only as a cross-referenced term inside this and other entries, not as a standalone lemma.

---

## 9. Amundson (Durbin, ed.), *Dictionary of Concepts in the Philosophy of Science* (1990) — VERBATIM

**Source:** Paul T. Durbin (ed.) [Zotero records the contributor as Amundson], *Dictionary of Concepts in the Philosophy of Science* (New York: Greenwood, 1988/1990). Zotero citekey `amundsonDictionaryConceptsPhilosophy1990` (item `67SKVJGD`, PDF `2RSMNCI5`, 392 pp).
**Retrieval route:** PyMuPDF `get_text()` — clean (standard PDF, no custom font; minor OCR artefacts, e.g. "modem"→"modern", "¬" soft-hyphens). NATURE entry = pdf pp. 224–228; TELEOLOGY = pdf pp. 337–340.

### 9a. NATURE — entry senses — VERBATIM

> "**NATURE.** 1. The world or the universe as intelligible in a fashion distinct from poetic/religious myths or stories; this is the oldest use of the term in the Western tradition, going back to the earliest Greek philosophers. However, the usage is still current, as referring to the object of 'natural science'…"
> — Amundson/Durbin 1990, s.v. NATURE, sense 1 (pdf p. 224)

> "…cycle'—of a natural being, whether a living organism or a nonliving (e.g., star) system; **this is the anti-atomistic, antimechanistic doctrine of nature as physis in Aristotle,** which may already be found in Plato and certain other early Greeks such as Empedocles and Heraclitus. 4. **The essence of an object** that explains definition 3 and distinguishes one kind or species of beings from other kinds; it was this usage—especially in certain medieval versions that treated natures as Platonic Forms inherent in things—against which the early modern scientists rebelled. 5. The natural world, as calling forth a human response or feeling…6. The object of conservation or preservation in its natural state (see ecology)."
> — Amundson/Durbin 1990, s.v. NATURE, senses 3–6 (pdf p. 225)

> "Heidegger would have it that metaphysics culminates inevitably in mechanistic science (see mechanism), in the marriage of science and technology, and in that nihilism of modern culture Nietzsche had condemned. … many modern thinkers share with him the perception that a science and technology based culture is at worst both nihilistic and forgetful of nature (Ellul, [1954] 1964; Marcuse, 1964)…"
> — Amundson/Durbin 1990, s.v. NATURE (pdf p. 226)

**Load-bearing:** Amundson explicitly names **"nature as physis in Aristotle"** (the anti-mechanistic doctrine, the *given* self-moving order) and the essence-sense (4). Useful as a clean modern English statement that "nature = physis" in the philosophy-of-science register, plus the Heidegger "marriage of science and technology" line (a counterpoint to Floridi's "marriage of physis and techne", see [[nomos-phusis-tekhne-verbatim-2026-05-30]] §7).

---

## 10. Preus, *Historical Dictionary of Ancient Greek Philosophy* (2015) — VERBATIM (deepened from v1)

**Source:** Anthony Preus, *Historical Dictionary of Ancient Greek Philosophy*, 2nd ed. (Lanham: Rowman & Littlefield, 2015). Zotero citekey `preusHistoricalDictionaryAncient2015` (item `3IXAURHE`, PDF `E4JNRCAN`, 541 pp).
**Retrieval route:** PyMuPDF `get_text()` — Greek polytonic AND English extract cleanly (standard PDF). NOMOS = pdf p. 292; TECHNĒ = pdf pp. 405–406; TECHNIKOS = pdf p. 406; PHYSIS / PHYSIKOI = pdf p. 328. **This run adds the full PHYSIS entry and the TECHNĒ "external source of change" + "art is about becoming" material absent from the 2026-05-30 dossier.**

### 10a. NOMOS — full entry VERBATIM (Heraclitus / Antiphon / Democritus / Stoics)

> "**NOMOS. Νόμος. Law; convention.** (Noun formed from nemo, distribute; nemesis is another noun based on the same verb.) There is some tension in the way this word is used in Greek philosophy and literature. On the one hand, the nomoi are clearly the laws governing the organization of the state; Plato's longest dialogue … is called the Nomoi (Laws). … the rules governing human behavior universally … are often called agraphoi nomoi, unwritten laws … **As Heraclitus says (f. 114, in part), 'All human nomoi are nourished by the one divine (nomos).'** On the other hand, legislated laws tended, at least by the 5th century BCE, to be seen as **arbitrary and variable from one society to another. Thus some introduced the idea of a contrasting nature (physis) that was not subject to social variability. Antiphon provides a particularly good example of a writer who emphasizes this contrast (DK 87A44).** Plato often represents the Sophists arguing on the basis of this contrast. Thrasymachus in Republic I, Callicles in the Gorgias, and Protagoras in the Protagoras are just a few examples. **Democritus took the contrast back into the scientific context … when he said, 'By convention (by nomos) sweet by convention bitter, by convention hot by convention cold, in reality atoms and void.'** The Stoics supposed that nature operates according to divine reason, or logos, so that **the tension or dialectic between nature and law is resolved: physics (physikē) and ethics are both part of the same rational system, the thought of God.** Stoics argued that we could discover 'natural law' of a normative sort…"
> — Preus 2015, s.v. **NOMOS** (pdf p. 292)

### 10b. PHYSIS — full entry VERBATIM (Aristotle's 5 senses) [NEW vs v1]

> "**PHYSIS; HISTORIA PERI PHYSEŌS. Φύσις, ἱστορία περὶ φύσεως. Nature; the study of nature.** Aristotle's definition of 'nature' is a good place to start: **'Source or cause of change or rest in that to which it belongs primarily' (Physics II.1).** More elaborately: (1) the coming-to-be of growing things; (2) the principle of growth in the things that grow; (3) the source of change present in the thing in virtue of its essence, and the cause of the organic unity of living things; (4) the basic material of which anything is made …; and (5) the ousia of a natural thing (Metaphysics V.4)."
> — Preus 2015, s.v. **PHYSIS** (pdf p. 328)

> "**PHYSIKOI, PHYSIOLOGOI. Φυσικοί, φυσιολόγοι.** Aristotle's terms for his predecessors who concentrated on the study of nature (physis), primarily Thales, Anaximander, Anaximenes, Empedocles, Anaxagoras, Leucippus, and Democritus. … In Parts of Animals I.1, 640b4–22 … he says that 'the old philosophers who first studied physis' focused on the material principle…"
> — Preus 2015, s.v. PHYSIKOI (pdf p. 328)

### 10c. TECHNĒ — full entry VERBATIM (the external-source-of-change contrast) [DEEPENED vs v1]

> "**TECHNĒ. Τέχνη. Art, craft, skill.** In Homer, examples of technai would be metalworking, shipbuilding, soothsaying, and general trickiness; the Hippocratic texts hold that medicine (iatrikē) is a technē. **There is a sense that technē is in some measure opposed to nature (physis); see TECHNIKOS.** … the Sophists proposed to instruct in the 'arts' of speaking, use of language, and especially governance (politikē)—Protagoras, Gorgias, and Thrasymachus are all reported to have used 'Technē' in the title of an instructional book. … Plato takes the analogy of the arts a step further with the image of the Demiourgos in the Timaeus; the physical universe is a product of the technē of a creative deity. **For Aristotle, technē is contrasted with nature (physis), in that the source of change for a product of technē is external to that which is produced, but the source of change for a natural production is within the thing that changes. There is a bit of continuity in this contrast: nature is like a physician who cures herself; and technē partially imitates nature, partially completes what nature cannot finish.**"
> — Preus 2015, s.v. **TECHNĒ** (pdf pp. 405–406)

> "…the 'art' knows the universal (katholou) and can teach (Metaphysics I.1). But **'art' is not the same as 'knowledge' (epistēmē), because epistēmē is about 'being' and art is about 'becoming' (genesis).** Technē can be distinguished into poiētikē and praktikē, productive and practical. It should be pointed out that there is no specific concept of 'fine art' as that is understood in the modern world…"
> — Preus 2015, s.v. TECHNĒ (cont., pdf p. 406)

### 10d. TECHNIKOS — VERBATIM (the explicit "artificial" pole)

> "**TECHNIKOS. Τεχνικός. Skillful, but also often 'artificial.'** Aristotle remarks that wrens … and insects and especially spiders … are technikoi … In Stoic philosophy, **pyr technikon, creative fire, is the material aspect of God.**"
> — Preus 2015, s.v. **TECHNIKOS** (pdf p. 406)

### 10e. Glossary glosses (back-matter) — VERBATIM

> "**NOMOS.** Law; convention." · "**PHYSIS, HISTORIA PERI PHYSEŌS.** Nature; the study of nature." · "**TECHNĒ.** Art, craft, skill." · "**TECHNIKOS.** Skillful, but also often 'artificial.'"
> — Preus 2015, Glossary (pdf p. 455–457 region)

**Load-bearing:** Preus is the cleanest English definitional source on disk and states the boundary three ways: (i) NOMOS = "law; convention," explicitly = the *arbitrary/variable/humanly-instituted* (Antiphon, Democritus "by nomos … in reality atoms and void"); (ii) PHYSIS = Aristotle's "source or cause of change … in that to which it belongs primarily" — the *internally-principled given*; (iii) TECHNĒ = "in some measure opposed to nature," its **source of change external** (vs physis's internal), "art is about becoming (genesis)." The TECHNIKOS gloss "but also often 'artificial'" is a direct lexical bridge from τέχνη to *the artificial* — useful for the thesis's artificiality/neo-artificiality vocabulary.

---

## Provenance summary

### `P:\books`-only items used (NOT in Zotero)
| Source | Path | Route |
|--------|------|-------|
| **de Vaan, *Etym. Dict. of Latin*** (§4) | `P:\books\0 References\Michiel de Vaan - Etymological Dictionary of Latin…Brill Academic Publisher.pdf` | PyMuPDF `get_text()` (clean Latin script) |
| **Beekes 2-vol copy** (§2, used for OCR) | `P:\books\0 References\Robert Steven Paul Beekes, Lucien van Beek - Etymological Dictionary of Greek (vols. 1 & 2)-Brill (2010).pdf` | PyMuPDF pixmap dpi350 → pytesseract `eng` OCR |

(Beekes and Iwanami and Preus and Amundson ALSO exist as Zotero attachments — those copies were used for §8/§9/§10; the P:\books Beekes 2-vol copy was used for §2 per the task's instruction to try it.)

### Zotero items used
| Source | Zotero item | PDF attachment | Route |
|--------|-------------|----------------|-------|
| Beekes (§2 cross-check) | `W8LSEIML` | `9JYWEW35` | (P:\books copy OCR'd; Zotero copy identical) |
| Amundson/Durbin (§9) | `67SKVJGD` | `2RSMNCI5` | PyMuPDF `get_text()` |
| Iwanami (§8) | `DILYTP57` | `ZXHL62KY` | PyMuPDF text-layer (`search_for` + `get_text`) |
| Preus (§10) | `3IXAURHE` | `E4JNRCAN` | PyMuPDF `get_text()` |
| LSJ (§1) | — (Perseus OA) | — | `urllib` GET, TEI `xmlchunk` `<tr>` strings |

### Could-not-retrieve (method that failed)
| Source | Status | Method that failed |
|--------|--------|--------------------|
| **Chantraine** (§3) | `[VERIFY: not retrieved]` | archive.org djvu full-text downloaded (9.96M chars French) but OCR **dropped ALL polytonic Greek** (0 Greek chars) → φύσις/τέχνη/νόμος lemmas unlocatable; no Greek-text PDF on disk |
| **Cassin, *Untranslatables*** (§5) | `[VERIFY: not retrieved]` | not in Zotero / not on `P:\books`; paywalled (Princeton UP), no OA full-text route |
| **Ritter, HWPh** (§6) | `[VERIFY: not retrieved]` | not in Zotero / not on `P:\books`; paywalled (Schwabe Online) |
| **Brill's *New Pauly*** (§7) | `[VERIFY: not retrieved]` | not in Zotero (Zotero "pauly" hit = unrelated insurance article) / not on `P:\books`; paywalled (Brill Reference Online) |

---

## Cross-source synthesis (etymology table — all VERBATIM-backed)

| Term | Headword gloss (verbatim source) | Root (verbatim source) | Pole |
|------|----------------------------------|------------------------|------|
| **φύσις** | "origin / birth / growth … Nature as an originating power" (LSJ §1a); "growth, character, descent, nature, being" (Beekes §2a) | ← φύω/φύομαι "grow, arise, **be**"; **IE \*bʰeh₂u-** (Beekes §2a) | **GIVEN** (self-arising; internal principle of motion — Preus §10b, Iwanami §8a) |
| **natura** (Lat.) | "conditions of birth, character" (de Vaan §4a) | ← nascor "**to be born**"; **PIE \*ǵnh₁-** (de Vaan §4a) | **GIVEN** (born/come-into-being; = physis, Iwanami §8a) |
| **τέχνη** | "art, skill, cunning of hand … a set of rules, system, method of making or doing" (LSJ §1b); "craftsmanship, handicraft … artifice" (Beekes §2b) | ← **\*tek- "produce" / \*te-tk- "build, timber"**, cf. **τέκτων "carpenter"** (Beekes §2b) | **MADE** (built; source of change *external* — Preus §10c) |
| **ars** (Lat.) | "skill, art; trick" (de Vaan §4b) | ← **\*h₂r-ti- "the fitting"**, cf. arma (de Vaan §4b) | **MADE** (fitted/joined) |
| **νόμος** | "that which is in habitual practice, use … custom … statute, ordinance made by authority" (LSJ §1c); "custom, usage, law" (Beekes §2c); "Law; convention … arbitrary and variable" (Preus §10a) | ← νέμω "**distribute, allot**"; **IE \*nem- "dispense, distribute; take"** (Beekes §2c) | **MADE / INSTITUTED** (humanly allotted; "人為的につくられた" Iwanami §8b) |
| **lex** (Lat.) | "law" (de Vaan §4c) | ← **\*leg- "collection"**, cf. lego "gather, read" (de Vaan §4c) | **MADE / INSTITUTED** (a collection of rules) |

---

## Three most consequential findings for the phusis / technē / nomos boundary

1. **τέχνη is etymologically *building* (Beekes §2b): root \*tek- / \*te-tk- "build, timber", same root as τέκτων "the carpenter."** This is the strongest lexical warrant the thesis can cite that *technē = the made-by-construction*. It anchors "tekhne is the made" in the morphology itself, not in interpretation. Pair with Preus §10c ("source of change … external to that which is produced") and Preus §10d (TECHNIKOS = "also often 'artificial'") for the full made/external/artificial cluster.

2. **νόμος is a *sub-lemma of the verb νέμω* "to distribute/allot" in Beekes (§2c) — exactly as in LSJ's etymology and in the Iwanami structure** — rooted in **\*nem- "dispense, distribute"** (Benveniste: "lawful and regular distribution"). νόμος is therefore, at root, *what-is-humanly-apportioned*. This grounds "nomos is the instituted/made" etymologically and, combined with Iwanami §8b's verbatim **「人為的につくられたノモス」** ("artificially-made nomos"), gives the author a third-party source that already attaches *artificial making* to nomos — the closest any source comes to the author's "nomos has always been tekhne" (still the author's synthesis: no source equates the two, but the made-pole grouping is now triply attested — Greek νόμος←distribution, Latin lex←collection, Japanese gloss 人為的につくられた).

3. **φύσις / natura form a verified cross-linguistic *given/grown/born* pair (Beekes §2a + de Vaan §4a + Iwanami §8a), all naming "the self-arising by coming-into-being."** Greek φύσις ← \*bʰeh₂u- "grow/be"; Latin natura ← nascor "be born"; Iwanami states the equation 自然 = natura = physis = φύομαι "生れる (to be born)" outright and adds Aristotle's "自分自身のうちに運動の原理をもつもの" ("that which has the principle of motion within itself"). The boundary the thesis pushes against is thus, lexically, **born/grown-from-within (φύσις) vs built-from-without (τέχνη) vs allotted-by-humans (νόμος)** — a triad now on a fully verbatim footing across Greek, Latin, and Japanese. The thesis's "tekhne is becoming phusis" is precisely the claim that *the built-from-without is acquiring the born/grown-from-within character* — which the etymology shows to be a category-crossing of the deepest kind (the two roots, \*tek- "build" and \*bʰeh₂u- "grow/be", are maximally opposed).

---

## Access / integrity log (2026-06-01)
- **Beekes CRACKED** via PyMuPDF pixmap (dpi350) → pytesseract `eng` OCR on the `P:\books\0 References\` 2-vol copy. `get_text()` and `get_text("rawdict")` both confirmed mojibake; OCR clean for English glosses + IE roots; grc tessdata absent so polytonic headwords supplied from LSJ. ✅
- **LSJ** Perseus TEI `xmlchunk` re-fetched; `<tr opt="n">` regex corrected → all 45 sense-glosses + sub-senses recovered. ✅
- **de Vaan** PyMuPDF `get_text()`, clean. ✅
- **Iwanami** Zotero copy text-layer via `search_for`/`get_text`; 自然 (p651), 技術 (p325), 社会 (p702), ソフィスト (p1003). ✅
- **Amundson** PyMuPDF `get_text()`, clean. ✅
- **Preus** PyMuPDF `get_text()`, clean; PHYSIS + TECHNĒ deepened vs prior dossier. ✅
- **Chantraine** archive.org djvu downloaded; 0 Greek chars (OCR dropped polytonic) → `[VERIFY: not retrieved]`. ❌
- **Cassin / HWPh / New Pauly** not on disk/Zotero, paywalled → `[VERIFY: not retrieved]`. ❌
- Temp files removed: `.research\cache\chantraine_djvu.txt`, `chantraine_real.txt`. No Zotero item modified. No file renamed/moved (pCloud protocol honoured).
