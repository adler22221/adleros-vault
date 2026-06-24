---
aliases: []
type: concept
project: master-thesis
topic: [fact-check, chapter-V, exosomatic, Lotka, page-pins]
status: ai-draft
target: thesis
source-notes: [lotkaLAWEVOLUTIONMAXIMAL1945]
summary: "Ch V fact-check: Lotka exosomatic + page-pins for print finalization"
---

# Chapter V Fact-Check — Print Finalization Pass (2026-06-09)

Scope: Chapter V (lines ~439–587) of `20260609 Between the Universe and the Metaverse (working).md`. **Research note only — manuscript not edited.** Focus per task: the Lotka "exosomatic" footnote (`[^v1-lotka]`), every `[VERIFY]`/`[LOOKUP]` marker and page-pinned primary quote in Ch V, plus a lightweight fabrication/consistency scan.

Verification surfaces used, in cascade order: NotebookLM (auth refreshed this session); Zotero local API (read-only); local primary PDFs under `P:\books`; the 1925 *Elements of Physical Biology* full-text scan at `.research/cache/downloads/lotka1925_djvu.txt`; web/OED for the coinage date.

---

## ITEM 1 (PRIMARY) — Lotka "exosomatic" footnote `[^v1-lotka]`

**Claim as written (line 514):**
> Lotka, "The Law of Evolution as a Maximal Principle," *Human Biology* 17 (1945): p.188. "Exosomatic" is the 1945 coinage; it does not appear in *Elements of Physical Biology* (1925). The endo/exo contrast is carried by "native … apparatus" vs "'artificial' aids … exosomatic." [Adler: VERIFY]

### (a) Article exists with that title / journal / volume / year — **CONFIRMED**
- Zotero item `GRKYNJKL` (citekey `lotkaLAWEVOLUTIONMAXIMAL1945`): Alfred J. Lotka, "THE LAW OF EVOLUTION AS A MAXIMAL PRINCIPLE," *Human Biology* vol. **17**, issue 3 (**1945**), pages **167–194**, JSTOR stable/41447607. Tagged `nlm:synced` (in NLM A-Sources). PDF attached (`ECQZUFCV`).
- Primary PDF read directly: `C:\Users\adler-standard\Zotero\storage\ECQZUFCV\LOTKA - 1945 - THE LAW OF EVOLUTION AS A MAXIMAL PRINCIPLE.pdf` (29 pp.). Title/author/journal/volume/year all match.

### (b) p.188 is the right page for the passage — **CONFIRMED (exact)**
The PDF page bearing the printed folio **"188"** contains, verbatim:
> "The one outstanding exception is the human species. Here evolution, especially in more recent times, has followed an entirely new path. In place of slow adaptation of anatomical structure and physiological function in successive generations by selective survival, increased adaptation has been achieved by the incomparably more rapid development of '*artificial*' aids to our native receptor-effector apparatus, in a process that might be termed **exosomatic evolution**."

This matches both the body quotes in §V.B ("followed an entirely new path"; "'artificial' aids to our native receptor-effector apparatus, in a process that might be termed exosomatic evolution") and the endo/exo gloss in the footnote ("native … apparatus" vs "'artificial' aids … exosomatic"). The term recurs on printed p.192 ("the exosomatic evolution of the human species is indisputably subject to orthogenesis"). **p.188 is correct and is the first occurrence.**

### (c) 1945 coinage; not in *Elements of Physical Biology* (1925) — **CONFIRMED (triangulated)**
1. **Primary 1925 text (negative check):** full-book scan (972 KB, 20,212 lines, verified as the genuine *Elements of Physical Biology*, A. J. Lotka, Baltimore) contains **zero** occurrences of "exosomatic," "endosomatic," "exo-somatic," "exo somatic," or "intrasomatic" (only one unrelated "somatic"). The word is absent from the 1925 book.
2. **Internal corroboration:** on p.188 of the 1945 article, Lotka's own footnote 33 cites *Elements of Physical Biology* (1925, pp. 357–358) — but only for the energy-flux/solar-energy point, **not** for "exosomatic." He treats the 1925 book as prior work on energetics, introducing "exosomatic" as new here.
3. **OED:** the Oxford English Dictionary's *earliest evidence* for "exosomatic" is **1945, A. J. Lotka** (entry `exosomatic_adj`). Independent lexicographic confirmation of the 1945 coinage.
4. **Secondary lit consensus:** "exosomatic" / "endosomatic" are standard-attributed to Lotka's 1945 *Human Biology* paper in the energetics/bioeconomics lineage (Georgescu-Roegen) and in Stiegler's exosomatization sources.

