---
aliases: []
type: literature
project: master-thesis
status: ai-draft
target: thesis
topic: [page-verification, needham, hui, floridi, illich, platform-governance, uegaki-char-perfect]
citation-status: citable
source-notes: [needhamScienceCivilisationChina1956, "5DYVKEM6", huiQuestionConcerningTechnology2016, huiArtCosmotechnics2021, floridiInformationVeryShort2010, illichToolsConviviality1973, gillespieCustodiansInternetPlatforms2018, uegakiJikoKanketsuShakai2022b]
summary: "Page-resolution + char-perfect re-extraction note for Ch.3-6 [VERIFY: page] flags. Pages confirmed IN-TEXT against actual Zotero PDFs / P:\\books PDFs / NLM. Maps each flag to confirmed-page+citekey / corrected-page / still-pending+reason. Uegaki Japanese quotes re-extracted character-perfect from local text-layer PDFs (vol.1=uegaki2021A, vol.2=uegaki2021B)."
---

> [AI draft | task: verification-resolutions | date: 2026-06-01 | method: in-text search of ACTUAL sources via PyMuPDF over Zotero storage PDFs + P:\books PDFs; NLM (notebook_query) only for works not held locally]
> Links: [[master-thesis]] · [[ch3-6-verbatim-2026-06-01]] · [[hui-organizing-inorganic-qi-2026-06-01]] · [[floridi-argument-reconstruction-2026-06-01]] · [[nomos-phusis-tekhne-CONSOLIDATED-2026-06-01]]
>
> **Discipline:** Every "confirmed" page below was read from the printed run-head/folio of the source's own text layer (not model-reported). "Corrected" = the flagged page was wrong and the true page is given. "Pending" = the source is not available to me locally and could not be paginated. Nothing here is fabricated; where a page cannot be verified, it is marked pending with the reason.
>
> **Page-index vs printed-folio caution:** Several prior notes recorded a *PDF page index* as if it were a *printed page*. Distinguished explicitly below.

---

## Resolution table

