---
type: concept
project: master-thesis
status: ai-draft
topic: [consistency-audit, copy-edit, cross-reference, table-numbering, locked-terms]
target: thesis
summary: "Whole-thesis consistency pass for print: cross-references, table numbering, locked-term through-lines, exteriorized/exosomatized alignment, Ch VI §D duplication, English-first CJK, heading sanity. Fix-list only — manuscript not edited."
source-notes: []
---

# Consistency scan — "Between the Universe and the Metaverse" (working, 20260609)

> Scope: read-only consistency pass on the single working .md. **Manuscript NOT edited.** Locations quote a unique snippet; line numbers are from the audited file.
> Section map confirmed from headings: Ch II is §A survival / §B "why artificiality not technology" / §C virtuality / §D **typology** / §E **double edge**. The double edge is now §IIE; §IID is the typology. Confirmed in the heading scan (lines 201, 217).

---

## SUMMARY (counts + MUST-FIX list)

- **Category 1 (cross-reference integrity):** 2 findings — 1 MUST-FIX, 1 POLISH
- **Category 2 (table numbering):** 1 finding — 1 MUST-FIX (missing Table 2-1; Ch II tables are 2-2, 2-3 with no 2-1)
- **Category 3 (locked-term through-lines):** 2 findings — 0 MUST-FIX, 2 POLISH
- **Category 4 (exteriorized vs exosomatized organ):** 1 finding — MUST-FIX (Ch II §A names this aspect neither way; Conclusion + footnote claim a phrase that is absent from §A)
- **Category 5 (Ch VI §D internal duplication):** 1 finding — POLISH
- **Category 6 (English-first CJK):** 2 findings — 0 MUST-FIX, 2 POLISH
- **Category 7 (heading/numbering sanity):** clean — 0 findings

**MUST-FIX list (4):**
1. **[Cat 1]** Footnote `[^c2-obara-petification]` (line 569) cites "the §IID pre-brief" for petification material that belongs to the **double edge (§IIE)**, not the typology (§IID). → "§IIE pre-brief".
2. **[Cat 2]** Chapter II has **Table 2-2 and Table 2-3 but no Table 2-1.** The first Ch II table (the typology, line 206) and its in-text call (line 204) are both numbered 2-2. → renumber typology to **Table 2-1** and the five-diagnoses table to **Table 2-2** (and update the two in-text refs), OR confirm a deliberately dropped 2-1 — but as printed it is a gap.
3. **[Cat 4 / Cat 1]** Footnote `[^v1-stiegler]` (line 503) asserts: *"Ch II §IIA already runs 'Technology as exosomatization.'"* That phrase **does not appear anywhere in §IIA** (or in the Ch II body). §IIA names this aspect only via Stiegler's "prosthesis"/"exteriorization." → align the chapter and the summary (see Cat 4 for the recommended minimal fix toward "exosomatized organ").
4. **[Cat 4]** Conclusion §A (line 709) names Ch II's first aspect **"the exosomatized organ"**; Introduction §F (line 73) names it **"technology as the exteriorization, or exosomatization, of human organs and memory"**; Ch II §A itself names it **neither**. The three places must agree (author prefers "exosomatized").

---

## Category 1 — Cross-reference integrity

### 1.1 [MUST-FIX] Footnote points to §IID (typology) for double-edge (§IIE) material
- **Location (line 569), footnote `[^c2-obara-petification]`:** *"Japanese verbatim carried from the §IID pre-brief, NLM-attributed but unpaged."*
- **Problem:** This footnote is anchored in the **double edge** section (§IIE — the Obara self-petification diagnosis sits in Table 2-3 / §IIE, lines 228, 235). Under the current section map the double edge is **§IIE**; **§IID is now the typology**. "§IID pre-brief" therefore points the reader (and any future editor) at the wrong section. Per the audit rule (any §IID that *means* the double edge must become §IIE), this is a mismatch.
- **Fix:**
  - `old_string`: `carried from the §IID pre-brief`
  - `new_string`: `carried from the §IIE pre-brief`