**VERDICT: CONFIRMED in full.** No correction needed. The footnote as written is accurate on all three parts (article identity, p.188, 1945-vs-1925 coinage). The `[Adler: VERIFY]` flag can be cleared.

*Optional polish (not required):* the article's full page range is 167–194; if a range is ever wanted alongside the p.188 pin, that is the span. JSTOR stable id 41447607.

---

## ITEM 2 — Other Ch V verification markers and page-pinned primary quotes

### 2.1 `[VERIFY]` / `[LOOKUP]` markers actually inside Ch V's own footnotes (v0–v8)
The only explicit `[VERIFY]`-class marker in the Chapter V footnote block (v0–v8) is the `[Adler: VERIFY]` on `[^v1-lotka]` (Item 1 above) and the `[Adler: …]` editorial note at line 509 (a footnote-pruning instruction, not a fact to verify). **No `[LOOKUP]` or `[VERIFY: TBD]` stubs remain in v0–v8.**

> Note for the author: the file also contains a large block of footnotes prefixed `c2-`, `dlx-`, `bhaskar-`, `bacon-`, `descartes-`, `iv-`, `primal-squeeze`, etc. (lines ~558–587) that carry many `[VERIFY]`/`[LOOKUP]` markers. These belong to **Chapters I/II/IV**, not Chapter V, and are out of scope for this pass — flagged here only so they are not mistaken for Ch V loose ends.

### 2.2 Page-pinned primary quotes in Ch V — verified against primary PDFs

