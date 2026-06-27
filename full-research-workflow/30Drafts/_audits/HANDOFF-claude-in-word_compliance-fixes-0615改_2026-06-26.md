---
aliases: []
type: draft
project: master-thesis
topic: [audit, claude-in-word, handoff, scu-compliance]
status: ai-draft
target: thesis
source-notes: []
summary: "Claude-for-Word fix handout for 楊逸帆碩士論文_2026-06-15-改.docx — exact FIND→REPLACE / actions for the confirmed compliance residuals (GROUPS 1–10; GROUP 3 retired), the fn67 Hui-citation resolution (de-quoted Q1 + 2024a/2024b split), the completed quotation source-verification pass (GROUP 8), the citation-completeness fixes (GROUP 9), recto + master-format numbering (GROUP 10), and a coverage matrix showing every original-handout task independently re-run. Companion to master-thesis_compliance-audit-0615改_2026-06-26.md."
---

# Fix handout — paste into Claude-in-Word

**Document:** `楊逸帆碩士論文_2026-06-15-改.docx`
**Note:** Track Changes is OFF and edits are already accepted — turn Track Changes back **on** before applying these if you want a redline of *this* round. Most fixes are exact FIND→REPLACE; a few are select-and-format or Word-menu actions. **Do not invent any citation or page number** — the two items that still need a page (fn47 and body[498]) are flagged in GROUP 9 for the author, not to be guessed.

---

## GROUP 1 — Reference list: move 2 entries, italicize 2 titles, add missing Hui source

**1.1 Move the Manik entry up (alphabetical order).**
Cut the entry beginning `Manik, M. M. H., & Wang, G. (2026). OpenClaw agents on Moltbook…` (currently sits after `Mignolo, W. D.`) and paste it **after `Lyons, T. W.` and before `Matthews, B.`**

