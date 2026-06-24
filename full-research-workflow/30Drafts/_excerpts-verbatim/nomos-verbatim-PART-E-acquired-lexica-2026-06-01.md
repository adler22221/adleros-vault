---
type: literature
project: master-thesis
status: ai-draft
target: thesis
citation-status: citable
topic: [phusis, nomos, techne, physis, nature, art, law, lexica]
source-notes: []
summary: "Verbatim excerpts on the phusis / technē / nomos boundary from two newly-acquired reference lexica — Ritter's Historisches Wörterbuch der Philosophie (HWPh, complete 13-vol EPUB) and Cassin's Dictionary of Untranslatables (Princeton 2014). Brill's New Pauly not acquired (download backend outage) — flagged [VERIFY]."
---

# PART E — Acquired Lexica: HWPh + Cassin (verbatim)

> Companion to PART-A (lexica), PART-B (encyclopedias), PART-C (ancient canon), PART-D (contemporary collapse).
> Acquisition date: 2026-06-01. All passages below are transcribed verbatim from the source files; German left untranslated per task with short English glosses. Column/Spalte identifiers preserved where the digital edition records them (`[Sp. NNNNN]` = the HWPh digital edition's continuous column counter; print Band:Spalte given separately where known from cross-references).
> Route used throughout: libgen.li (`column=def`) → ads.php → get.php (CDN `booksdl.lc`). Anna's Archive `.org/.se/.li` were unreachable in this environment (HTTP 000); `annas-archive.gl` was reachable but its slow_download sits behind a DDoS-Guard JS challenge and IPFS gateways had no providers for the New Pauly CID.

---

## 1. Historisches Wörterbuch der Philosophie (HWPh)

**Work:** *Historisches Wörterbuch der Philosophie*, ed. Joachim Ritter, Karlfried Gründer, Gottfried Gabriel (Schwabe, Basel, 1971–2007), 13 vols.
**Acquired as:** complete EPUB, all 13 vols (digital "Gesamtwerk" edition).
**Local file:** `C:\Users\adler-standard\Downloads\thesis-pdfs\HWPh_Gesamtwerk_Bd1-13_86668e7b.epub` (31.6 MB; kept as EPUB, not converted, per project rule).
**Extraction:** EPUB unzipped (`zipfile`), entry XHTML located via `toc.ncx` navlabels, HTML stripped with `lxml`, column anchors (`<a id="pNNNNN">`) rendered as `[Sp. NNNNN]`.
**Print-Spalte cross-references** (from the Physis/Nomos article's own apparatus, authoritative): Gesetz = **Bd. 3, Sp. 494 ff.**; Nomos = **Bd. 6, Sp. 893–895**; Natur = **Bd. 6, Sp. 421–441**. Physis/Nomos is in **Bd. 7** (P–Q); Technik in **Bd. 10** (St–T); Kunst in **Bd. 4** (I–K). (The 5-digit `[Sp.]` IDs are the digital edition's running counter, not the print Spalte.)

### 1a. Physis/Nomos, Physis/Thesis  — *the single most on-point HWPh entry*
**Author:** L. Deitz. **Digital cols:** [Sp. 27512–27523]. **Print:** HWPh Bd. 7.
**Gloss:** The article on the physis/nomos (nature/law) and physis/thesis (nature/convention) antitheses — origin in 5th-c. medicine and ethnography, radicalization by the Sophists, Plato's attempted grounding of nomos in a transcendent physis, Aristotle's deflation, Stoic and Pauline reuse (νόμος φύσεως, "law of nature").

> [Sp. 27512]
> **Physis/Nomos** (φύσις/νόμος Natur/Gesetz), **Physis/Thesis** (φύσις/θέσις Natur/Satzung, Konvention)
> 1. *Physis/Nomos.* – Es ist weder bekannt, wann N. [1] als '(schriftlich festgelegtes) Recht' oder '(ungeschriebene) Sitte' zum ersten Mal der Ph. [2] in der Bedeutung von 'eigentlicher Beschaffenheit' oder 'wahrem Wesen' gegenübergestellt wurde, noch wer diesen Gegensatz als erster formuliert hat. Von DIOGENES LAERTIOS [3] wird er dem ARCHELAOS (Mitte des 5. Jh.) zugeschrieben, aber wie der fast selbstverständliche Gebrauch in Tragödie [4], Medizin und Historiographie zeigt, muß die Gegenüberstellung begrifflich schon in der ersten Hälfte des 5. Jh. geprägt worden sein und Verbreitung gefunden haben. So zeigt der Autor der hippokratischen Schrift Περὶ ἀέρων am Beispiel der Schädelform der Makrokephalen, daß die allgemein menschliche Natur durch langjährige Volkssitte entscheidend verändert werden kann und durchaus keine überall gültige Konstante ist [5], während HERODOT die Totensitten der Hellenen und Inder miteinander kontrastiert, um dadurch die völkerspezifische Abhängigkeit der Nomoi zu exemplifizieren [6]. ...
>
> Aber erst mit der Sophistik des 5. Jh. wurde der Gegensatz auf alle Bereiche des öffentlichen und privaten Lebens angewendet. So äußert Hippias in PLATONS ‹Protagoras›: «Ich bin der Auffassung, daß ihr alle Verwandte, Hausgenossen und Mitbürger seid, [und zwar] von Natur (φύσει), [wenn auch] nicht durch Gesetz (νόμῳ)». Das Gesetz, der Tyrann der Menschen, regele vieles gewaltsam gegen die Natur [8]. Schärfer noch heißt es in einem ANTIPHON-Fragment, daß «die Gebote der Gesetze willkürlich, die der Natur dagegen notwendig» sind (τὰ μὲν γὰρ τῶν νόμων (〈ἐπίθ〉)ετα, τὰ δὲ 〈τῆς〉 φύσεως ἀ〈ναγ〉καῖα); den «natürlich gewachsenen» (φύν〈τα〉) Vorschriften wird hier der Vorzug gegenüber den «vereinbarten» (ὁμόλογη〈θέν〉τα) gegeben [9]. ... THUKYDIDES überliefert ... den Ausspruch: «Es ist völlig unmöglich ..., daß die menschliche Natur (ἀνθρωπεία φύσις), wenn sie ... einem Ziel zustrebt ... durch die Kraft der Gesetze (νόμων ἰσχύς) ... davon abgehalten werde» [12]. Radikaler noch vertritt die platonische Dialogfigur Kallikles, daß die Gesetze nur von den Schwachen eingerichtet werden, um sich gegen die von Natur aus Starken behaupten zu können. Die Natur der Stärkeren bedarf keiner Gesetze; sie gebietet sich selbst [13].
>
> [Sp. 27514]
> ... Bei ARISTOTELES ist die Auseinandersetzung um den Gegensatz von nebensächlicher Bedeutung. Für ihn besitzt jede menschliche Gesellschaft zugleich geschriebene und (aus Gewöhnung und Tradition hervorgegangene) ungeschriebene Gesetze [19]; 'ungeschriebene Gesetze' können auch allgemeine, überstaatliche und für alle Menschen verbindliche 'Naturgesetze' (νόμοι τῆς φύσεως, νόμοι κατὰ φύσιν) sein, wie diejenigen, auf die sich Antigone beruft [20]. ...
>
> [Sp. 27515]
> ... am prägnantesten gebraucht es CHRYSIPP [24]: Zwischen Göttern und Menschen besteht eine Gemeinschaft, da beide am Logos teilhaben, der ein naturgegebenes Gesetz ist (ὅς ἐστι φύσει νόμος). PAULUS verwendet die Antithese, um darzulegen, daß die Heiden, auch ohne das geschriebene Mosesgesetz der Juden zu besitzen, dessen Forderungen von Natur erfüllen können und sich auf diese Weise selbst Gesetz sind [25].
> ... man [gebrauchte] sie bald in der Form νόμοι τῆς φύσεως (Gesetze der Natur) ..., um dadurch ein ewiges, allgemein verbreitetes und in der Natur gegründetes Gesetz zu bezeichnen [26].
>
> [Sp. 27516]
> 2. *Physis/Thesis.* – Dieses Gegensatzpaar ist der Antithese ‹Ph./N.› teilweise parallel. ... Es spielt vor allem im Rahmen der sprachtheoretischen Diskussion über die natürliche oder konventionelle, d.h. durch Übereinkunft (συνθήκη) der Sprechenden entstandene und durch sie bedingte Richtigkeit der Namen (ὀρθότης τῶν ὀνομάτων [29]) eine Rolle. ...
> — L. DEITZ

**English gloss of the load-bearing passages:** The physis/nomos opposition is first attested in 5th-c. medicine/ethnography (Hippocrates *Airs Waters Places*; Herodotus), generalized by the Sophists (Hippias: kin "by nature" not "by law"; Antiphon: the commands of laws are arbitrary/conventional, those of nature necessary; Callicles: laws are a device of the weak; the nature of the strong needs no laws). Plato tries to re-ground nomos in a transcendent nature (φύσει δίκαιον); Aristotle deflates the opposition and admits ἄγραφοι νόμοι / νόμοι τῆς φύσεως; the Stoa (Chrysippus) makes the Logos a *law that is by nature* (φύσει νόμος); Paul (Rom. 2:14) makes the Gentiles "a law to themselves."

### 1b. Nomos
**Author:** Th. Rentsch (the Nomos column follows immediately after his preceding article). **Digital col:** [Sp. 23075 ff.]. **Print:** HWPh Bd. 6, Sp. 893–895.
**Gloss:** Etymology from IE *nem (νέμειν "to graze / to distribute, allot"); nomos as "Nahme" and "first measurement and division of pasture"; Hesiod's "order governing field-work"; the written vs. unwritten nomos; nomos displacing the older θεσμός.

> [Sp. 23075]
> **Nomos** (griech. νόμος). Das Fremdwort ‹N.›, das häufig noch immer als Synonym von Gesetz, Moralgesetz, Gebot oder Normordnung gebraucht wird [1], hat in der politischen Ethik des Protestantismus und in der modernen Rechtstheorie einen Bedeutungswandel erfahren, der darauf hinausläuft, die Vorstellungen der Entwicklung vom N. zum Gesetz vom Ursprung her zu revidieren. ...
> Zur indogermanischen Wurzel ‹*nem› gehörend [2], ist ‹N.› ein nomen actionis von νέμειν, das a) weiden, weiden lassen und b) verteilen, zuteilen, teilen bedeutet. Zur Zeit der nomadischen Landnahme könnte demnach mit ‹N.› die ‹Nahme› des Landes und die «erste Messung und Teilung der Weide» gemeint gewesen sein. Bei HESIOD ist N. schon die «Ordnung, die den Gang der Arbeit auf den Feldern für alle bestimmt», im übertragenen Sinn auch die «Art und Weise des Gottesdienstes». In einem erweiterten Sinn heißt ‹N.› Regel, Brauch, auch Brauchtum, Sitte, Lebensordnung einer Gemeinschaft [3], bei HERAKLIT und PINDAR die politische (Real-)Verfassung der Polis samt Sitte, Brauch und Herkommen [4]. Immer wirkt im N. «der Gott, der ihn der Polis eingestiftet hat» [5]. Bald tritt allerdings der «geschriebene» N. neben den «ungeschriebenen» [6]. Der N. als Norm und Verordnung verdrängt den alten θεσμός von seinem Platz [7]. ...

