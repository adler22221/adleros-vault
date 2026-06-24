---
type: concept
project: master-thesis
status: ai-draft
summary: "Self-contained fix-list for the Claude for Word add-in to apply to 楊逸帆碩士論文_2026-06-14.docx as tracked changes. Each item has an exact FIND → REPLACE plus rationale. Derived from the source-grounded citation audit (master-thesis_citation-audit-0614_2026-06-15.md)."
---

# Handoff brief — citation fixes for Claude in Word

**Target document:** `楊逸帆碩士論文_2026-06-14.docx`
**How to apply:** Turn on **Track Changes**. Apply Sections A–C as tracked edits using the exact FIND → REPLACE strings below (each FIND is unique in the document). For Section D, **do not edit** — leave a Word **comment** at the spot instead, because it needs an author decision. Every fix was verified against the actual cited source; rationale is given so you can put it in the tracked-change comment.

---

## A. Body-text fixes (apply as tracked changes)

### A1 — ¶ beginning "Obara's zoology studies on gorilla's chest-drumming" — wrong book (two cites)
The gorilla chest-drumming AND the crane/ibex courtship passages are both in Obara's **solo** book 『だから儀式はなくならない』(1988), not the Obara–Hani 『ペット化する現代人』(1995). The 1988 book is already in the reference list. Two replacements in this paragraph:

1. FIND: `(小原秀雄 & 羽仁進, 1995: 17–19)`
   REPLACE: `(小原秀雄, 1988: 17–19)`
2. FIND: `(小原秀雄 & 羽仁進, 1995: 22–26)`
   REPLACE: `(小原秀雄, 1988: 21–24)`

*Why:* Verified in the source — gorilla drumming = 1988 pp.17–19; crane = 1988 pp.21–22, ibex = 1988 pp.23–24. The 1995 book's pp.17–26 is a Hani dialogue (cheetahs, wildebeest, ants, tool-use) with no gorilla/crane/ibex.

### A2 — Date format: edition-year only (house style) — six in-text cites
**House style = edition year only in-text; no original date before a slash.** Fix every in-text cite that shows an "originalyear/editionyear" (or "[originalyear] editionyear") form. **Leave the reference-list entries as they are** (they keep orig/edition slashes — see D3). The six instances:

a) ¶ "…nature turns into an irresistible parable of imprisonment" (this also restores the year missing in the original audit finding):
   FIND: `(Adorno, Negative Dialectics: 354–361)`
   REPLACE: `(Adorno, 1973: 354–361)`

b) Footnote containing "total mediation, Negative Dialectics":
   FIND: `Negative Dialectics (1966/1973: 357)`
   REPLACE: `Negative Dialectics (1973: 357)`

c) ¶ "an extensional AOS is also an Umwelt" — covers both Uexküll cites in that paragraph:
   FIND: `Uexküll, 1934/2010`
   REPLACE: `Uexküll, 2010`

d) ¶ containing "is nothing else but our own, human Umwelt":
   FIND: `(1934/2010: 53)`
   REPLACE: `(2010: 53)`

e) Footnote containing "Brentano, Psychology from an Empirical Standpoint":
   FIND: `Psychology from an Empirical Standpoint [1874] 1973: 88`
   REPLACE: `Psychology from an Empirical Standpoint 1973: 88`

*Why:* Edition-only is the house style; these are the only in-text cites that break it (Adorno ×2, Uexküll ×3, Brentano ×1). Quoted content and pages are all correct — date format only. (The Adorno P495 one also fixes its missing-year/title-form issue from the audit.)

### A3 — ¶ "That the European escape from the agrarian constraint" — paraphrase error
FIND: `consumed about as much cloth per capita`
REPLACE: `produced about as much cloth per capita`

*Why:* Pomeranz (*The Great Divergence*) says the Lower Yangzi **produced** about as much cloth per capita in 1750 as Britons in 1800 — not "consumed."

### A4 — ¶ "By the Enlightenment mode I mean" — quotation includes words not in the source
FIND: `installing them as masters of a disenchanted world” (Horkheimer and Adorno, 2002: 1)`
REPLACE: `installing them as masters” of a disenchanted world (Horkheimer and Adorno, 2002: 1)`

*Why:* The source sentence ends at "installing them as masters." The phrase "of a disenchanted world" is the thesis's gloss (the source's next, separate sentence is "Enlightenment's program was the disenchantment of the world"). Move the closing quotation mark to after "masters."

