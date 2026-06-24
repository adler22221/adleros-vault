---
type: concept
project: master-thesis
status: ai-draft
summary: "Bibliography entries + reconciliation for thesis print finalization"
---

# Bibliography Compilation & Reconciliation — Print Finalization

> Compiled 2026-06-09. Source: 16 Zotero keys (read-only local API) + web verification for AI-safety additions and the Lamina1 whitepaper.
> Target style: matches the existing References section of `ThesisRevision/revision-draft/20260609 Between the Universe and the Metaverse (working).md` (lines ~770–911).
> **Observed style conventions** (replicated below):
> - Author-date, year in parentheses followed by a period: `Lastname, F. (YEAR). Title. Place: Publisher.`
> - **No markdown italics** in the bibliography (titles are plain text in the .md; the typesetter italicizes book/journal titles at print).
> - Multiple authors joined with `&`; en-dash `–` for page ranges; journal as `Journal, Vol(Issue): pp`.
> - Translators given as `(T. Translator, Trans.)` or noted inline; editions as `(Nth ed.)`.
> - DOIs/URLs appended bare where present in existing entries.
>
> **I do not edit the manuscript.** This note is for the author to paste/reconcile manually.

---

## (1) READY-TO-PASTE BLOCK — all MISSING entries, alphabetized

Paste into the References section in alphabetical position. (All are confirmed against Zotero or web; no invented data. Bracketed notes are for the author, NOT for the final text.)

```
Bostrom, N. (2014). Superintelligence: Paths, Dangers, Strategies. Oxford: Oxford University Press.

Clement, C. R., Denevan, W. M., Heckenberger, M. J., Junqueira, A. B., Neves, E. G., Teixeira, W. G., & Woods, W. I. (2015). The domestication of Amazonia before European conquest. Proceedings of the Royal Society B: Biological Sciences, 282(1812): 20150813.

Descartes, R. (1985). The Philosophical Writings of Descartes, Volume I (J. Cottingham, R. Stoothoff, & D. Murdoch, Trans.). Cambridge: Cambridge University Press.

Deutsch, E. (1969). Advaita Vedānta: A Philosophical Reconstruction. Honolulu: University of Hawaii Press.

Eckhart, M. (2009). The Complete Mystical Works of Meister Eckhart (M. O'C. Walshe, Trans.). New York: Crossroad.

Larson, G. J. (1979). Classical Sāṃkhya: An Interpretation of Its History and Meaning. Delhi: Motilal Banarsidass.

Levis, C., Costa, F. R. C., Bongers, F., Peña-Claros, M., Clement, C. R., Junqueira, A. B., et al. (2017). Persistent effects of pre-Columbian plant domestication on Amazonian forest composition. Science, 355(6328): 925–931.

National Research Council (US) Committee on Genetic Vulnerability of Major Crops. (1972). Genetic Vulnerability of Major Crops. Washington, DC: National Academy of Sciences.

Needham, J. (1969a). The Grand Titration: Science and Society in East and West. London: George Allen & Unwin.

Ord, T. (2020). The Precipice: Existential Risk and the Future of Humanity. New York: Hachette Books.

Russell, S. (2019). Human Compatible: Artificial Intelligence and the Problem of Control. New York: Viking.

Sandel, M. J. (1984). The Procedural Republic and the Unencumbered Self. Political Theory, 12(1): 81–96.

Sandel, M. J. (1998). Liberalism and the Limits of Justice (2nd ed.). Cambridge: Cambridge University Press.

Scheler, M. (2009). The Human Place in the Cosmos (M. S. Frings, Trans.). Evanston, IL: Northwestern University Press.

Schopenhauer, A. (1969). The World as Will and Representation, Vol. 1 (E. F. J. Payne, Trans.). New York: Dover Publications.

Taylor, C. (2007). A Secular Age. Cambridge, MA: Belknap Press of Harvard University Press.

White, L., Jr. (1967). The Historical Roots of Our Ecologic Crisis. Science, 155(3767): 1203–1207.

Wiener, N. (1950). The Human Use of Human Beings: Cybernetics and Society. Boston: Houghton Mifflin.
```