| # | Flag (work / passage) | Flagged page | Resolution | Confirmed page | Citekey | Source read |
|---|---|---|---|---|---|---|
| 1 | **Needham SCC Vol.2** — organicism vs atomism ("Taoist organicism and Democritean-Epicurean atomism"; "conservancy-dictated bureaucratism") | pp.337–338 | **CONFIRMED** (the comparison sentence sits on p.338; section runs 337→338) | **p.338** (continuous from 337) | `needhamScienceCivilisationChina1956` (R5Y6IBYE) | Zotero PDF att. 3M7E7JJA, pdfidx 366, run-head "338" |
| 2 | **Needham SCC Vol.2** — worldview as "mirror image" / "heavenly counterpart of the bureaucracy upon earth" (Book of Changes) | **p.288** | **CORRECTED** — p.288 is about Granet & numerical symbolism; the mirror-image / heavenly-counterpart passage is on **pp.337–338**, immediately adjacent to the organicism passage | **pp.337–338** (not 288) | `needhamScienceCivilisationChina1956` (R5Y6IBYE) | Zotero PDF att. 3M7E7JJA: "heavenly counterpart" pdfidx 365 (folio 337); "mirror image of Chinese bureaucratic society" pdfidx 366 (folio 338); folio 288 verified = Granet, *not* this passage |
| 3 | **Needham SCC Vol.7 Pt.2** — material forces ("underneath lie the material forces of climate, geography and social integration") | (no page given) | **CONFIRMED + paginated** | **p.43** | `5DYVKEM6` | Zotero PDF att. 4GBTGH3H, pdfidx 92, folio 43 (span-verified) |
| 3b | **Needham SCC Vol.7 Pt.2** — water-works / topography→corvée passage | (bundled into 5e) | **CONFIRMED but on a DIFFERENT page than 3** — and the draft's tail "…making Chinese feudalism 'bureaucratic'" is NOT on this page (that clause is from *Grand Titration*, conflated) | **p.5** (water-works passage); tail-clause = pending (Grand Titration, see #8) | `5DYVKEM6` | Zotero PDF att. 4GBTGH3H, pdfidx 54, folio 5 (span-verified) |
| 4 | **Hui, *Question Concerning Technology in China*** — "the Chinese have no equivalents of the categories that the Greeks called techne and physis" | **p.52** | **CORRECTED** — quote is on **p.34** | **p.34** (not 52) | `huiQuestionConcerningTechnology2016` (CWX5W69K) | Zotero PDF att. 7UFSB2I2, pdfidx 52; bracketing folios: pdfidx 50=folio 32, pdfidx 51=folio 33, pdfidx 54=folio 36 → pdfidx 52 = folio 34 |
| 5 | **Hui, *Art and Cosmotechnics*** — "organized inorganic … becomes the organizing inorganic" | **p.247** | **CORRECTED** — passage is on **p.227** | **p.227** (not 247) | `huiArtCosmotechnics2021` (7RRD47HE) | Zotero PDF att. VAKYNS2G, pdfidx 247, folio 227 (span-verified); related "organizing inorganic" force at folio 224 |
| 6 | **Hui, *Art and Cosmotechnics*** — "technology becomes nomos" | **p.78** | **CORRECTED + reworded** — there is **no** sentence "technology becomes nomos" in this book. The intended passage is Schmitt-framed: "a new nomos of the earth … such a new nomos is determined by technology." It is on printed **p.58** (the "p.78" in prior notes = the **PDF page index**, pdfidx 78, not the folio) | **p.58** (printed); = pdfidx 78 | `huiArtCosmotechnics2021` (7RRD47HE) | Zotero PDF att. VAKYNS2G, pdfidx 78, folio 58; only other "nomos" hits = bibliography (folio 301). No systematic technē/nomos/physis triad in this book (it is in QCT-China §§8–10) |
| 7 | **Floridi, *Information: A Very Short Introduction* (2010)** — *dedomena* ("data in Greek"; pure data) | (confirm VSI / RHPI) | **CONFIRMED present in VSI 2010, Ch.2 "Data"** (definition reads as quoted). VSI PDF has **no extractable folios** → exact VSI folio not machine-confirmable; commonly cited as VSI **p.23**. Cross-pagination: the same definition is firmly paginated in Floridi, *The Philosophy of Information* (2011) **Ch.4, pp.85–86** (per RHPI 2016, ch.18) | VSI: **p.23 (approx.; folio not extractable)** · PI 2011: **pp.85–86** (firm) | `floridiInformationVeryShort2010` (XVC8NSC3) | Zotero PDF att. 8YFLMQLJ, pdfidx 23–24, 61 (text confirmed, footer folios not in text layer); NLM Floridi notebook RHPI cross-ref |
| 8 | **Needham, *The Grand Titration*** — "the four factors: geographical, hydrological, social and economic" | ("four factors" page) | **PENDING** — *Grand Titration* is **not in Zotero**, **not in P:\books**, and the NLM copy is an **unpaginated text source** (no printed folio recoverable). Passage text confirmed verbatim; page not verifiable from any available source. (Conventionally Ch.6 "Poverties and Triumphs…", commonly ~p.214 in the 1969 Allen & Unwin ed. — UNVERIFIED, do not cite as fact) | — pending — | (no citekey; not catalogued) | NLM "Joseph Needham" src 7c55bfb3 (verbatim, no page) |
| 9 | **Gillespie, *Custodians of the Internet*** — "right but not the responsibility" / safe-harbor | **p.44** | **CONFIRMED** | **p.44** | `gillespieCustodiansInternetPlatforms2018` (8JIFT74Z) | Zotero PDF att. BZ284QZ2, pdfidx 52 run-head "THE MYTH OF THE NEUTRAL PLATFORM 44"; corroborated by book's own index ("the right but not the responsibility," 31, 44, 96) |
| 10 | **Gillespie, *Custodians of the Internet*** — "content disappears without explanation and rules change with notification" / "shockingly opaque" | **p.199** | **CONFIRMED** (and the draft's "extraction artefact" worry is resolved: the book really does print "rules change with notification") | **p.199** | `gillespieCustodiansInternetPlatforms2018` (8JIFT74Z) | Zotero PDF att. BZ284QZ2, pdfidx 207 run-head "WHAT PLATFORMS ARE, WHAT THEY SHOULD BE 199"; "handed over to private companies" at folio 197 |
| 11 | **Pasquale, *The Black Box Society*** — "The values and prerogatives that the encoded rules enact are hidden within black boxes" (Intro) | **p.8** | **PENDING** — **not full-text in NLM** (bibliography-only), **not in Zotero**, **not in P:\books**. The "p.8" came from a secondary OA PDF, not confirmable against the Harvard UP print | — pending — | (no citekey; add to Needs Review) | NLM A-Sources: "not present" |
| 12 | **Klonick, "The New Governors"** (Harvard L. Rev. 131) — "operating outside the boundaries of the First Amendment"; "They are the New Governors of online speech" | **131:1598 / p.1599** | **PENDING** — **not full-text in NLM** (bibliography-only), **not in Zotero**. Vol/start-page (131:1598) is a journal-metadata fact, but the page-exact placement of the quoted clauses is **not confirmable** against the HLR PDF | — pending (vol. 131, p.1598 start is metadata, not passage-page) — | (no citekey; add to Needs Review) | NLM A-Sources: "not present" |
| 13 | **Suzor, *Lawless*** — "This is what I mean when I say that intermediaries govern in a lawless way" + the other 4 sentences | (pages unknown) | **PENDING** — **not full-text in NLM** (only cited by Gillespie), **not in Zotero**, **not in P:\books**. Page-exact citation not confirmable | — pending — | (no citekey; add to Needs Review) | NLM A-Sources: "not present" |
| 14 | **Illich, *Tools for Conviviality*** — modernized / "demeaning" poverty; radical-monopoly definition | **p.82** (a prior note "corrected" p.84→p.82) | **CORRECTED back to p.84** for the Zotero edition. The Zotero copy is the **1973 Harper & Row original** (citekey `illichToolsConviviality1973`), where modernized/demeaning poverty is **p.84** and the radical-monopoly definition is **p.65**. The "p.82" was edition-specific to the **1975 Fontana reprint** the NLM copy used. Since the thesis citekey and the attached PDF are the **1973** ed., cite **p.84** | **p.84** (1973 Harper & Row ed.; def at p.65). NB: p.82 is correct only for the 1975 Fontana ed. | `illichToolsConviviality1973` (FRSMXKFK — **already in Zotero**; the ch3-6 draft's "not yet in Zotero" note is outdated) | Zotero PDF att. P6K4NJIG (title page: "Ivan Illich / Tools for Conviviality / 1973"): "modernized poverty"/"demeaning poverty" pdfidx 89 folio 84; radical-monopoly def pdfidx 70 folio 65 |

### Bhaskar
Skipped per task (pp.6/11/12 already confirmed).

---

## Cataloguing corrections surfaced during verification (for the author; no Zotero writes made)
- **Illich** *Tools for Conviviality* **IS already in Zotero** as `illichToolsConviviality1973` (FRSMXKFK) with the 1973 PDF attached (att. P6K4NJIG). The ch3-6-verbatim note's repeated "not yet in Zotero / citekey reserved" is **stale** — update it.
- **Edition fork to record in the citekey/notes:** Zotero holds the **1973 Harper & Row** ed.; NLM holds the **1975 Fontana** reprint. Page numbers differ (poverty p.84 vs p.82; verify any other Illich page against the *intended* edition).
- **Needham Vol.7 Pt.2** material is split across two pages, not one: ideology/material-forces **p.43**; water-works/topography **p.5**. The "…making Chinese feudalism 'bureaucratic'" clause in the ch3-6 5e block is **not** on Vol.7 Pt.2 p.5 — it belongs to *The Grand Titration* and should be re-sourced or dropped.
- **Hui page slips** (p.52→34; p.247→227; "p.78" was a PDF index = printed p.58) are the kind of error 劉 (scope/precision) and 米 (term precision) would flag — worth a global pass for PDF-index-as-folio confusion.

---

## Uegaki char-perfect re-extraction

**Provenance for this whole section.** The standalone essay PDF `〈無限の生〉と〈有限の生〉ーー〈自己完結社会〉の未来についての一つ考察.pdf` is an **image-only scan with NO text layer** (0 extractable characters on all 8 pages) — it CANNOT be the source of character-perfect text. All passages below are therefore re-extracted from the **two monograph PDFs, which DO carry a clean Japanese text layer**:
- **Vol.1 (上)** = `P:\books\Synthetic Antrhopology 総合人間学\上柿崇英\uegaki2021A.pdf` (331 pp.)
- **Vol.2 (下)** = `P:\books\Synthetic Antrhopology 総合人間学\上柿崇英\uegaki2021B.pdf` (281 pp.) = Zotero `uegakiJikoKanketsuShakai2022b` (VESTLJGF)

Extracted via `.venv-nlm` PyMuPDF 1.27.2.3. **Printed folios** read from the page's own header digit; PDF-index→folio offset in Vol.2 is `printed = pdfidx − 8`. Ruby/furigana glyph noise (stray "0" tokens) was stripped; **no characters in the quoted strings were altered**. The earlier `[VERIFY: re-extract char-perfect]` flag is now **resolved** — corrections vs the OCR-noisy ch3-6 version are called out inline.

### U-1. 意のままになる生 / 〈無限の生〉 — the world-view/anthropology definition (Vol.2 下, printed p.110)

「それは〈無限の生〉、すなわち「意のままになる生」こそが人間のあるべき姿であると考え、人間の使命とは、それを阻む「意のままにならない生」の現実を改変し、克服していくことであると考えるひとつの「世界観＝人間観」に他ならない。」

- Provenance: Vol.2 (下), uegaki2021B.pdf, pdfidx 118, folio **110**.
- vs OCR draft: matches in substance; note Uegaki writes 「世界観＝人間観」 with a full-width equals (＝), and uses 〈　〉 angle brackets for 〈無限の生〉. Char-perfect.

### U-2. The "anthropology of freedom" lineage — Locke / Rousseau / Kant (Vol.2 下, printed p.111)

「最初に見ていきたいのは、Ｊ・ロック（J. Locke）やＪ・Ｊ・ルソー（J. J. Rousseau）らによって基礎づけられ、Ｉ・カント（I. Kant）においてひとつの完成を見た人間理解、〈自立した個人〉の思想の母体ともなった「自由の人間学」についてである。」

- Provenance: Vol.2 (下), pdfidx 119, folio **111**.
- Correction vs OCR draft: names use **full-width Roman + full-width parens** — Ｊ・ロック（J. Locke）, Ｊ・Ｊ・ルソー（J. J. Rousseau）, Ｉ・カント（I. Kant） — and the draft's half-width "(J. Locke)" rendering is an OCR normalisation. The phrase is 「自由の人間学」 (kagi-kakko), not 〈　〉. Char-perfect above.

### U-3. 約束された本来性 + the Rousseau line (Vol.2 下, printed p.112)

「そして第二は、「約束された本来性」、すなわちこの世界には未だ現実には現れていないものの、未来において実現することが約束された「本来の人間」なるものが存在するという想定である。それが見事に体現されているのは、「人間は生まれながらにして自由であるが、しかしいたるところで鉄鎖につながれている」というルソーの言葉であるだろう。」

- Provenance: Vol.2 (下), pdfidx 120, folio **112**.
- vs OCR draft: matches. Uegaki's embedded Rousseau rendering is 「…鉄鎖につながれている」 (kanji 鉄鎖, okurigana つながれて). Char-perfect.

### U-4. Extension from political → ontological freedom (Vol.2 下, printed pp.112–113)

「問題は、こうした人間に対する規定が、やがて「政治的自由」の脈絡から外れ、次第に人間存在そのものへと一般化された「存在論的自由」を論じるものへと拡張されていったことである。そしておそらくそのときにこそ、われわれは〈無限の生〉へと続く扉を開くことになったのである。」

- Provenance: sentence spans the foot of folio **112** (pdfidx 120: 「…一般化された「存」) onto the head of folio **113** (pdfidx 121: 「在論的自由」を論じる…). Char-perfect, joined across the page break.

### U-5. 〈無限の生〉＝「意のままになる生」 as the story of ontological liberation (Vol.2 下, printed p.114)

「われわれがそこで語っていたのは、諸個人があまねく「存在論的抑圧」から解放され、あるべき「存在論的自由」を獲得していく物語、すなわちあの〈無限の生〉＝「意のままになる生」の物語だったのである。」

- Provenance: Vol.2 (下), pdfidx 122, folio **114**. Char-perfect.

### U-6. 〈有限の生〉 and its five principles (Vol.2 下, printed p.129)

「そしてそれは、〈無限の生〉が否定し続けてきた「意のままにならない生」、すなわち人間存在の根源的な原理としての〈有限の生〉そのものに他ならない。」

「ここではそれを、改めて〈有限の生〉の五つの原則――①「生物存在の原則」、②「生受の条件の原則」、③「意のままにならない他者の原則」、④「人間の〈悪〉とわざわいの原則」、⑤「不確実な未来の原則」――」

- Provenance: Vol.2 (下), pdfidx 137, folio **129** (the five principles run 129→130).
- Correction vs OCR draft: the ch3-6 note dated these to "pp.129–130; essay p.5". The monograph location is **pp.129–130**; the essay folio cannot be confirmed (no text layer). The five principle names are char-perfect above (note ④ is 「人間の〈悪〉とわざわいの原則」, with 〈悪〉 in angle brackets and わざわい in hiragana).

### U-7. table 6 (表６) — the five-period schema (Vol.2 下, printed p.15)

Header (char-perfect): 「表６　本章における「第一期」から「第五期」までの時代区分と時代の特徴」.
Column heads: 期間の概要 ／ およその期間 ／ **時代の象徴**.

| 期 | 期間の概要 | およその期間 | 時代の象徴 |
|---|---|---|---|
| 第一期 | 近代国家日本の成立から敗戦まで | 1868年～1945年 | 重厚な〈生活世界〉と〈社会的装置〉の萌芽 |
| 第二期 | 戦後復興から高度経済成長期まで | 1945年～1970年 | 構造転換の過渡期と〈旅人〉の時代 |
| 第三期 | 高度消費社会の隆盛からバブル崩壊まで | 1970年～1995年 | 〈郊外〉の成立と〈旅人〉の定住化 |
| 第四期 | 情報化とグローバル化の進展まで | 1995年～2010年 | 「情報世界」の台頭と〈漂流人〉の出現 |
| 第五期 | いまわれわれが立っている地点 | 2010年～ | 〈自己完結社会〉の成立 |

- Provenance: Vol.2 (下), pdfidx 23, folio **15**.
- Corrections vs OCR draft: (a) the date separator is the Japanese wave-dash **〜/～** (e.g. 「1868年～1945年」), not the hyphen the draft used; (b) the third column is titled **時代の象徴** ("symbol of the era"), which the draft's summary loosely rendered as "Title / characteristic"; (c) the draft's slash-joined cells (e.g. "…の萌芽／…") are formatting, not Uegaki's text — the real table separates 概要 and 象徴 into distinct columns. Cell strings above are char-perfect.

### U-8. 〈漂流人〉(drifter) — definition (Vol.2 下, printed p.40; first coinage p.5)

「さて、本書では、これまで見てきた〈郊外〉生まれの人々を指して〈漂流人〉と呼ぶことにしよう。かつての〈旅人〉たちが、〈故郷〉という名の「母港」を後に大いなる「目的地」へとこぎ出した船だとするなら、〈漂流人〉は、はじめから帰るべき「母港」も、向かうべき「目的地」も、あるいは自身の立ち位置を確認するための「羅針盤」さえも失った漂泊船のようである。」

- Provenance: Vol.2 (下), pdfidx 48, folio **40** (as the ch3-6 draft had). NB the term is **first coined** earlier at folio **5** (pdfidx 13) with the variant verb 「…〈漂流人〉と呼ぶことにしたい。」 — if the scaffold wants the first-introduction page, it is **p.5**. Char-perfect.

### U-9. 〈承認不安〉(recognition anxiety) — main statement (Vol.2 下, printed p.36) + note 144 (printed p.93)

「とりわけ「第四期」の後半になると、少なくない人々が自身の“居場所”をめぐって苦しみ、「承認不安」とも呼べる事態に直面するようになっていた。」

note (144): 「ここでの「承認不安」は、おそらく「自由な個性の全面的な展開」を人生の理想として素朴に信じた人々が、理想と現実の狭間で挫折していくことを通じて生じてきたものである。」

- Provenance: main statement Vol.2 (下) pdfidx 44, folio **36**; note 144 Vol.2 (下) pdfidx 101, folio **93**.
- **Correction vs OCR draft:** the draft placed note 144 at "≈ p.96" — the actual folio is **p.93**. Char-perfect.

### U-10. 〈自己完結社会〉— the canonical definition (Vol.1 上, はじめに, printed p.i)

「〈自己完結社会〉の成立とは何を意味するものなのだろうか。それは第一に、われわれが高度化した社会システムへの依存を深めることによって、結果的に目の前の他者、物理的に接触する生身の人間に対して、直接的な関わりを持つ必然性を感じられなくなっていく事態を指している。」

- Provenance: Vol.1 (上), uegaki2021A.pdf, pdfidx 3, front-matter folio **i** (はじめに).
- **Major correction vs OCR draft.** The ch3-6 note gave the 自己完結社会 definition as 「…情報技術、ロボット/人工知能技術、生命操作技術とともに肥大し続ける〈社会的装置〉に人々が深く依存し、生身の他者と関わっていく必然性、生身の身体とともに生きる必然性が失われていく社会のことである。」 — **that exact sentence does NOT appear in either local PDF** (searched both volumes for 「肥大し続ける」「生身の他者と関わっていく必然性」「生身の身体とともに生きる必然性」: zero hits). It was an NLM-excerpt reconstruction/paraphrase, not Uegaki's text. The genuine canonical definition is the はじめに passage above (printed p.i). Two related sub-concepts Uegaki names on pp.i–ii: 〈生の自己完結化〉 and 〈生の脱身体化〉. **Use the verbatim above; do not quote the "肥大し続ける〈社会的装置〉" version.**

---

## Method / negative results
- Tooling: `P:\_AI agents\full-research-workflow\.venv-nlm\Scripts\python.exe` + PyMuPDF; helper scripts written to `.research\cache\_zq.py` (Zotero read API) and `.research\cache\_pdfsearch.py` (in-text PDF search). Zotero local read API only (no writes; FREEZE respected).
- Works with NO locally/NLM-paginable source (pages unverifiable, marked pending): **Pasquale *Black Box Society*, Klonick "New Governors", Suzor *Lawless*, Needham *Grand Titration*.** Recommend cataloguing these into a Zotero "Needs Review" collection (with PDFs) before the page-exact citations are finalised.
- Floridi VSI 2010 PDF is present but its OUP-small-format text layer omits footer folios; VSI page reported as approximate (p.23) and cross-anchored to the firmly-paginated PI 2011 pp.85–86.