### A5 — ¶ "From this principle, Adorno and Horkheimer trace three movements" — quote word order
FIND: `to dominate both it and human beings wholly`
REPLACE: `to dominate wholly both it and human beings`

*Why:* The source reads "dominate **wholly** both it and human beings" (*Dialectic of Enlightenment* p.2); the same quote is rendered correctly earlier in the manuscript.

---

## B. Footnote fixes (apply as tracked changes)

### B1 — Footnote with the German Scheler quote — wrong first word
FIND: `Ein solches Wesen ist also nicht mehr trieb- und umweltgebunden`
REPLACE: `Ein geistiges Wesen ist also nicht mehr trieb- und umweltgebunden`

*Why:* Scheler's original is "Ein **geistiges** Wesen…" ("a spiritual being"). "solches" was carried over from the quote's later sentence "Ein solches Wesen hat 'Welt'" — which is correct and must stay unchanged. **Only the first "solches" → "geistiges".**

### B2 — Footnote listing animal-cognition studies (Howard, Boysen, Agrillo, Nieder) — article title (optional)
FIND: `Large number discrimination by fish`
REPLACE: `Large number discrimination by mosquitofish`

*Why:* The real article title is "Large number discrimination by mosquitofish" (Agrillo, Piffer & Bisazza, *PLoS ONE* 2010, 5(12):e15232).

---

## C. Reference-list addition

### C1 — Add the Adorno *Telos* essay (cited in a footnote, missing from the bibliography)
Insert into the References, in the Adorno block (after "Adorno, T. W. (1966/1973). Negative Dialectics…"):

`Adorno, T. W. (1984). The Idea of Natural-History (R. Hullot-Kentor, Trans.). Telos, 60: 111–124.`

*Why:* A footnote cites "Adorno, 'The Idea of Natural-History,' Telos 60 (1984: 124)" but there is no matching reference entry. Page span **111–124 confirmed** (Telos Press + PhilPapers; Hullot-Kentor's introduction precedes the essay at 97–110). Format = house "Journal, Number: pages" (Telos has no separate volume; "60" is the issue number — so `Telos, 60: 111–124`, not `Telos, 1984, 60`, which would repeat the year already in the date).

---

## D. Needs author decision — leave a COMMENT, do not auto-edit

### D1 — Bhaskar "2008a" / "2008b" labels (two footnotes)
The reference list has only an unlettered **Bhaskar (2008)** = *A Realist Theory of Science*, plus **Bhaskar (1993)** = *Dialectic: The Pulse of Freedom* and **Bhaskar (2009)** = *Scientific Realism…*. But two footnotes cite "Bhaskar, 2008a" and "Bhaskar, 2008b", which have no reference entry. Recommended resolution (author to confirm):
- "(Bhaskar, 2008b: 5)" and "(Bhaskar, 2008b: 11)" → **"2008"** (those intransitive/transitive passages are in *A Realist Theory of Science*).
- "(Bhaskar, 2008a)" → **"1993: 4"** (the ontic-fallacy "compulsive determination of knowledge by being" passage is in *Dialectic*, your 1993 entry, p.4).
- *Or*, if you own specific 2008 Routledge reprints, add "Bhaskar (2008a/2008b)" entries to the reference list instead.

### D2 — Kant Akademie citation (optional)
"(Kant, Critique of the Power of Judgment, Ak. 5:198)" uses the Akademie form with no year. Standard for Kant; for strict author-date consistency (edition-only) you could make it "(Kant, 2000, Ak. 5:198)". Optional.

### D3 — Reference-list slash entries (decide, then I/you can apply)
Three **reference-list** entries keep the orig/edition slash: "Adorno, T. W. (1966/1973)", "Brentano, F. (1874/1973)", "Scheler, M. (1928/2009)". That is standard for a reference list, so the A2 in-text edition-only fixes are consistent with leaving these as-is. **If your edition-only rule applies to the reference list too**, change them to "(1973)", "(1973)", "(2009)" respectively. Otherwise leave them.

---

## Note (no action needed)
Miura, 国際関係の中の環境問題 (2004): 15–16 — **page manually confirmed correct by the author** (2026-06-15). The audit is now complete with **every** citation in the manuscript verified against its actual source.