**English gloss:** Nomos is a *nomen actionis* of νέμειν ("to graze; to distribute/allot"); at the time of nomadic land-taking it could mean the "taking" (Nahme) and "first measurement and division of pasture." In Hesiod already an "order governing field-work"; in Heraclitus/Pindar the political constitution of the polis with custom and tradition; the god "instilled it in the polis." The written nomos soon stands beside the unwritten; nomos as norm/ordinance displaces the older θεσμός. (This etymology — Nahme / division of pasture — is the Schmittian *Nomos der Erde* root.)

### 1c. Natur
**Digital col:** [Sp. 21620 ff.]. **Print:** HWPh Bd. 6, Sp. 421–441. (Long multi-section article; verbatim headword + Antike opening only.)
> [Sp. 21620]
> **Natur** (griech. φύσις, lat. natura, engl. nature, frz. nature, ital. natura)
> I. Antike. – Zwei Grundbedeutungen, die der Begriff ‹Physis› (Ph.) auch schon in vorphilosophischem griechischem Kontext hat, so in der mythischen Dichtung bei HOMER [1], AISCHYLOS [2], SOPHOKLES [3] und PINDAR [4] ..., sind für den Ph.-Begriff in der griechischen Philosophie besonders fundamental, nämlich einerseits die Bedeutung (Beschaffenheit, Wesen) [6] und andererseits die Bedeutung (Werden, Wachstum, Wuchs) [7]. Die bekannteste Bedeutung von Ph., wonach der Begriff das Insgesamt aller natürlichen Seienden in ihrem Wesen und dem Gesetz ihres Werdens und Wachsens meint, findet sich dagegen erst relativ spät und ist eine Schöpfung der Philosophie des ARISTOTELES [8] mit Anklängen schon bei PLATON [9]. ...