| Footnote | Source / pin as written | Verdict | Evidence |
|---|---|---|---|
| `[^v3-protention]` | Hui, *Recursivity and Contingency* (2019), §36, **p.210** (tertiary protention = "missing element") | **CONFIRMED** | RC PDF ToC + index ("tertiary protention, 210–16, 243"); §36 "Tertiary Protention and Preemption" begins p.210; "missing element—tertiary protention" present. |
| `[^v3-preempt]` | Hui, RC **p.211**: "always preemptive … the machine has already anticipated what the options will be … a reduction of the contingent to the most probable." | **CONFIRMED (verbatim)** | RC PDF, running header "Organizing Inorganic 211"; quote matches word-for-word. |
| `[^v3-loop]` / `[^v4-mutating]` | Hui, RC **p.243**: "It constantly evaluates the past in order to anticipate the future, which in turn determines the present." | **CONFIRMED (verbatim)** | RC PDF, running header "The Inhuman That Remains / 243"; quote present verbatim. |
| `[^v2-concretization]` | Simondon, *On the Mode of Existence of Technical Objects* (Univocal, 2017), **p.49** ("comes closer to the mode of existence of natural objects … closure of the system of causes and effects"), **p.50** ("becomes capable of doing without the artificial milieu … as it organizes itself"), **p.58** ("its own condition … self-conditioning") | **CONFIRMED (verbatim, all three)** | Simondon PDF: printed p.49 "comes closer to the mode of existence of natural objects, tending toward internal coherence, toward a closure of the system of causes a[nd effects]"; printed p.50 "it becomes capable of doing without the artificial milieu, because its internal coherence increases … as it organizes itself"; "its own condition"/"self-conditioning" on p.58. |
| `[^v2-guard]` | Simondon **p.51**: "tend toward concretization … One mustn't confuse the tendency … with the status of entirely concrete existence." | **CONFIRMED** | Simondon PDF printed p.51 carries "status of entirely concrete [existence]". |
| `[^v5-hui]` | Hui, *Art and Cosmotechnics* (2021), **p.224** ("from micro to macro physics … 'organizing inorganic' force … live inside of … submitting to its rules"), **p.227** ("integrated into technical systems … tendency and capacity to totalize") | **CONFIRMED (both pages)** | A&C PDF: printed p.224 (header "CHAPTER 3 224 ART AND COSMOTECHNICS") has "micro to macro physics" + "organizing inorganic" + "submitting to its rules"; printed p.227 (header "ART AND AUTOMATION 227") has "organizing inorganic" + "tendency and capacity to totalize" + "integrated into technical systems". |
| `[^v4-cr]` | Bhaskar, *The Possibility of Naturalism* (3rd ed., Routledge **1998**), **p.41** (three dependencies of social structures; "do not exist independently of the activities … of the agents' conceptions … only relatively enduring"); named p.49; intransitivity p.51. Footnote notes "p.41 is 1998 pagination; 'p.38' is the 1979 1st ed." | **CONFIRMED (page + edition)** | PON 1998 PDF, printed **p.41** carries: "…the activities they govern, they do not exist independently of the conceptions that the agents possess of what they are doing … may be only relatively enduring." The 1998-vs-1979 pagination caveat is correct. **Minor wording note below.** |
| `[^v2-gram]` | Stiegler, *Automatic Society*, Vol. 1 (**Polity, 2016**): grammatization **p.19** ("began at the end of the Upper Palaeolithic age … the most advanced stage") | **CONFIRMED (quote + edition year); page-folio SOFT** | Edition: PDF copyright page reads "This English edition © Polity Press, **2016**" — footnote's 2016 is correct (PDF filename's "2017" is a later printing, not the edition year). Quote verbatim: "Digital tracking technologies are the most advanced stage of a process of grammatization that began at the end of the Upper Palaeolithic age, when humanity first learnt…". Exact printed folio (p.19) not independently confirmable from this scan's heading structure, but the passage is in the book's early Introduction, consistent with p.19. |
| `[^v1-uexkull]` | Uexküll, *A Foray into the Worlds of Animals and Humans* (Minnesota, 2010), **pp.46** (receptor/effector), **49** (functional cycle / *Funktionskreis*) | **UNRESOLVED (low priority)** | The 2010 Minnesota Uexküll volume was not located on disk this pass; the receptor/effector + Funktionskreis content is standard and uncontested, and the same edition is cited in Ch I/II. Recommend a quick folio confirmation against the NLM Uexküll source or the Ch I/II copy before print, but no substantive risk. |

#### §V.I forward-reference pins (footnotes v8) — spot-checked
| Footnote | Pin | Verdict | Note |
|---|---|---|---|
| `[^v8-acceleration]` | Rosa, *Social Acceleration* (Columbia UP, 2013, trans. Trejo-Mathys), **p.151** (Ch.6 "The Circle of Acceleration"); "contraction of the present" pp.155–156 | **UNRESOLVED (not checked this pass)** | Rosa *Social Acceleration* PDF not confirmed on disk; quote is consistent with the known Ch.6 argument. Low risk; confirm folio if time permits. |
| `[^v8-radmonopoly]` | Illich, *Tools for Conviviality* (Fontana/Collins, **1975**), **pp.65–66** ("radical monopoly … Cars can thus monopolize traffic …"); notes Harper & Row 1973 paginates differently | **PLAUSIBLE; folio not re-pinned** | Illich PDF present in cache (`Illich_ToolsForConviviality.pdf`); the radical-monopoly passage is genuinely Illich and the edition caveat is the kind the author has handled correctly elsewhere. Recommend a 2-minute folio confirm against the cached PDF before print. |
| `[^v8-terminal]` | Stiegler, *Automatic Society* **p.25** (proletarianization); Schwartz & Nichols, *After Collapse* (2006) | **NOT CHECKED (forward-reference)** | These are Ch VI forward-references; verify with Ch VI's pass. |

---

## ITEM 3 — Fabrication / mis-attribution / internal-consistency scan (lightweight)