**Buddhist no-self source (key `PZB2KDWD`) — author-decision needed before paste.** The body cites it as `(SN 22.59, in Bodhi, 2000)`, i.e. attributed to "Bodhi". The Zotero record lists Bhikkhu Bodhi only as *translator* (no book author), so a strict author-date head would be by title. To keep the in-text `Bodhi, 2000` working, use a translator-led head:
```
Bodhi, Bhikkhu (Trans.). (2000). The Connected Discourses of the Buddha: A Translation of the Saṃyutta Nikāya. Boston: Wisdom Publications.
```
(Alternative if the author prefers strict APA: `The Connected Discourses of the Buddha: A Translation of the Saṃyutta Nikāya (Bhikkhu Bodhi, Trans.). (2000). Boston: Wisdom Publications.` — but this breaks the `Bodhi, 2000` in-text form. Recommend the translator-led head above.)

---

## (2) STATUS TABLE — every key/source

| # | Zotero key / source | Resolved as | In-text form (body) | References status | Data gaps / flags |
|---|---------------------|-------------|---------------------|-------------------|-------------------|
| 1 | `96A529FF` Scheler | *The Human Place in the Cosmos* (Frings, Trans.), Northwestern UP, **2009** | Scheler, 1928 / "Die Stellung des Menschen im Kosmos, 1928" (line 278) | **MISSING — ADD** | ⚠️ **Date mismatch**: body cites **1928** (original German); Zotero item is the **2009** Frings translation. Body has `[VERIFY printed page — Frings 2009 / Meyerhoff 1961]`. Author must decide which year anchors the entry & in-text cite. Entry above uses 2009 (the edition in Zotero). |
| 2 | `SVHHX9KW` Sandel (book) | *Liberalism and the Limits of Justice* (**2nd ed.**), Cambridge UP, **1998** | Sandel, 1998: 179 (line 278) | **MISSING — ADD** | ✅ Resolves cleanly. **NOTE the "ambiguous log"**: this key is *Liberalism and the Limits of Justice*, NOT *The Case Against Perfection* (a common Sandel confusion). Body's `[VERIFY edition pagination]` flag: p.179 is in the 2nd ed. — author should confirm against the physical 2nd ed. |
| 3 | `CGEJDBT8` Sandel (article) | "The Procedural Republic and the Unencumbered Self", *Political Theory* 12(1): 81–96, **1984** | "first stated in Sandel, 1984: 90" (line 278) | **MISSING — ADD** | ✅ Clean. DOI 10.1177/0090591784012001005 available if the author wants DOIs (existing refs mostly omit DOIs for older articles). |
| 4 | `4SIQBWH8` Descartes | *The Philosophical Writings of Descartes, Volume I* (Cottingham/Stoothoff/Murdoch, Trans.), Cambridge UP, **1985** | Descartes (lines 189, 280-fn, 353, 384, 561) | **MISSING — ADD** | ✅ Clean. (firstName stored as `René` with mojibake in raw API; corrected.) |
| 5 | `GRF9JPRT` White | "The Historical Roots of Our Ecologic Crisis", *Science* 155(3767): 1203–1207, **1967** | White, 1967: 1205, 1206–1207 (line 281) | **MISSING — ADD** | ✅ Clean. Author = "Lynn White Jr." — rendered `White, L., Jr.` |
| 6 | `49FT9G95` Needham | *The Grand Titration: Science and Society in East and West*, George Allen & Unwin, London, **1969** | **Needham, 1969a** (line 300) | **MISSING — ADD** | ✅ Clean. ⚠️ Body uses **1969a** suffix and also cites **Needham, 1969b** = *Within the Four Seas* (line 300) — see Orphans §3. No ISBN in Zotero (1969 ed. predates ISBN; acceptable). |
| 7 | `Z7TA7A4D` Taylor | *A Secular Age*, Belknap/Harvard UP, **2007** | Taylor, 2007 (line 278) | **MISSING — ADD** | ✅ Clean. Body has `[VERIFY page]` — page still to be filled by author. |
| 8 | `PZB2KDWD` Bodhi/Saṃyutta | *The Connected Discourses of the Buddha* (Bhikkhu Bodhi, Trans.), Wisdom Publications, Boston, **2000** | "SN 22.59, in Bodhi, 2000" (line 292) | **MISSING — ADD** | ⚠️ Bodhi is **translator only** in Zotero (no book author). Author-date head needs a decision — see §1 note. |
| 9 | `4I4ZRW63` Larson | *Classical Sāṃkhya: An Interpretation of Its History and Meaning*, Motilal Banarsidass, Delhi, **1979** | Larson, 1979 (line 291) | **MISSING — ADD** | ✅ Clean. No ISBN in Zotero (acceptable). |
| 10 | `ZDVQV7W2` Deutsch | *Advaita Vedānta: A Philosophical Reconstruction*, University of Hawaii Press, Honolulu, **1969** | Deutsch, 1969 (line 291) | **MISSING — ADD** | ✅ Clean. No ISBN in Zotero (acceptable). |
| 11 | `6BFMAMKQ` Walshe/Eckhart | *The Complete Mystical Works of Meister Eckhart* (M. O'C. Walshe, Trans.), Crossroad, New York, **2009** | "Walshe, 2009" (line 293) | **MISSING — ADD** | ⚠️ In-text says **Walshe, 2009** (translator) but Zotero author = **Meister Eckhart**, translator = Walshe. Entry above is headed **Eckhart, M.** for strict APA. **This breaks the in-text `Walshe, 2009`.** Author decision: either (a) change in-text to `(Eckhart, 2009)` / `(Eckhart 2009, trans. Walshe)`, or (b) head the entry `Walshe, M. O'C. (Trans.). (2009). The Complete Mystical Works of Meister Eckhart...` Recommend (a) for consistency with how the thesis heads other translated primary works (Schopenhauer, Descartes by author). **FLAG for author.** |
| 12 | `493B9572` Schopenhauer | *The World as Will and Representation, Vol. 1* (E. F. J. Payne, Trans.), Dover, New York, **1969** | "Schopenhauer, WWR I, §63" (line 293) | **MISSING — ADD** | ⚠️ In-text uses **"WWR I, §63"** (no year). Entry is dated 1969 (Payne/Dover). In-text has no year to match — author may want `(Schopenhauer, 1969: §63)` or keep the `WWR I` siglum and ensure the References entry is findable by name. **Minor flag.** |
| 13 | `5WXX25J7` Levis | "Persistent effects of pre-Columbian plant domestication...", *Science* 355(6328): 925–931, **2017** | "Levis et al., 2017" (line 335) | **MISSING — ADD** | ✅ Clean. Zotero stores 6 named authors + literal `et al.` creator → rendered with `et al.` to match the body's `Levis et al.` and existing house style (cf. Rockström/Steffen entries use `et al.`). |
| 14 | `N22WI2PI` Clement | "The domestication of Amazonia before European conquest", *Proc. R. Soc. B* 282(1812): 20150813, **2015** | "Clement et al., 2015" (line 335) | **MISSING — ADD** | ✅ Clean. 7 named authors — listed in full above (under 8 authors). |
| 15 | `UWDPGDVM` NRC | *Genetic Vulnerability of Major Crops*, report, NRC (US) Committee, Washington DC, **1972** | "National Research Council, 1972" (line 339) | **MISSING — ADD** | ⚠️ **No publisher in Zotero** (report item). Standard publisher for this NRC report is **National Academy of Sciences** (Washington, DC) — supplied above from standard catalog data; author should confirm, or drop the publisher and leave `Washington, DC: National Research Council.` |
| 16 | `VS4DKAX2` Baudrillard | *The Intelligence of Evil or the Lucidity Pact* (C. Turner, Trans.), Berg, Oxford/New York, **2005** | "Baudrillard, [VERIFY citekey] — *The Intelligence of Evil; or, The Lucidity Pact*" (line 184) | **MISSING — ADD** | ⚠️ **This is a SECOND Baudrillard work** — NOT the 1994 *Simulacra and Simulation* already in refs (line 789). Both are cited (1994 at line 183; 2005 at line 184). Year-disambiguation NOT needed (different years). Resolves the `[VERIFY citekey]` flag. **ADD entry below.** |

### Additional MISSING entry (Baudrillard 2005) — for paste block §1:
```
Baudrillard, J. (2005). The Intelligence of Evil or the Lucidity Pact (C. Turner, Trans.). Oxford; New York: Berg.
```
(Place rendered `Oxford; New York` to match house style for dual-city imprints, cf. Stiegler 2016 `Cambridge, UK; Malden, MA`.)

### Task-4 web-verified items (ALREADY in table as ADD where applicable):

| Source | Status | Verified entry |
|--------|--------|----------------|
| **Bostrom "fix"** | ⚠️ See flag below | `Bostrom, N. (2014). Superintelligence: Paths, Dangers, Strategies. Oxford: Oxford University Press.` — **MISSING — ADD** |
| **Wiener** | **MISSING — ADD** | `Wiener, N. (1950). The Human Use of Human Beings: Cybernetics and Society. Boston: Houghton Mifflin.` |
| **Russell** | **MISSING — ADD** | `Russell, S. (2019). Human Compatible: Artificial Intelligence and the Problem of Control. New York: Viking.` |
| **Ord** | **MISSING — ADD** | `Ord, T. (2020). The Precipice: Existential Risk and the Future of Humanity. New York: Hachette Books.` |
| **Lamina1 (2022)** | ✅ **ALREADY PRESENT** (line 845) | `Lamina1. (2022). Lamina1 Whitepaper 1.1. Retrieved from https://www.lamina1.com/docs/Lamina1_Whitepaper_1.1.pdf` — KEEP (citable source confirmed; see §3). |

---

## (3) FLAGGED ISSUES NEEDING AUTHOR DECISION

### A. Bostrom "fix" is actually an ADD, not a correction
- The existing entry `Bostrom, N. (2005). Transhumanist Values. Review of Contemporary Philosophy, 4: 87–101.` (line 797) is **CORRECT and must STAY** — it is cited at lines 404 ("only a half-baked beginning…") and supports the transhumanism discussion.
- The body **separately** cites **Bostrom (2014)** at line 68 ("the reckoning of catastrophic risk in Nick Bostrom (2014)…") and references it again at line 731. That 2014 work is *Superintelligence* — and there is **no 2014 entry in References**. So the requested *Superintelligence* (Oxford UP, 2014) is a **MISSING — ADD**, not a replacement of the 2005 entry.
- **Verified**: *Superintelligence: Paths, Dangers, Strategies*, Oxford University Press, 2014. Original hardcover ISBN 978-0-19-967811-2; place **Oxford** (OUP UK academic imprint). Decision: confirm you want both Bostrom 2005 and Bostrom 2014 in refs (you do — both are cited). No disambiguation suffix needed (different years).

### B. Lamina1 (2022) — KEEP, do not drop
- A citable source **does exist**: the *Lamina1 Whitepaper 1.1* (publicly released Sept 2022, Neal Stephenson's Lamina1 project). It is **already in References** (line 845) and cited in the body at line 35 as `(Lamina1, 2022; Levy, 2022)`.
- **Recommendation: KEEP.** A corporate/project whitepaper with a public URL is a legitimate grey-literature citation. The only caveat: the URL in the entry (`lamina1.com/docs/Lamina1_Whitepaper_1.1.pdf`) should be link-checked before print (whitepaper PDFs migrate; a mirror exists on Scribd, doc id 624239272, as a fallback). Consider adding an access date if the journal style requires one.
- Related entry already present: `Parisi, T., Carter, W., & Bar-Zeev, A. (2023). Metaverse-as-service whitepaper v1.0. Lamina1.` (line 867) — also cited (line 35). No action.

### C. Translator-as-author-head conflicts (Eckhart, Bodhi)
- **Eckhart `6BFMAMKQ`**: in-text `Walshe, 2009` vs. author-date head `Eckhart, M.` — mismatch. Pick one (recommend changing in-text to Eckhart; see table row 11). **Author must edit body OR entry head to agree.**
- **Bodhi `PZB2KDWD`**: in-text `Bodhi, 2000` works only with a translator-led head. Recommended head supplied in §1.

### D. Scheler date (1928 vs 2009)
- Body cites the 1928 original (`Die Stellung des Menschen im Kosmos, 1928`); Zotero holds the 2009 Frings translation. Standard practice: head by translation year used (2009) OR `Scheler, M. (1928/2009)`. Decision needed; the body's German-title parenthetical can stay as descriptive context. Page still unresolved (`[VERIFY printed page]`).

### E. NRC publisher gap
- Zotero `report` item has no publisher. Supplied "National Academy of Sciences" from standard catalog data — **confirm or replace**. Do not invent if uncertain; `Washington, DC: National Research Council.` is an acceptable fallback.

### F. Pages/edition still flagged `[VERIFY]` in body (not resolvable from Zotero metadata alone)
- Taylor 2007 page; Sandel 1998 p.179 edition-pagination; Scheler printed page. These are PDF-lookup tasks the author flagged in-text; Zotero metadata does not carry them. Not invented here.

---

## (4) ORPHANS NOTED IN PASSING (focused scan, not a full reconciliation)

These are cited in the body but I did **not** see a matching References entry while scanning the target passages. The task said a full both-directions reconciliation is a later step — flagging only the obvious ones encountered:

| In-text cite | Where seen | Note |
|--------------|-----------|------|
| **Needham, 1969b** (*Within the Four Seas*) | line 300 | Body references it as a re-anchor target for the Needham hinge; **no `Within the Four Seas` entry exists** in References. If the author adds *The Grand Titration* (1969a), they should decide whether 1969b is also needed, or drop the 1969b mention. The body's parenthetical even says the citation "can be re-anchored if The Grand Titration is not added to Zotero." |
| **Crosby, 1986** (*Ecological Imperialism* / "weed" passage) | lines 335, 338 | "Alfred Crosby… (Crosby, 1986: ch. 7)" — **no Crosby entry** seen in References. Likely a genuine orphan to resolve. |
| **Miura, 2004 / 2006** | lines 285, 338 | Body cites `Miura, 2004: 15–16` and `Miura, 2006: 95–99`. References has the Japanese-language `三浦永光（2006）` entry (line 772) — so 2006 is covered, but **Miura 2004 may be a separate work** with no entry. Flag for author to confirm whether 2004 ≠ 2006. |
| **Watson, 2013** (Zhuangzi trans.) | line 292 | "trans. Watson, 2013" — **no Watson entry** seen. Likely orphan. |
| **Bacon** | lines 280-fn, 189 | Cited via `[^bacon]` footnote ref; could not confirm a Bacon References entry in the scanned range. Flag for author. |

> These five are surfaced opportunistically. A systematic body↔References reconciliation (both directions, all ~99 entries) remains a separate later pass as the task notes.

---

## Provenance
- Zotero: read-only local API (`localhost:23119`, header `X-Zotero-Connector-Api-Version: 2`), 16 keys, all resolved (no 404s).
- Web verification (Task 4): Bostrom *Superintelligence* (OUP 2014, ISBN 978-0-19-967811-2); Wiener (Houghton Mifflin, Boston, 1950, subtitle "Cybernetics and Society"); Russell (Viking, 2019); Ord (Hachette Books, New York, 2020 — UK Bloomsbury/London also exists); Lamina1 Whitepaper 1.1 (Sept 2022, public).
- No page numbers, publishers, or other fields were invented. Gaps are flagged explicitly above.