**1.2 Move the Watson/Wilson entry to the J block.**
Cut the entry beginning `James Watson and Edward O. Wilson: An intellectual entente. (2009, September 10). Harvard Magazine…` (currently between `Wiener, N.` and `World, n.`) and paste it **after `Illich, I. (1975)…` and before `Kant, I.`** (it's a no-author work, alphabetized by "James").

**1.3 Italicize the Kant title.** In the entry `Kant, I. (1790/2000). Critique of the Power of Judgment (P. Guyer…)`, select **`Critique of the Power of Judgment`** and apply *italic* (leave the rest roman).

**1.4 Italicize the Manik arXiv title.** In the Manik entry, select **`OpenClaw agents on Moltbook: Risky instruction sharing and norm enforcement in an agent-only social network`** and apply *italic* (stop before `. arXiv:`).

**1.5 Add the missing Hui source + disambiguate the two 2024 works.** fn67 quotes Hui's essay "Machine and Ecology," which is **not in the reference list**. Add it; and because the list already has a Hui 2024 (*Machine and Sovereignty*), both 2024 works need a/b letters (alphabetical by title: **E**cology < **S**overeignty):
- **ADD** (place after the Hui 2021 entry): `Hui, Y. (2024a). Machine and Ecology. In Y. Hui (Ed.), Cybernetics for the 21st Century, Vol. 1: Epistemological Reconstruction (pp. 43–66). Hong Kong: Hanart Press.`
- **RELABEL** the existing entry → `Hui, Y. (2024b). Machine and Sovereignty: For a Planetary Thinking. Minneapolis: University of Minnesota Press.`
- **UPDATE existing in-text cites** of *Machine and Sovereignty* — "Hui's monotechnology (2024…" and "Hui's (2024…" — to **(2024b)**. (The new fn67 cites use **2024a**.)

*(The other new reference entries — Ritz, Douven, 総合人間学会, Qianlong Emperor — are listed together in GROUP 9b.)*

**1.6 Add original/edition slashes (verified original-language dates).** Your reference list already slashes some translated classics (Bacon 1620/1863, Adorno *Negative Dialectics* 1966/1973, Kant 1790/2000) but not 17 others. Each year below was verified against the book's own copyright page and/or two independent sources (adversarially cross-checked). **Change only the reference-list date to the slash form; in-text cites stay at the edition year — unchanged.**

| Entry (current date) | Replace date → |
|---|---|
| Adorno, *The Idea of Natural-History* (1984) | **1932/1984** |
| Baudrillard, *The Intelligence of Evil* (2005) | **2004/2005** |
| Descola, *Beyond Nature and Culture* (2013) | **2005/2013** |
| Habermas, *TCA* Vol 1 (1984) | **1981/1984** |
| Habermas, *TCA* Vol 2 (1987) | **1981/1987** |
| Horkheimer & Adorno, *Dialectic of Enlightenment* (2002) | **1947/2002** |
| Liu, *The Three-Body Problem* (2014) | **2008/2014** |
| Portmann, *A Zoologist Looks at Humankind* (1990) | **1944/1990** |
| Rosa, *Social Acceleration* (2013) | **2005/2013** |
| Schopenhauer, *WWR* Vol 1 (1969) | **1818/1969** |
| Stiegler, *Technics and Time, 1* (1998) | **1994/1998** |
| Stiegler, *Automatic Society, 1* (2016) | **2015/2016** |
| Weber, *Science as a Vocation* (1946) | **1919/1946** — and delete the now-redundant "(1919)" after the title |

**Leave edition-only (no single original date — collection or ancient canon):** Descartes, *Philosophical Writings I* (multi-work omnibus, 1619–1649) · Eckhart, *Complete Mystical Works* (medieval sermons/treatises) · Bodhi, *Connected Discourses* (ancient Pali Saṃyutta Nikāya) · Stiegler, *The Neganthropocene* (a 2018 assembly of 13 lectures/texts from 2012–2017, never a prior single book).

*Two to confirm: Schopenhauer's title page prints **1819** though scholarly convention dates it **1818** — pick one. Horkheimer & Adorno's 1944 was a privately-circulated mimeograph, so **1947** (first published Querido edition) is recommended — use 1944/2002 only if you mean to date the drafting.*

**1.7 Split a merged reference entry.** Two entries run together with no paragraph break: `…(E. Jephcott, Trans.). Stanford, CA: Stanford University Press.Houston, S., & Stuart, D. (1998). The Ancient…` — insert a paragraph break **before `Houston, S., & Stuart, D.`** so they read as two separate entries.

---

## GROUP 2 — Footnotes: normalize page references to SCU colon form

**2.1** FIND `(Bhaskar, 2008, p. 46)` → REPLACE `(Bhaskar, 2008: 46)`  *(fn3)*

**2.2** *(fn64)* It already opens "Bhaskar (1998):". Rewrite the bare page refs to colon form, e.g.:
FIND `enumerated p.41` → `enumerated at (1998: 41)`; FIND `named p.49` → `named at (1998: 49)`; FIND `discussed p.51` → `discussed at (1998: 51)`. *(adjust wording to read naturally)*

**2.3** *(fn54)* Replace the full Chicago note
`Lotka, "The Law of Evolution as a Maximal Principle," Human Biology 17, no. 3 (1945): 167–194, at 188.`
→ `Lotka (1945: 188).`
*(The Lotka 1945 entry is already in the reference list. If the surrounding sentence still cites Lotka 1925, add a 1925 reference entry — otherwise no.)*

---

## GROUP 3 — RETIRED (superseded by GROUP 9)

This group originally expanded the abbreviation "SEP" at its first use (fn4). **GROUP 9** instead rewrites fn4's citation to author-date — `(Douven, 2021; Ritz, 2020)` — which removes "SEP" from the document **entirely** (it appeared only in fn4). With no "SEP" abbreviation left, there is nothing to define, so this group is intentionally empty. (The §4.3 "IoT" half was already compliant — full form precedes the abbreviation.)

---

## GROUP 4 — Cleanliness (text)

**4.1 Doubled spaces → single** (collapse the double space in each):
`Stiegler  calls` → `Stiegler calls` · `1995)  reaches` → `1995) reaches` · `of  secreting` → `of secreting` · `possibilities  —` → `possibilities —` · *(fn)* `58):  "` → `58): "`
**Do NOT change** `World   世界` (intentional table-cell alignment).

**4.2 Space before punctuation → remove the space:**
`soul ; and` → `soul; and` · `the last . But` → `the last. But` · `substrate ; for` → `substrate; for` · `flesh . Here` → `flesh. Here`
**Do NOT touch** `.docx` or `!Kung` (legitimate).

**4.3 Straight → curly** in fn12 (the Polanyi footnote) and one body Heading3:
`"Life's Irreducible Structure"` → `“Life’s Irreducible Structure”` · `"dual control,"` → `“dual control,”` · apostrophes in `Polanyi's / Life's / argument's` → `’` · body `one's “true endowed nature”` → `one’s …`

**4.4 Table 4-1 header.** Select the header cell text **`Period`** in Table 4-1 (it's set to 1pt → invisible) and set font size to **12pt** to match the other header cells.

---

## GROUP 5 — Deposit-readiness (Word menus, not text)

**5.1 Document properties.** File ▸ Info ▸ Properties: set **Title** = the thesis title, and **Keywords** = the five abstract keywords (`metaverse, adaptational squeeze, artificiality, critical realism, philosophy of technology` / 偽境、趨壓、人工性、批判實在論、技術哲學). Both `dc:title` and `cp:keywords` are currently empty.

**5.2 Fonts / portability.** DFKai-SB and PMingLiU are Windows-only. For deposit, **export to PDF** (PDF embeds the glyph outlines, so CJK survives on any machine). If a `.docx` must also be submitted, turn on File ▸ Options ▸ Save ▸ *Embed fonts in the file*.

**5.3** *(optional)* Remove the leftover **Grammarly** custom document property.

---

## GROUP 6 — Comments (do LAST, after GROUP 7)

**6.1** Once fn67's citation is resolved (**GROUP 7** + the GROUP 1.5 / GROUP 9b reference adds), **delete all 4 Word comments** (Review ▸ Delete ▸ Delete All Comments in Document). They're authoring TODOs dated today and must not ship to the committee/library.

---

## GROUP 7 — fn67 citations: RESOLVED (verified verbatim against the source PDFs in P:\books)

All six fn67 quotes were checked against Hui's own texts. Five are verbatim; one (Q1) is a paraphrase wearing quote marks.

| fn67 quote | Verdict | Source + page |
|---|---|---|
| "largely determines the relation between human and non-human beings, human and cosmos, and nature and culture" | ⚠️ **NOT verbatim** in any Hui work — paraphrase in quotes | no single passage matches (closest: A&C 2021 ≈p.190, different wording) |
| "the planetarization … invasion of technology into all beings, rendering them standing reserves" | ✅ verbatim | **Hui, 2019: 233–234** (*Recursivity and Contingency*) |
| "the hybridism between the natural environment and machines constitutes a gigantic system … nature ended and ecology began" + ecology "a concept of cybernetics" | ✅ verbatim | **Hui, 2024a: 49** ("Machine and Ecology") |
| livestock: "intervene **in** the environment by controlling its fertility and sterility … modulate the **behaviour** of the livestock on a large scale" | ✅ verbatim (fn67 slips: "intervene **into**"→"in"; "behavior"→"behaviour") | **Hui, 2024a: 54** |
| "a second nature that envelops the earth" | ✅ verbatim | **Hui, 2019: 186** |

**Suggested fn67 rewrite** — de-quotes the unverifiable Q1, fixes the two spelling slips, inserts the cites (requires the GROUP 1.5 reference additions first):
> …is grounded directly in Hui. Modern technology, on Hui's account, reorganizes the relations between human and non-human, human and cosmos, and nature and culture: "the planetarization … means the invasion of technology into all beings, rendering them standing reserves" (Hui, 2019: 233–234); "the hybridism between the natural environment and machines constitutes a gigantic system … nature ended and ecology began," ecology now "a concept of cybernetics" (Hui, 2024a: 49); and, in the livestock case, "human beings intervene in the environment by controlling its fertility and sterility … to modulate the behaviour of the livestock on a large scale" (Hui, 2024a: 54), giving "a second nature that envelops the earth" (Hui, 2019: 186). …

After inserting this, the four Word comments can be deleted (**GROUP 6**).

> **Q1 decision: DE-QUOTE** (Adler, 2026-06-26). The rewrite above already renders Q1 as paraphrase — no quotation marks — and attributes the idea to Hui generally. (No verbatim Hui source exists for that sentence; checked R&C 2019, QCTC 2016, A&C 2021, Machine & Sovereignty 2024, Cybernetics 2024, Digital Objects 2016.)

---

## GROUP 8 — Quotation source-verification pass (the owed §3.7 / §4.4 [VERIFY] task — now COMPLETE)

The original handout left "a full pass over all footnote and body quotations that cannot be source-verified" owed (only the Hui footnote was flagged). I ran it independently: extracted **every** multi-word quotation in the manuscript (49 in footnotes, 155 in body), checked each for a citation, and read the full context of the 52 that lacked an adjacent one. Almost all are the thesis's own coined terms/definitions, classical quotes attributed in surrounding prose, proverbs, or quotes cited in the **anchoring footnote**. The genuine gaps (the exact in-text edits are in **GROUP 9a**):

| # | Quote (location) | Resolution |
|---|---|---|
| V1 | body[427] "refraining from activity contrary to Nature" (Needham, no page) | ✅ **VERIFIED → (Needham & Wang, 1956: 69)** — the phrase is on p. 69, in the §10 wu wei discussion that opens p. 68. |
| V2 | body[705] Hui "constantly evaluates the past in order to anticipate the future" (no page) | ✅ **VERIFIED → (Hui, 2019: 243)**. |
| V3 | fn8 "what does it mean to be human?" + "have their roots in the self-alienation of the human being" | ✅ **RESOLVED** → source = the JASA 2006 founding statement (synthetic-anthropology.org) → cite (総合人間学会, 2006); entry in **GROUP 9b**. |
| V4 | fn47 "the limitless actualization of an imagined ideal upon reality" (Uegaki gloss) | ✅ **RESOLVED → (上柿崇英, 2022a: 29)** — the 無限の生 worldview is defined there (matching phrasing also in the はじめに, p. xii). |
| V5 | body[413] "Our Celestial Empire possesses all things in prolific abundance…" (1793 Qianlong edict) | ✅ **RESOLVED** → **NOT in Crossley** (checked his PDF). It's the **Backhouse & Bland (1914)** translation → cite + add entry (**GROUP 9b**). |
| V6 | body[422] "continues to expand itself by the logic of society alone, ignoring any consistency with nature" (Uegaki) | ✅ **RESOLVED → (上柿崇英, 2022a: 16)** — where Uegaki names the 社会↔自然 severance; **no "my translation" tag** (GROUP 9c). |
| V7 | body[497]/[498] "propitious for the natural sciences, yet non-experimental" / "the more complete… domination of nature" | ✅ **RESOLVED → de-quote both.** body[497] is not verbatim in any Needham work. body[498] **is at SCC Vol 7-2 (2004): 75** — but there Needham is *summarizing the 1970s counterculture's attack on science* (Roszak/Pirsig/Weisskopf), i.e. the critique of the dominating register, **not** his characterization of it, so it inverts your point. De-quote and cite the **Grand Titration** `(Needham, 1969a)` for the real observational-vs-experimental contrast → GROUP 9a. |

*Optional page-pins (already attributed, not gaps):* fn48 Uegaki quote (cited in fn48); fn24 / body[278] Obara quotes (小原秀雄, 2000).

**Cleared — checked, no action (representative):** fn36 Bacon (fully cited, 1863: I, aph. 3/98/closing); body[700] Stiegler/Simondon (cited in fn55–58; "grammatization began at the end of the Upper Palaeolithic" verified in *Automatic Society* p.19/29 → `Stiegler (2016: 19, 29)`); body[745] OpenClaw quotes (cited in fn71: Trend Micro 2026, Manik & Wang 2026); body[311] Peirce (1902); fn75 / body[749] Aristotle (Physics II.8, 199b26–31); body[181] "chains we are born into" (Rousseau allusion); body[491] "heaven is high, the emperor far away" (proverb); body[161/166/299/345/356/358/525/748/755/760/762] + fn22/76 (the thesis's own coined terms / definitions / glosses).

---

## GROUP 9 — Citation completeness (fn4 / fn8 / fn12 + the resolved [VERIFY] items)

Per **APA 7**, every work cited in-text — *including in a footnote* — must have a reference-list entry; footnoting is not a substitute. Below are the in-text fixes and the new reference entries (all source-verified, 2026-06-27).

### 9a — In-text citation fixes
- **fn4** — replace `(SEP, "Abduction"; "Scientific Realism"; Ritz, 2020)` → **`(Douven, 2021; Ritz, 2020)`**. Ritz (2020) is the on-point source for the abduction-vs-retroduction distinction; the SEP "Abduction" entry (Douven) covers the quoted "best of a bad lot" and the IBE characterization. **Drop "Scientific Realism" (Chakravartty)** — it does no specific work in fn4. (Still removes "SEP," so §4.3 / GROUP 3 stay closed.)
- **fn8** — after `"…self-alienation of the human being."` add **`(総合人間学会, 2006)`**.
- **fn12 (Polanyi)** — at `Polanyi's instances in "Life's Irreducible Structure"` add **`(Polanyi, 1968)`**; at `the stronger reading sometimes drawn from "dual control,"` add **`(Polanyi, 1968: 1308)`** *(verified, p. 1308 of the 1968* Science *paper)*.
- **body[427] (wu wei)** — after `"refraining from activity contrary to Nature"` add **`(Needham & Wang, 1956: 69)`** *(verified: the phrase is on p. 69; the §10 wu wei discussion opens p. 68)*.
- **body[705] (Hui)** — after `"constantly evaluates the past in order to anticipate the future"` add **`(Hui, 2019: 243)`** (or place it in fn61).
- **body[497] & body[498] (Needham) — de-quote both.** body[497]'s "propitious… non-experimental" is **not verbatim** in any Needham work. body[498]'s "the more complete… domination of nature" **is at SCC Vol 7-2 (2004): 75** — but there Needham is **summarizing the 1970s counterculture's *attack* on science** (Roszak, Pirsig, Weisskopf: "*They attack… 'the more complete the domination of nature, the more fully does it become possible for ruling elites to increase their power'*"), i.e. the *critique* of the dominating register, **not** Needham's characterization of it — so quoting it for your interventionist-science point inverts its sense. Render both as your paraphrase of Needham's observational-vs-experimental thesis, cited to the **Grand Titration** → `(Needham, 1969a)` (the actual source of that "Needham Question" contrast). *(If you still want a quotation, present it as the counterculture critique Needham relays, `Needham, Elvin, & Huang, 2004: 75`.)*
- **body[422] (Uegaki)** — after `"…ignoring any consistency with nature."` add **`(上柿崇英, 2022a: 16)`** *(verified: p. 16, where Uegaki names the second singularity 「<社会>と<自然>の切断」 — society "lacking 'consistency' with the natural ecosystem… expands infinitely")*. **No "(my translation)" tag** (see 9c).
- **body[413] (Qianlong)** — paragraph revision + citation in **9d**.
- **fn47 (Uegaki)** — add **`(上柿崇英, 2022a: 29)`** to the `"the limitless actualization of an imagined ideal upon reality"` gloss *(the 無限の生 worldview is defined there in the body; the exact "control reality to match the ideal / pursue it limitlessly" wording your gloss renders also sits in the はじめに, p. xii — confirm which your footnote draws on)*.

> **V4 & V6 are resolved against your 2022a（上）** — the book is in Zotero (item CYAAA3IK, 2022-03-30) under the draft-named attachment `uegaki2021A.pdf`, and in P:\books as `〈自己完結社会〉の成立（上）.pdf`. (Earlier "I don't hold it" was wrong — I had only filename-matched on the year.)

### 9b — New reference-list entries to ADD (match your edition-only house style; alphabetize into place)
- `Ritz, B. (2020). Comparing abduction and retroduction in Peircean pragmatism and critical realism. Journal of Critical Realism, 19, 5: 456–465.`
- `Douven, I. (2021). Abduction. In E. N. Zalta (Ed.), The Stanford Encyclopedia of Philosophy (Summer 2021 ed.). Stanford University. https://plato.stanford.edu/archives/sum2021/entries/abduction/` *(fn4 — covers "best of a bad lot" + IBE)*
- `総合人間学会 (2006)。〈本学会について（設立趣旨）〉。（2026年6月27日アクセス）http://synthetic-anthropology.org/?page_id=2`
- `Qianlong Emperor (1793/1977). Two Edicts from the Qianlong Emperor, on the Occasion of Lord Macartney's Mission to China, September 1793 (E. Backhouse & J. O. P. Bland, Trans.). In J. M. Gentzler (Ed.), Changing China: Readings in the History of China from the Opium War to the Present. New York: Praeger.` — *original/edition slash, matching Bacon (1620/1863) etc.; Backhouse-Bland = the 1914 translation reproduced by Gentzler; accessed via Asia for Educators, Columbia: https://afe.easia.columbia.edu/ps/china/qianlong_edicts.pdf*

**In-text → `(Qianlong Emperor, 1977)`** — treated exactly like your other translated works: **slash in the reference (1793/1977), edition year in-text** (as Bacon 1620/1863 → 1863). *(Strict APA would put the dual `1793/1977` in-text; your consistent house style is edition-only in-text, so 1977.)*

### 9c — "My translation" labelling (APA)
APA 7 does **not** require "[my translation]" on every quotation. It explicitly permits a **single note** stating that you translated all the passages. Cleanest: one footnote at the **first** Uegaki/Obara quotation — *"Unless otherwise noted, all translations from the Japanese are my own."* — then **drop the per-instance "(my translation)" tags** (e.g. in body[423]) for consistency. Keep a per-instance tag only where you mix your own translation with a published one in the same place. *(SCU follows the* 東吳哲學學報 *rules with APA as fallback; the blanket note is APA-compliant — confirm the* 學報 *has no stricter requirement.)*

### 9d — body[413] paragraph revision (Qianlong — block-quoted edict, thesis style)
Replace the whole body[413] paragraph with a **lead-in → block quote → analysis** (the block quote is set as your `Block Text` style; its citation goes *after* the closing period, as in your Heraclitus and Liu Cixin block quotes):

Lead-in (normal paragraph, ending with a colon):
> Qianlong's reply to the Macartney mission — read today as arrogance, and not wrongly — is, read through the present frame, the record of two adaptational operating systems whose logics will not translate into one another:

Block quote (Block Text style):
> Supposing that your Envoy should come to our court, his language and national dress differ from that of our people, and there would be no place in which he might reside … it has never been our dynasty's wish to force people to do things unseemly and inconvenient … Europe consists of many other nations besides your own: if each and all demanded to be represented at our Court, how could we possibly consent? … our ceremonies and code of laws differ so completely from your own that, even if your Envoy were able to acquire the rudiments of our civilization, you could not possibly transplant our manners and customs to your alien soil … As your Ambassador can see for himself, we possess all things. I set no value on objects strange or ingenious, and have no use for your country's manufactures. (Qianlong Emperor, 1977)

Analysis (normal paragraph):
> Two things are at work here, and neither is mere hauteur. The first is mutual incommensurability: each order — its language and dress, its ceremonies and laws — is intelligible and inhabitable only from within, so that what one would transplant into the other has no soil in which to take root. The second is self-sufficiency: a system that "possesses all things" meets external solicitation as interference rather than exchange, for it has already reached its own homeostasis among its members, its institutions, and the local universe that forms its background environment — the signature of an AOS closed upon itself. The arrogance the edict also carries is real, but it is better read as the inertia of a dynastic tradition: a reflection of how the Qing AOS operated rather than the heart of what the case shows, which is two worlds each complete in its own terms, neither commensurable with nor reducible to the other. Such closure is not peculiar to the Qing; it is not uncommon among other civilizations, or even tribal societies (though this is not to make a normative judgment about it).

*Notes: (1) in-text `(Qianlong Emperor, 1977)` keys to the 9b entry (slash in the reference, edition year in-text — same as Bacon). (2) I folded the old "kowtow / tribute-vs-trade" thread into the incommensurability framing — re-add a sentence if you want it explicit. (3) the closing "not uncommon among other civilizations… tribal societies" line is carried from your original.*

---

## GROUP 10 — Recto chapter starts + master-format numbering (MANDATORY)

**Chapters I, II, III, IV, V, VI, Conclusion, and References already start on a recto (odd) page** — each sits at the head of an `oddPage` section. **Only the Introduction does not**: it shares one section with the **List of Tables**, and that section's recto/oddPage start lands on the List of Tables rather than on the Introduction. That same section also carries the arabic "start at 1," so the List of Tables currently prints as **arabic p.1** — whereas master-format wants **roman** for 目錄/表目錄 and **arabic beginning at 緒論** (the Introduction).

So there is **one fix**, and it resolves both problems at once: split the List-of-Tables / Introduction section. **Do NOT change Chapters I–VI, Conclusion, or References** — they are already correct, and a "Section start" change made with **Apply to: Whole document** would wrongly cascade to every section (including the landscape tables).

**Mechanism:** a Word **"Odd Page" *section break*** forces the new section onto the next odd page, **inserting a blank verso page** when needed — physically pushing the Introduction onto the recto leaf (the Word equivalent of LaTeX `\cleardoublepage`). The odd *number* is the result, not a hand-set value.

### The fix — split the List-of-Tables / Introduction section (one operation, both problems)
- **a.** If a manual **page break** sits just before the **Introduction** heading, delete it (you'll replace it with a section break).
- **b.** Cursor **at the very start of the "Introduction" heading** → **Layout ▸ Breaks ▸ Section Breaks ▸ Odd Page**. *(List of Tables now ends one section; the Introduction starts a new section on a recto page.)*
- **c.** Click in the **List of Tables** → **Insert ▸ Page Number ▸ Format Page Numbers…** → **Number format = i, ii, iii…**, select **"Continue from previous section"** ▸ OK. *(Roman, continuing the count from the Contents.)*
- **d.** Click in the **Introduction** → **Format Page Numbers…** → **Number format = 1, 2, 3…**, **"Start at: 1"** ▸ OK. *(The single intended restart — master-format arabic-from-緒論.)*
- **e.** Click in **Chapter I** → **Format Page Numbers…** → confirm **"Continue from previous section"** (NOT "Start at 1"), arabic. *(Ch I follows the Introduction's count.)*

> ⚠️ "Continue from previous section" everywhere **except** step (d). Never tick "Apply to: Whole document" for Section start. Leave footnotes at **Numbering: Continuous** (References ▸ Footnotes launcher ↘) — already set; just don't let it flip to "Restart each section."

### Verify
- **Layout ▸ Margins ▸ Mirrored** (so odd = recto when bound duplex), if not already.
- **View ▸ Two Pages:** every chapter title — Introduction, I, II, III, IV, V, VI, Conclusion, References — on a **right-hand (recto)** page.
- Footer sequence: front matter incl. **List of Tables = roman**; **Introduction = arabic 1**; arabic **unbroken** to the end of References, no chapter restarting at 1.
- Footnotes still **1 … 81**, no restart.

*(Aside: the title-page block has three roman "start at 1" restarts — almost certainly harmless, suppressed footers. Leave them unless you want the full front-matter sequence audited.)*

---

## Coverage — every original-handout task was independently re-run

| Original handout task | Independent result |
|---|---|
| §3.1 TOC (1–2) / List-of-Tables indents / odd-page breaks / footnote renumber / block-quote punctuation | TOC ✓ · List-of-Tables ✓ · footnote numbering ✓ · block-quote ✓ · **recto: 8/9 chapters already start recto** (corrected); only the Introduction needs the split → GROUP 10 |
| §3.2 Fonts (DFKai-SB CJK; East-Asian-slot fix) | ✓ CJK all DFKai-SB; **0 accented-Latin mis-pinned** (fix effectively complete; 199 ASCII hint=eastAsia benign) |
| §3.3 Narrative `(year)` reductions / page-inside-parens | ✓ 0 non-compliant `(year): page` |
| §3.4 Chicago→SCU footnote conversions | ✓ done — **but prior session MISSED fn3 / fn54 / fn64** → GROUP 2 |
| §3.5 Footnote intelligibility/redundancy sweep | ✓ no footnote restates its paragraph |
| §3.6 Reference additions/corrections | ✓ additions present — **but Wilson mis-placed, Manik mis-placed, Kant italic missing** → GROUP 1 |
| §3.7 / §4.4 [VERIFY] quotation pass | **✅ completed → GROUP 8** (resolutions actioned in GROUP 9) |
| §4.1 Wilson alphabetization | ❌ still in W → GROUP 1.2 |
| §4.2 English quote over-stripping | ✓ English quotes intact; 3 "Chinese-quoted" tokens are legitimate |
| §4.3 SEP / IoT first use | SEP → **resolved by GROUP 9** (fn4 author-date removes the abbreviation; GROUP 3 retired) · IoT ✓ |
| §4.5 Bracketed placeholders | ✓ none |
| §4.6 Accept-all-clean | moot (already accepted; no redlines) |
| + completeness-critic finds (not in original handout) | empty doc title/keywords, CJK fonts not embedded, 4 embedded comments, Table 4-1 1pt header → GROUPS 5–6 |
| + citation completeness (not in original handout) | fn4 SEP/Ritz, fn8 JASA, fn12 Polanyi need entries/cites → GROUP 9 |