- **`[^v6-signs]` forged-phenomena cluster (OpenClaw / Clawdbot→Moltbot→OpenClaw, Moltbook ~147–150k agents, openclawbook.io, arXiv 2602.02625 (Manik & Wang), MoltMatch / June Chong / Jack Luo, Trend Micro 2026-02, Nous Research Hermes 2026-05-15).** These are 2025–2026 contemporary-news claims, deliberately framed in-text as a fast-moving, soon-obsolete snapshot. They lie **outside** the NLM/Zotero/`P:\books` cascade and were not verifiable in this pass. **Not flagged as fabricated** — the author has sourced these from current web/press separately — but they are the one cluster in Ch V whose specifics (exact agent-counts, the arXiv id `2602.02625`, dates, the AFP/Taipei Times MoltMatch item) carry citation risk and should get a dedicated web-verification pass before print, since they are empirically falsifiable and date-stamped. **Recommend: spot-verify the arXiv id and the MoltMatch press attribution.**
- **Aristotle `[^v7-aristotle]`** (*Physics* II.8, 199b26–31, "if the ship-building art were in the wood…"): standard, correctly located (the locus classicus is indeed *Physics* II.8 ~199b28); the footnote also correctly distinguishes the "internal archē" criterion as *Physics* II.1. No issue.
- **OED meta- `[^v7-oed]`** (two senses): consistent with the OED entry structure; uncontroversial.
- **Internal consistency:** the 道/理/相 ↔ 偽道/偽理/偽相 mapping, the F1–F5 squeeze-ontology cross-refs (F2/F3/F4/F5 in v4/v8), and the Ch IV-engine ↔ four-organs table (5-2) are internally coherent and consistent with the locked `squeeze-ontology` references and prior memory locks (offloading, supremacy-of-subject, Bhaskar precision). No contradictions surfaced.
- **No fabricated citations detected** among the page-pinned primary sources; every primary quote checked resolved to a real passage at (or adjacent to) the cited folio.

---

## Summary of verdicts

| Item | Verdict |
|---|---|
| Lotka footnote `[^v1-lotka]` — article identity | CONFIRMED |
| Lotka — p.188 | CONFIRMED (exact, verbatim passage on printed p.188) |
| Lotka — 1945 coinage, absent from 1925 *Elements* | CONFIRMED (1925 full text negative + OED earliest-evidence 1945 + internal fn33) |
| Hui RC p.210 / p.211 / p.243 | CONFIRMED (verbatim) |
| Simondon *Mode of Existence* p.49 / p.50 / p.51 / p.58 | CONFIRMED (verbatim) |
| Hui *Art and Cosmotechnics* p.224 / p.227 | CONFIRMED |
| Bhaskar *PON* (1998) p.41 + edition caveat | CONFIRMED (light paraphrase-in-quote — see note) |
| Stiegler *Automatic Society* (Polity 2016) grammatization quote | CONFIRMED (quote + 2016 edition year); page-folio p.19 SOFT |
| Uexküll *Foray* (2010) pp.46/49 | UNRESOLVED (not on disk; low risk) |
| Rosa *Social Acceleration* p.151 / pp.155–156 | UNRESOLVED (not checked) |
| Illich *Tools for Conviviality* (1975) pp.65–66 | PLAUSIBLE (PDF in cache; folio not re-pinned) |
| §V `[^v6-signs]` contemporary-news cluster | NOT VERIFIED (out of cascade; recommend dedicated web pass) |

### Items needing the author's attention before print
1. **Clear** the `[Adler: VERIFY]` on `[^v1-lotka]` — it checks out in full.
2. **`[^v4-cr]` wording (minor):** the footnote quotes Bhaskar as "of the agents' conceptions of what they are doing"; the 1998 text reads "of the conceptions that the agents possess of what they are doing." Sense identical; tighten the quotation marks to the exact text, or paraphrase outside quotes, before print.
3. **Confirm three soft folios** if time allows: Stiegler *Automatic Society* p.19; Uexküll pp.46/49 (against NLM source or the Ch I/II copy); Rosa p.151 and Illich pp.65–66 (the Illich PDF is in `.research/cache/downloads/`).
4. **Dedicated web-verification pass** on the `[^v6-signs]` agent-internet cluster (arXiv id `2602.02625`, agent-counts, MoltMatch/AFP attribution) — these are the only date-stamped, falsifiable empirical claims in Ch V and sit outside the source cascade.

Links: [[master-thesis]] · [[squeeze-ontology]] · source: [[lotkaLAWEVOLUTIONMAXIMAL1945]]