**English gloss:** Physis has two pre-philosophical core senses — (a) constitution/essence (Beschaffenheit, Wesen) and (b) becoming/growth (Werden, Wachstum). The familiar sense of physis as "the totality of all natural beings in their essence and the law of their becoming and growth" is comparatively late, an Aristotelian creation with Platonic anticipations.

### 1d. Technik
**Digital col:** [Sp. 42325 ff.]. **Print:** HWPh Bd. 10 (St–T).
> [Sp. 42325]
> **Technik** (griech. τέχνη; lat. ars, disciplina, technica; engl. technology, technic; frz. technique; span. técnica)
> A. Antike. – Der Begriff ‹T.›, wie er sich in der zweiten Hälfte des 18. Jh. mit dem Beginn der industriellen Revolution als Bezeichnung für das Ganze des maschinell/instrumentell Verfügbaren herausbildet, ist zu einem Schlüsselbegriff der Moderne avanciert ... Die deutsche Wortbildung des Substantivs ‹T.› geht auf das lateinische Wort ‹technica› zurück, das im 17. Jh. unter direktem Rückgriff auf das griechische Adjektiv τεχνικός ('das einer τέχνη Gemäße') gebildet wird [3]. Τέχνη bezeichnet ein zielgerichtetes, sachgemäßes Können, eine Fertigkeit, Geschicklichkeit oder Kunst (ars). Bei den frühesten Belegen ist zwar die etymologische Herkunft aus dem Wortstamm *tek (bauen, zimmern) bemerkbar ...; immer geht es dabei um ein regelgeleitetes, sachverständiges, also an bestimmtes Wissen gebundenes praktisches oder theoretisches Können.
> [Sp. 42326] ... Der Werkzeuggebrauch und die Künste (τέχναι, artes) als Ausdruck von Kultur gegenüber der bloßen Natur [7] sind seit der Antike in Mythos und Philosophie verschiedener Kulturentstehungstheo[rien] ...