- **Note:** This is the **only** "§IID"/"§2D" string in the file (grep-confirmed). All "§IIC" references (lines 52, 208, 566, 567, 574) correctly point to virtuality and are fine. No other double-edge cross-ref is mislabeled.

### 1.2 [POLISH] Footnote claims §IIA "runs 'Technology as exosomatization'" — phrase absent
- **Location (line 503), footnote `[^v1-stiegler]`:** *"Ch II §IIA already runs 'Technology as exosomatization.'"*
- **Problem:** Section pointer (§IIA = "Artificiality as the human mode of survival") is correct, but the **quoted phrase is not in §IIA** — §IIA uses "prosthesis"/"exteriorization," never "Technology as exosomatization." This is also load-bearing for Category 4. Listed here as the cross-ref symptom; the substantive fix is in Cat 4.
- **Fix (cross-ref side):**
  - `old_string`: `Ch II §IIA already runs "Technology as exosomatization."`
  - `new_string`: `Ch II §IIA already names this aspect (as Stiegler's exteriorization of organs and memory); the thesis uses exosomatization for it throughout.`
  - (or, if Cat 4 fix inserts the word "exosomatized" into §IIA, leave the pointer and just drop the false quotation.)

### Verified-correct cross-references (no action)
- §IIC → virtuality: lines 52, 208 (Table 2-2 header: "the field of virtuality, §IIC"), 566, 567, 574. ✓
- "Chapter IV.A" → Adorno & Horkheimer (§IV.A): lines 230, 237. ✓
- "§IV.B" → Habermas/colonization (footnote `[^v0-naming]`, line 500). ✓
- §VI.C (Type 2) and §VI.E (Type 4) cross-refs inside §VI.D (lines 647, 641): ✓ correct targets.
- "Type 1/2/3/4" labels in §VI body, Table 6-1, Table 6-2 are internally consistent.
- Chapter content claims in Conclusion §A (Ch I–VI summaries, line 709) match the chapters — except the "exosomatized organ" wording (see Cat 4).

---

## Category 2 — Table numbering

### 2.1 [MUST-FIX] Missing Table 2-1 (Ch II jumps 2-2 → 2-3)
- **Labels found (grep-confirmed, in order):** 1-1, **2-2, 2-3**, 3-1, 4-1, 5-1, 5-2, 6-1, 6-2.
- **Problem:** Every other chapter starts its table numbering at `N-1`. Chapter II has **no Table 2-1**; its first table (the typology of artificiality) is labeled **2-2** at line 206, and the in-text call at line 204 also says 2-2. Result: a missing-number gap that a print reader will notice, and the typology — the chapter's central apparatus — carries a number implying a non-existent predecessor.
- **Recommended fix (renumber down by one within Ch II):**
  - Line 204 — `old_string`: `Table 2-2 sets it out, and the paragraphs that follow read it across`
    `new_string`: `Table 2-1 sets it out, and the paragraphs that follow read it across`
  - Line 206 — `old_string`: `**Table 2-2. The typology of artificiality.**`
    `new_string`: `**Table 2-1. The typology of artificiality.**`
  - Line 222 — `old_string`: `**Table 2-3. Five diagnoses of the made's tendency-toward-inversion.**`
    `new_string`: `**Table 2-2. Five diagnoses of the made's tendency-toward-inversion.**`
  - **Cross-check after renumber:** the Table 2-2 header text "(the field of virtuality, §IIC)" at line 208 belongs to the typology table — it stays with whatever number the typology table gets (2-1 under this fix). No other reference uses "Table 2-2"/"Table 2-3" elsewhere in the body (grep-confirmed), so no further updates needed.
- **If instead a Table 2-1 was cut:** the author should confirm whether a Table 2-1 was deliberately removed and the others not renumbered; either way the printed sequence must be made gapless.
- **Other chapters:** 5-1→5-2 sequential ✓; 6-1→6-2 sequential ✓; 1-1, 3-1, 4-1 each the sole table in their chapter ✓. Every table is referenced in text (1-1 "the table below" L131; typology L204; 2-3/diagnoses L221 "I set them side by side… Table 2-3"; 3-1 L302 lead-in; 4-1 L381; 5-1 L417; 5-2 L467/469; 6-1 L599–600; 6-2 L667–669). No orphan tables, no dangling refs. The only defect is the missing 2-1.

