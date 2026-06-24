---
type: draft
project: master-thesis
status: ai-draft
target: thesis
summary: "Front-matter for the print baseline: cover (from manuscript), EN abstract draft, ZH abstract draft. EN/ZH abstracts are AI-drafts — author review + CJK verification required."
source-notes: []
---

# Front matter for the print baseline
> Phase C input. Cover is taken verbatim from the manuscript head. The **abstracts are AI drafts** (the thesis had none) — review the English; **verify the Chinese**. Both abstract pages carry the 校徽 watermark and a supervisor-signature line (physical signature). See [[master-thesis]].

---

## 1. COVER (title page — no watermark, no page number)
Centered, stacked. Two blocks per the Soochow template (`thesis-formatting/master-cover.doc`). The English block is already in the manuscript; the Chinese block needs the author's **Chinese name** and a **Chinese title** (placeholders below).

**Chinese block (top):**
```
東吳大學哲學系
碩士論文

宇宙與偽境之間：在夾縫中求生   ← [DRAFT TITLE — author confirm Chinese title & "squeeze" rendering]

指導教授：米建國
研究生：楊＿＿（Adler Yang）   ← [author: supply Chinese name]
中華民國一一五年六月
```
**English block (bottom) — from manuscript:**
```
Department of Philosophy
Soochow University
Master's Thesis

Between the Universe and the Metaverse:
Surviving the Squeeze in Between

Supervisor: Chienkuo Mi
Student: Adler Yang
6 / 2026
```

---

## 2. ENGLISH ABSTRACT (watermark; 1–2 pp; supervisor-signature line)
> AI draft in the author's register, distilled from the Introduction + Conclusion §A. Review/adjust.

**Abstract**

The word "metaverse" names more than its current devices can show. Defined by today's headsets and virtual worlds, it invites three errors: a path-dependency on an accidental origin, a disciplinary reductionism, and an actualism that pins analysis to whatever has so far been built. Against these, this thesis proposes a dispositional method — to characterize the metaverse not by its present specimens but by the dispositions of the conditions from which any such environment must arise.

The argument proceeds in two movements joined at their root. A world, the thesis holds, is not a worldview but a built habitat — an adaptational operating system a human collectivity raises within the universe and lives inside of, buffered, though never insulated, from the given. Such a world is made of artificiality: the exosomatized organ, the causally efficacious nonmaterial, and laws of its own that are irreducible to the universe's. The modern Western mode came to overspread other worlds by universalizing a single disposition, traceable to a material and an epistemic root and, beneath both, to the elevation of the sovereign subject. On the human side, that subject pursues a life-as-intended, reading whatever does not answer to its intention as a wrong to be discharged, until human life turns self-finishing. On the side of the apparatus, artificiality self-completes — acquiring the capacity to operate, maintain, and renew itself — until it stands up as a background environment around the world: the metaverse, a second given beside the universe.

The two engines converge as a squeeze. The human is pressed between two givens, the universe and the metaverse, as the world that once buffered it is hollowed from within. The threat this names lies beneath the familiar questions of governance, ownership, and liberty; what answers it is a turn from the flight from dependence toward the reorganization of dependence. Harmony, on this account, is nothing more mystical than the prevention of the squeeze.

**Keywords:** metaverse; the squeeze hypothesis; artificiality; universe / world / metaverse; the sovereign subject; philosophy of technology; critical realism; the self-finishing society

*Thesis Supervisor _______________  Date _______________*

---

## 3. CHINESE ABSTRACT (watermark; 1–2 pp; supervisor-signature line)
> ⚠️ **AI draft — the author MUST verify the Chinese** (academic register + the thesis's locked CJK terms: 宇宙/世界/偽境, 人為, 自足完成化, 自己完結化, 偽道). The "squeeze" rendering (擠壓 / 夾擊 / 夾縫) needs the author's settled term — I used 擠壓 / 夾縫 provisionally.

**摘要**

「偽境」（metaverse）一詞所指，遠多於其當前的裝置所能顯示者。若以今日的頭戴顯示器與虛擬世界來界定它，便會落入三種謬誤：對偶然起源的路徑依賴、學科上的化約論，以及將分析侷限於既已實現之物的「實在主義」。為對治之，本論文提出一種「傾向性」的方法——不以偽境當前的樣態來刻畫它，而以「任何此類環境得以興起的諸條件」之傾向來刻畫它。

論證循兩條在根部相連的線索展開。本論文主張：世界並非世界觀，而是一個被建造的棲所——一套「適應性作業系統」，由人類群體在宇宙之中築起並棲居其中，雖受其緩衝，卻從未與既與者（the given）隔絕。此等世界由「人為」（artificiality）所構成：外體化的器官、具因果效力的非物質者，以及不可化約為宇宙自身者的種種法則。近代西方的模式之所以遍覆其他世界，乃因其將單一的傾向普遍化；此傾向可溯及一個物質的根源與一個知識論的根源，並在二者之下，溯及「主體之至高化」。在人的一側，此主體追求「如意之生」（life-as-intended），將一切不順其意者讀為應予清償的虧欠，終致人之生命走向「自己完結化」。在裝置的一側，人為則「自足完成化」——取得自我運作、維持與更新之能——終至挺立為環繞世界的背景環境：偽境，宇宙之外的第二個既與者。

兩具引擎匯流為一種「擠壓」（squeeze）。人被夾於兩個既與者——宇宙與偽境——之間，而那曾緩衝著他的世界，則自內被掏空。此一威脅，潛伏於治理、所有權與自由等熟悉問題之下；而能回應它者，乃是一種轉向：從「逃離依賴」轉為「重組依賴」。據此，和諧並無任何神祕之處，不過就是對「擠壓」的預防。

**關鍵詞：** 偽境；擠壓假說；人為；宇宙／世界／偽境；至高主體；技術哲學；批判實在論；自己完結社會

*指導教授 _______________  中華民國 ___ 年 ___ 月 ___ 日*

---

## 4. TOC
Word-generated field (Contents heading + dotted leaders + page numbers), inserted after the abstracts, refreshed in Phase C5. Watermark on.

## Build notes (Phase C)
- Cover content currently sits at the TOP of the manuscript .md (lines 1–21, before `# Introduction`). For the .docx, that block becomes the **title page** (centered, no watermark); the body conversion should start at `# Introduction`. Easiest: convert the body (from `# Introduction`) via Pandoc, and assemble cover + abstracts + TOC as front matter in Word COM with a section break before the body (roman→arabic page numbering switch there).
- Title page: suppress the H1-chapter styling on the cover lines (they're plain centered text, not headings).