**English gloss:** Modern "Technik" (the whole of what is machine/instrument-available) is an 18th-c. coinage; the word derives from Latin *technica* < Greek τεχνικός ("conforming to a τέχνη"). Τέχνη = goal-directed, competent skill bound to determinate knowledge; root *tek- ("to build, to carpenter"). Tool-use and the arts (τέχναι, artes) figure since antiquity as the **expression of culture over against mere nature** — the technē-vs-physis axis.

### 1e. Kunst, Kunstwerk
**Digital col:** [Sp. 15526 ff.]. **Print:** HWPh Bd. 4 (I–K).
> [Sp. 15526]
> **Kunst,** (griech. τέχνη; lat. ars; ital. arte; frz. und engl. art), **Kunstwerk** (griech. ἔργον; lat. artificium, opus; ital. artificio, opera d'arte; frz. œuvre d'art; engl. work of art)
> I. Der K.-Begriff in der Antike. – 1. Die enthusiastische Herkunft. – HOMERische Sätze wie den, Hephaist und Athene hätten den Schmied seine K. gelehrt [1], bringt EPICHARM auf die allgemeine Form, göttliche Vernunft begleite alle K., die ausnahmslos vom Gott und nicht vom Menschen erfunden seien [2]. ...

**English gloss:** "Kunst" = τέχνη / ars; "Kunstwerk" = ἔργον / opus. The antique concept begins in an "enthusiastic" provenance — all art (Kunst) is god-given, "invented by the god and not by man" (Epicharmus), the poet being the conduit of divine knowledge of all the arts — a frame Plato (*Ion*) later contests.