---

## Category 3 — Locked-term through-lines

Overall: through-lines are held consistently. Two minor synonym/gloss notes.

### 3.1 [POLISH] "supremacy of the subject" appears once amid pervasive "sovereignty of the subject"
- **Location (line 696, §VI.H):** *"to loosen **the supremacy of the subject** and to bear more of the anti-intended as constitutive…"* — in the **same paragraph** that opens "At the level of **the sovereign subject**…".
- **Problem:** The thesis's locked term is **sovereignty of the subject / the sovereign subject** (40+ occurrences across Intro, III, IV, V, VI, Conclusion). "Supremacy of the subject" occurs exactly once (line 696). It reads as a near-synonym and is not wrong in sense, but a print reader may take "supremacy" to be a distinct concept. (NB: the standing memory note uses "supremacy of the subject" as the mode's characteristic — but the *manuscript's* through-line is "sovereignty.")
- **Fix (align to the manuscript through-line):**
  - `old_string`: `to loosen the supremacy of the subject`
  - `new_string`: `to loosen the sovereignty of the subject`

### 3.2 [POLISH] 道/理/相 and 偽道/偽理/偽相 — glosses consistent; one redundancy of "real/actual/empirical handles"
- **Through-lines verified consistent:**
  - 道/理/相 (real/actual/empirical) introduced and glossed at Ch I §E (line 131), re-glossed in footnotes `[^dlx-strata]` (578), `[^v0-strata]` (501); used consistently in Ch V (417, Table 5-1) and Ch VI (589). ✓
  - 偽道/偽理/偽相 first glossed via "forged Dao" (offstage) at line 173; the metaverse triad introduced at line 417 and Table 5-1 (425). Senses are stable throughout (no drift from "forged/made" to anything else). ✓
  - Four squeeze types — Type 1 organismic / Type 2 civilizational / Type 3 global·dis-embedding / Type 4 metaverse — consistent in §VI.A–F, Table 6-1, Table 6-2. ✓
  - as-intended/anti-intended (意のままになる/にならない): consistent; CJK glossed at first use (line 343, with the inclusive-意 reading) and reused with the embedded/dis-embedded pairing. ✓
  - self-finishing (自己完結化, human side) vs self-completion (自足完成化, apparatus side): mapping is correct and never swapped — explicitly paired at line 498 ("Apparatus-side self-completion (自足完成化) and human-side delegation — Uegaki's 自己完結化") and footnote `[^v8-coupling]` (543). ✓
  - dis-embedded/embedded life (無限の生/有限の生): consistent; the deliberate non-literal rendering is flagged in `[^iv-rendering]` (556). ✓
  - semiotic (genus) vs biosemiotic (living subset): consistent across §IIC (189), §IID (205), and footnotes `[^c2-meaning-semiotic]` (566) / `[^c2-semiotic-occupants]` (567). ✓
- **Minor note (optional, no fix required):** "real / actual / empirical are critical-realist handles only, parenthetical at first mention and nowhere in the running body" is asserted verbatim in *both* `[^dlx-strata]` (578) and `[^v0-strata]` (501). Harmless but duplicative across footnotes; could collapse one into a back-reference. POLISH-optional.

---

## Category 4 — "exteriorized" vs "exosomatized" organ (Ch II vs Conclusion)