### 1f. Gesetz
**Digital col:** [Sp. 8757 ff.]. **Print:** HWPh Bd. 3, Sp. 494 ff.
> [Sp. 8757]
> **Gesetz** (griech. νόμος, lat. lex, ital. legge, frz. loi, engl. law)
> I. Im Rechtssinne ist G. die von einer hierzu befugten Rechtsautorität durch Satzung erzeugte Vorschrift für menschliches Verhalten und hat nicht bloß deskriptive, sondern vor allem präskriptive Funktion. ... 1. Der im frühgriechischen Rechtsdenken wurzelnde ... vielschichtige Begriff des Nomos, der als verpflichtende Lebensordnung der griechischen Polis noch keine strikte Trennung zwischen Brauch und G., Ethos und Recht gestattet ... Ungeachtet seiner Herkunft aus diesem älteren Sprachgebrauch kann das Wort νόμος sowohl das aller Satzung zugrunde liegende Herkommen als auch das gesatzte G. bezeichnen [2].

**English gloss:** In the juridical sense, Gesetz (law) is a prescription for human conduct issued by a competent legal authority through statute — *prescriptive*, not merely descriptive. Its problematic is already worked out in antiquity. The polis concept of Nomos permits *no strict separation* between custom and law, ethos and right; νόμος can denote both the underlying tradition (Herkommen) and the posited statute (gesatztes Gesetz).

---

## 2. Cassin (ed.), Dictionary of Untranslatables: A Philosophical Lexicon

**Work:** Barbara Cassin (ed.), Emily Apter, Jacques Lezra & Michael Wood (eds., English ed.), *Dictionary of Untranslatables: A Philosophical Lexicon* (Princeton University Press, 2014).
**ISBN:** 9780691138701 / 0691138702.
**Acquired as:** PDF, 1339 pp. (text layer present on 1320/1339 pp.), 63 MB.
**Route:** libgen.li search `column=def` by ISBN → ads.php → get.php (resumed via HTTP-range `-C -` after a mid-stream CDN timeout; final size 66,080,609 B matches the catalog's 63 MB).
**Local file:** `C:\Users\adler-standard\Downloads\thesis-pdfs\Cassin_2014_Untranslatables.pdf`
**Extraction:** PyMuPDF (`fitz`) `get_text()`; no OCR needed (native text layer, Greek polytonic intact).

### 2a. NATURE  *(= the PHYSIS entry)*
**Authors:** Pascal David; box "Homer, phusis and pharmakon" by Barbara Cassin & Pascal David. **PDF pp. 741–742 / book pp. 703–704.** Cross-refs: ART, CULTURE, ERSCHEINUNG, ESSENCE, ESTI, FORCE, LIGHT, MIMÊSIS, TO BE.
**Gloss:** The entry is built around Heidegger's problematization of the translation of φύσις by *natura*; it states the decisive ontological distinction between φύσις (the "how" of all appearing; a name for Being) and *natura/nature* (a *sector* of the existent, paired against culture/history/art).

Headword box (verbatim):
> NATURE
> GERMAN  Natur, Aufgang
> GREEK  phusis [φύσις]
> LATIN  natura
> RUSSIAN  priroda [природа], natura [натура]
> SPANISH  naturaleza
> ➤ ART, CULTURE, ERSCHEINUNG, ESSENCE, ESTI, FORCE, LIGHT, MIMÊSIS, TO BE

Aristotle's etymology (verbatim):
> "Nature" [phusis] means (1) the genesis [genesis (γένεσις)] of growing things [tôn phuomenôn (τῶν φυομένων)]—the meaning that would be suggested if one were to pronounce the u in phusis long. (Metaphysics, 5.4. 1014b 17–19)

The decisive boundary (verbatim, book p.704):
> Breaking with a long tradition, or rather a long obstruction, Heidegger proposes, then, to reinterpret phusis not as "nature" (from Latin nasci, "to be born"), but as Aufgang, an "opening-up" or "emergence." But contrary to a commonly held view, Heidegger does not oppose a natura-"birth" to a phusis-"growth" that he considers more originary; rather, the line of demarcation runs between phusis on one hand, and natura as birth and growth combined on the other. **While nature designates a sector of the existent (in pairs of oppositions in which the other term may be culture—nature/culture—history, art, super-nature [grace], etc.), phusis names instead the "how" (desinence-sis: phu-sis) in accord with which everything appears. It is a name for Being, not for the existent. In short: "nature" is ontically oriented, and phusis is ontological.**

And the Heraclitean fragment (verbatim):
> Rather than Homer, it is Heraclitus who constitutes the source on which Heidegger constantly drew for the meaning of phusis, and notably fragment 123: phusis kruptesthai philei [φύσις ϰϱύπτεσθαι φιλεῖ]. This fragment has often been translated as "Nature likes to hide itself."

### 2b. ART  *(= the TECHNĒ / ARS entry)*
**PDF pp. 80–85 / book pp. 42–47.** Cross-refs (Box 1): LOGOS, PRAXIS, VIRTUE.
**Gloss:** Establishes that for the Ancients "art and technique were one and the same thing" (ars = technē), and gives the canonical Aristotelian statement of the technē/physis relation — art completes and imitates nature.

art = technique = ars = technē (verbatim, book p.43):
> The "art" of the Ancients includes every kind of making, and thus what we would call "technique" or "technology." ... For the Ancients, and so long as people thought with Latin, art and technique were one and the same thing: Latin ars (from the root *er-, ...) equals Greek technê [τέχνη] (from the root *teks-, "construct," "make"). Since art and technique are defined by the production of an object, the question is what guarantees the success of the finished product ...

**The single most useful technē/physis passage (verbatim, book p.44):**
> [art] consists of bringing into existence things "whose origin is in the maker and not in the thing made," Nicomachean Ethics, 6.4.1140a13–14). But that always also implies that art provides the concepts necessary for thinking about nature. ... From this comes the famous complement: "Generally art partly completes what nature cannot bring to a finish [epitelei ha hê phusis adunatei apergasasthai (ἐπιτελεῖ ἃ ἡ φύσιϛ ἀδυνατεῖ ἀπεϱγάσασθαι)], and partly imitates her" (Physics 2.8.199a15–16). Art displays both its dependency on the model by imitating it, and a certain superiority in realizing what the model, even though it is prior, was not able to produce.

And on the breadth of the field of technē (verbatim, book p.44):
> The field of technê can thus include all values from divine demiurgy (artifex mundi, the Romans called it) to human power or faculty, which is rational and useful, but obviously susceptible to Promethean excess and trickery.