### 4.1 [MUST-FIX] The three statements of Ch II's first aspect do not agree
Exact wording at each site:
- **Conclusion §A (line 709):** *"artificiality at its root, in three aspects: **the exosomatized organ**, the causally efficacious nonmaterial, and the laws of artificial environments…"*
- **Introduction §F (line 73):** *"artificiality in its three aspects: **technology as the exteriorization, or exosomatization,** of human organs and memory (Lotka, 1945; Stiegler, 1998); virtuality…; and the irreducibility…"*
- **Chapter II §A (lines 148–166):** names this aspect **neither "exosomatized" nor "exteriorized" as a label.** It runs Stiegler's **"prosthesis"** ("The prosthesis is not a mere extension of the human body; it is the constitution of this body qua 'human'", L152) and **epiphylogenesis / tertiary retention** (L161). The word "exosomatiz*" first enters the thesis only in **Chapter V** (L431, footnote `[^v1-stiegler]` L503). Footnote `[^v1-stiegler]` even *claims* §IIA "already runs 'Technology as exosomatization'" — but that phrase is absent from §IIA.
- **Problem:** Conclusion says "exosomatized organ"; Intro says "exteriorization, or exosomatization"; the chapter being summarized uses neither term for the aspect. Summary, intro, and chapter disagree on the name of the very first aspect of artificiality.
- **Recommended minimal fix (align toward "exosomatized," author's preference):** keep the Conclusion as-is ("the exosomatized organ") and tighten Ch II §A so the chapter names the aspect it is later summarized by. Insert the term at the natural anchor in §A where the prosthesis/exteriorization is named, e.g. at line 152:
  - `old_string`: `"The prosthesis is not a mere extension of the human body; it is the constitution of this body qua 'human'" (Stiegler, 1998: 152–153).`
  - `new_string`: `"The prosthesis is not a mere extension of the human body; it is the constitution of this body qua 'human'" (Stiegler, 1998: 152–153). This exteriorization — the placing of an organ outside the body, which the thesis will hereafter call exosomatization (Chapter V) — is the first aspect of artificiality.`
  - Then make Introduction §F (line 73) consistent with "the exosomatized organ" phrasing if a single term is wanted:
    - `old_string`: `technology as the exteriorization, or exosomatization, of human organs and memory`
    - `new_string`: `the exosomatized organ — the exteriorization of human organs and memory`
  - And correct the false quotation in footnote `[^v1-stiegler]` (see 1.2 above).
- **Decision needed from author:** whether to standardize on **"exosomatized"** everywhere (recommended; matches Conclusion and the author's stated preference and the Ch V usage) or keep "exteriorization/exosomatization" as a paired gloss in Intro §F. Either way, **Ch II §A must contain the term** by which the Conclusion summarizes it.

---

## Category 5 — Ch VI §D internal duplication / overlap

### 5.1 [POLISH] Adaptational-arrow reversal stated twice in close succession
- **Locations:** line 639 (*"the adaptational arrow reverses: through the first two types the subject fitted itself to the environment; now the subject makes the environment fit it…"*) and the opening of line 643 (*"The reversal of the adaptational arrow breaks the two alignments that held through Type 2…"*).
- **Assessment:** Mild. Line 643 re-invokes the reversal as a topic sentence to launch the "two breaks," so it functions as a deliberate callback rather than dead repetition. Optional tightening only:
  - `old_string`: `The reversal of the adaptational arrow breaks the two alignments that held through Type 2, and a single engine drives both breaks.`
  - `new_string`: `That reversal breaks the two alignments that held through Type 2, and a single engine drives both breaks.`
- **Overlap with §C and §E — NOT redundant (by design):** §D's radical-monopoly (L645, "still domain-bounded; their unification under one architecture is Type 4's escalation") and acceleration-spiral (L645, "begins its spiral here") are *explicitly* forward-linked to §E's escalations (L664 "made total", L658 "intensifies past any brake"). §D's inequality paragraph (L647) is explicitly distinguished from §C's via "along the distinction §VI.C drew." The two-faces/liberation note (L641) is explicitly handed to §E ("§VI.E follows that liberation to its limit"). These are the chapter's accumulation structure, not duplication. **No fix.**

---

## Category 6 — English-first CJK rule

Rule: English term first → "(原文, romanization)" at first use → bare English after. Overall strong compliance; coined terms (自足完成化, 自己完結化, 偽道, 意のまま…) are introduced English-first with romanization. Two ordering slips at the first *joint* appearance of the metaverse triad.

### 6.1 [POLISH] 偽道 / 偽理 / 偽相 appear as bare CJK before their English gloss (Ch V §A)
- **Location (line 417):** *"The metaverse, when it arrives, will have its own three layers, marked with the prefix 偽 — **偽道 / 偽理 / 偽相** — where 偽 carries its old Xunzi sense of the humanly-made (人為), not 'fake.'"*
- **Problem:** This is the **first appearance of 偽理 and 偽相** in the thesis, and they are presented as bare characters; their English senses arrive only in the table that follows (Table 5-1, L425). 偽道 was glossed earlier ("forged Dao", L173), but 偽理/偽相 are introduced CJK-first here. Mild English-first violation.
- **Fix (front-load the gloss at first joint use):**
  - `old_string`: `marked with the prefix 偽 — 偽道 / 偽理 / 偽相 — where 偽 carries its old Xunzi sense of the humanly-made (人為), not "fake."`
  - `new_string`: `marked with the prefix for the made (偽) — the forged Dao, the forged structures, and the forged phenomena (偽道 / 偽理 / 偽相) — where 偽 carries its old Xunzi sense of the humanly-made (人為), not "fake."`
- **Same pattern, same fix recommended at line 589 (Ch VI §A):** *"carries the same three strata under the prefix 偽 — 偽道, 偽理, 偽相 — where 偽 bears its Xunzian sense of the humanly-made (人為)…"* — by Ch VI the terms are established, so this is lower priority, but for strict compliance add "(the forged Dao, structures, and phenomena)" before the characters.

### 6.2 [POLISH] 偽境 introduced with English adjacent but not strictly preceding (Table 5-1)
- **Location (line 425, Table 5-1 row label):** `| 偽境 · metaverse | …` — the row leads with the characters, English after the middot.
- **Assessment:** Table row-labels pair 宇宙·universe / 世界·world / 偽境·metaverse symmetrically; CJK-first here is a table-layout convention and the running-body first use of 偽境 (line 486, "the thesis names this made background environment 偽境 — the humanly-made (偽 = 人為) environment…") is English-led in sense. Borderline; if strict English-first is wanted in the table, reorder to `| metaverse · 偽境 |` (and likewise universe/world rows for consistency). Low priority — flagged for completeness.

### Verified-compliant CJK first uses (no action)
- 道/理/相 (L131), 自足完成化 (L210 table / L214 body, both glossed), 自己完結化 (L366), 意のまま (L343), 無限の生/有限の生 (L364), 自己ペット化 (L228/235), 君子不器·器·器化·修身 (L229, L236), 元宇宙 (L26 Intro, glossed), 緣起/無我/有所待 (L46), 天人合一/wu wei/無為 (L263), 切断/亀裂 family (L261), 思念体 (L374, L660). All English-first with romanization at first use.

---

## Category 7 — Heading / numbering sanity

**Clean.** Confirmed from the heading scan:
- Introduction (unnumbered) ✓; Chapters **I–VI** numbered, no gap ✓; Conclusion (unnumbered) ✓; References (unnumbered) ✓.
- Section letters sequential, no skips: Intro A–F; Ch I A–E; Ch II A–E; Ch III A–H; Ch IV A–D (with §IV.C sub-sections (A)–(H), sequential); Ch V A–I; Ch VI A–H; Conclusion A–G.
- No duplicated section letters; no `###` sub-sections out of order.

---

## Items the author should confirm (not auto-fixable)
1. **Table 2-1 decision (Cat 2):** renumber-down (recommended) vs. confirm a deliberately removed Table 2-1.
2. **Exosomatized standardization (Cat 4):** confirm "the exosomatized organ" as the single term across Intro §F / Ch II §A / Conclusion §A.
3. Whether memory's "supremacy of the subject" framing (Cat 3.1) should be honored anywhere — the *manuscript* uses "sovereignty"; recommended fix aligns to the manuscript.