> [NOTE: Cassin treats technē primarily under ART (= ars). A discrete "TECHNE" sub-treatment also appears within the MIMÊSIS entry, book p.662: "techne is distinguished from praxis, those two terms then corresponding to two different modes of regulated and finalized activity: 'the disposition to act accompanied by a rule [τῆς ποιητιϰῆς ἕξεως]' (6.4.1140a 3–5; see PRAXIS)." — PDF p.700.]

### 2c. NOMOS / LAW  *(= the THEMIS / DIKÊ / NOMOS entry)*
**Author:** [entry signed within the THEMIS cluster]. **PDF pp. 1162–1166 / book pp. 1124–1128.** Headword: `THEMIS [θέμις] / DIKÊ [δίϰη] / NOMOS [νόμoς] (GREEK)`. Cross-refs: JUSTICE, LAW, LEX, RIGHT/JUST/GOOD, POLIS, PRAVDA, etc.
**Gloss:** Traces the succession of Greek "rule/law" terms — themis → thesmos → nomos — and gives the crucial point that nomos carries a *spatial* notion of the city ("division") and replaces thesmos in the democratic reforms.

Headword box (verbatim):
> THEMIS [θέμις] / DIKÊ [δίϰη] / NOMOS [νόμоς] (GREEK)
> ENGLISH  rule, juridical norm, principle, procedure, justice, law
> FRENCH  règle, prescription, jugement, justice, loi
> GERMAN  Gottheit der Recht, Ordnung

**The single most useful nomos passage (verbatim, book p.1124):**
> The vocabulary that organizes the theories and practices of justice in ancient Greece changes a great deal from Homer to Aristotle, with a succession of expressions for "rule" or "law" that includes themis [θέμις] (or the plural themistes [θέμιστες]), then thesmos [θεσμός]—both drawn from the root *dhe-, "lay down," which refers to external sources of authority and divine power—and finally, starting in the fifth century, **nomos [νόμоς], "division," which signals a spatial notion of the city.** ... the law is established through procedure and does not preexist it.

The themis → thesmos → nomos succession (verbatim, book p.1124):
> Starting at the end of the sixth century BCE in Athens (perhaps as part of the democratic reforms of Cleisthenes), nomos [νόμоς] starts to be substituted for thesmos, before replacing it completely. In its political usage, nomos, unlike thesmos, seems to involve the idea of an order that is accepted by those who submit to it (cf. Ostwald, Nomos).

> [NOTE: the literal LATIN counterpart is treated by Cassin under a separate entry **LEX / JUS (LATIN)**, book p.565 ff. (PDF p.603); not transcribed here — flag for a follow-up pass if the Latin lex/jus material is needed.]

---

## 3. Brill's New Pauly / Der Neue Pauly

**[VERIFY: not acquired — download backend outage 2026-06-01.]**

**Work sought:** *Brill's New Pauly: Encyclopaedia of the Ancient World* (Antiquity), ed. Hubert Cancik & Helmuth Schneider (Brill, 2002–2010), English ed. Target entries: **physis** (Vol. 11, Phi–Prok, 2007; ISBN 9789004142169), **nomos** (Vol. 9, Mini–Obe, 2006; ISBN 9789004122727), **techne/technē** (Vol. 14, Sym–Tub, 2009; ISBN 9789004142190).

**Items were located** (metadata + MD5 confirmed on libgen.li/.la and on annas-archive.gl), but **none could be downloaded** in this session. Failure detail, for an honest record and to support a later retry:
- libgen.li / libgen.la `get.php` → consistent **HTTP 500 / 504** from the file CDN `cdn2.booksdl.lc` (the redirect target). Cassin downloaded from the same CDN ~15 min earlier, so this is a transient backend overload specific to this window, not a dead link.
- Anna's Archive `.org / .se / .li` → **HTTP 000** (unreachable from this environment).
- `annas-archive.gl` → reachable (HTTP 200) and has the records, but `slow_download` sits behind a **DDoS-Guard JS challenge** requiring a real browser; **no Chrome browser is connected** to this session, so the challenge cannot be solved.
- IPFS (Vol. 11 CID `QmQ93PCWxZyNf8WANKxuY2GZxvUjsZSkGGbGgkYLkNJ3yu`) → public gateways (dweb.link, w3s.link, nftstorage.link, ipfs.io, etc.) all returned **504 / 403** — no providers serving the CID.

**MD5s for a clean retry when the CDN recovers (or via a connected browser on annas-archive.gl):**
- Vol. 11 (physis): `325997953f446b83b131328de8037571`
- Vol. 14 (technē): `f6cd817b9834ead92a2a7b6bdc545c16`
- Vol. 9 (nomos): `4ff2e5f9a398d3245771e228fc1ef8e0`

**Retry 2026-06-01 (later same day) — STILL BLOCKED.** `ads.php` resolves valid `get.php` keys for all three MD5s on both libgen.li and libgen.la, but every download is pinned to the file-CDN node **`cdn2.booksdl.lc`**, which read-times-out on every attempt (libgen.la's ads for Vol. 14 also returned HTTP 500). Notably, in the same window a Kant Guyer&Wood PDF downloaded fine from a *different* node, `cdn3.booksdl.lc` — so this is a **node-specific outage on cdn2**, not a network-wide failure: the three New Pauly files happen to be hosted on the unhealthy node. No partial files written. Retry again once cdn2 recovers, or fetch via a browser-solved DDoS-Guard challenge on annas-archive.gl.

---

## Provenance summary (for Zotero cataloging)

| Source | Vol/Page or Col | ISBN | Route | Local path | Status |
|---|---|---|---|---|---|
| HWPh — Physis/Nomos, Physis/Thesis (Deitz) | Bd. 7 [dig. Sp. 27512–27523] | (set) | libgen.li (already on disk) | `…\thesis-pdfs\HWPh_Gesamtwerk_Bd1-13_86668e7b.epub` | ✅ extracted |
| HWPh — Nomos | Bd. 6, Sp. 893–895 [dig. 23075] | (set) | ″ | ″ | ✅ |
| HWPh — Natur | Bd. 6, Sp. 421–441 [dig. 21620] | (set) | ″ | ″ | ✅ |
| HWPh — Technik | Bd. 10 [dig. 42325] | (set) | ″ | ″ | ✅ |
| HWPh — Kunst, Kunstwerk | Bd. 4 [dig. 15526] | (set) | ″ | ″ | ✅ |
| HWPh — Gesetz | Bd. 3, Sp. 494 ff. [dig. 8757] | (set) | ″ | ″ | ✅ |
| Cassin — NATURE (phusis) | pp. 703–704 (PDF 741–742) | 9780691138701 | libgen.li ads→get (resumed) | `…\thesis-pdfs\Cassin_2014_Untranslatables.pdf` | ✅ |
| Cassin — ART (technē/ars) | pp. 42–47 (PDF 80–85) | 9780691138701 | ″ | ″ | ✅ |
| Cassin — THEMIS/DIKÊ/NOMOS | pp. 1124–1128 (PDF 1162–1166) | 9780691138701 | ″ | ″ | ✅ |
| Brill's New Pauly — physis | Vol. 11 | 9789004142169 | — | — | ❌ [VERIFY: not acquired] |
| Brill's New Pauly — nomos | Vol. 9 | 9789004122727 | — | — | ❌ [VERIFY: not acquired] |
| Brill's New Pauly — technē | Vol. 14 | 9789004142190 | — | — | ❌ [VERIFY: not acquired] |

Links: [[master-thesis]] · [[squeeze-ontology]] · companion files [[nomos-verbatim-PART-A-lexica]] [[nomos-verbatim-PART-B-encyclopedias]] [[nomos-verbatim-PART-C-ancient-canon]] [[nomos-verbatim-PART-D-contemporary-collapse]]
