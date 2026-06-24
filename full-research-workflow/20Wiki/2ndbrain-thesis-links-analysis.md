---
aliases: [2ndbrain Links, Thesis Hub Links Analysis]
type: concept
project: master-thesis
status: ai-draft
summary: "Analysis of all 2ndbrain notes that link to the thesis project hub and metaverse concept files. Primary value: 4 @citekey reference entries already in thesis-sources. Secondary: author process notes pointing to thesis sections."
---

# 2ndbrain Thesis Links Analysis

> **Purpose:** Both target files are sparse hubs — the value is entirely in what links *to* them, not in the files themselves.
> **Reading rule (Tier 2 files):** These are the author's working notes. Content may be outdated or context-mixed. Use as *section pointers only* — do not accept as current argument. Author verifies before using.

**Target files analysed:**
- [[Between the Universe and the Metaverse]] — contains only two LibraryThing book references (see §1)
- [[metaverse]] — single-line stub, essentially empty

---

## §1 Books Referenced in the Hub File

The hub file itself contains only two LibraryThing references. Both PDFs exist locally; neither is yet in Zotero `thesis-sources`.

| Book                   | Author                | PDF location                                                                                                 | NLM status                          | Recommendation                                                                                                                                     |
| ---------------------- | --------------------- | ------------------------------------------------------------------------------------------------------------ | ----------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------------- |
| *拡張される身体 — 自己の再定義のために* | 酒井紀幸 (Sakai Noriyuki) | `P:\books(1)\Knowledge, Science, Technology, Rationality, & Intellectuals\拡張される身体 _ 自己の再定義のために 酒井 紀幸ocr.pdf` | ✅ In `日本の科学技術論考` (UUID: `dda533bd`) | **Defer.** Not in thesis-sources or committee-reviewed versions. If D2 gap requires it: add to Zotero → tag `nlm:pending` → run `zotero_to_nlm.py` |
| *言葉と心 — 全体論からの挑戦*      | 中山康雄 (Nakayama Yasuo) | `P:\books(1)\[source] scanbee\60642ADLER YANG様\言葉と心 _ 全体論からの挑戦 中山 康雄 .pdf`                                   | ❓ Not confirmed in any NLM notebook | **Defer.** Same rationale as above.                                                                                                                |

---

## §2 Reference Database Entries (@citekey files) — Primary Actionable Output

These four `@citekey.md` files in `2ndbrain/800_ReferenceDatabase/` contain thesis-linked annotations and are **already in Zotero `thesis-sources`**. They represent previously completed literature reviews that should be reintegrated.

### Zotero / NLM Sync Checklist

| Citekey                                | Title                                                                                  | Authors          | Year | In `thesis-sources`? | In NLM A-Sources (`c68ca15e`)? | `10Literature/` note? |
| -------------------------------------- | -------------------------------------------------------------------------------------- | ---------------- | ---- | -------------------- | ------------------------------ | --------------------- |
| `collierGovernmentEmergency...`        | *The Government of Emergency: Vital Systems, Expertise, and the Politics of Security*  | Collier & Lakoff | 2021 | ✅                    | Check                          | Check                 |
| `duranteTechnologyOntologyVirtual2022` | *Technology and the Ontology of the Virtual*                                           | Massimo Durante  | 2022 | ✅                    | Check                          | Check                 |
| `wattsPhilosophyHeidegger2011`         | *The Philosophy of Heidegger*                                                          | Michael Watts    | 2011 | ✅                    | Check                          | Check                 |
| `kellyInevitableUnderstanding122016`   | *The Inevitable: Understanding the 12 Technological Forces That Will Shape Our Future* | Kevin Kelly      | 2016 | ✅                    | Check                          | Check                 |

### Annotation summary (from @citekey files — for author's reference when deciding on `agent compile`)

**@collier (Collier & Lakoff 2021)**
- Linked to thesis at: fragility of artificiality + controllability dependence; cascading failures through complex networks; interconnected technologies and vulnerability
- Thesis notes in file: 3 explicit `cite in [[Between the Universe and the Metaverse]]` markers
- Potential sections: §IV (causal efficacy of neo-artificiality), §VI (squeeze — fragility axis)

**@durante (Durante 2022)**
- Linked to thesis at: metaverse as a historical process continuous with artificial things; distinct domain analogous to but not identical with the universe; artificial becoming automatic then autonomous; four-quadrant ontology (natural-material / natural-nonmaterial / artificial-material / artificial-nonmaterial)
- Thesis notes in file: 6 explicit thesis-referencing footnotes, including the four-quadrant claim ("once artificial-material and artificial-nonmaterial also become independent from humans, we are left in the abyss/nowhere in between")
- Potential sections: §I-1/I-2 (universe/metaverse distinction), §III/§IV (autonomy and artificiality), §VI (squeeze — ontological abyss framing)

**@watts (Watts 2011 — Heidegger)**
- Linked to thesis at: Dasein as world-being / extrasomatized organs; 自己家畜化論 (self-domestication theory, Obara) — habitat imposes evolutionary pressure; Heidegger's "world-being" parallel to extrasomatization; controllability dependence; rationality dependence
- Thesis notes in file: 9 explicit thesis-referencing footnotes
- Potential sections: §II (world concept), §III (technosphere, Heidegger angle), §IV (causal: extrasomatization ↔ evolutionary pressure)

**@kelly (Kelly 2016)**
- Linked to thesis at: ontological status of technological artifacts; distinct physics of artificial systems vs natural systems; metaverses as releasing flux already present in reality; distributed cognition parallel to universe
- Thesis notes in file: 6 thesis-referencing footnotes
- Potential sections: §I-2 (universe/metaverse analogy), §VI (squeeze examples — technological inevitability)

> **Next step for these 4:** Run `agent compile [citekey]` for each to generate a structured `10Literature/` note, OR use Zotero Integration plugin import. Verify NLM A-Sources sync status before VERIFY sweep (Phase D.5).

---

## §3 Author Process Notes — Section Relevance Pointers

> ⚠️ These files contain the author's working notes from 2022–2024. Content may be outdated, context-mixed, or superseded by current drafts. Use as **pointers to which sections to cross-check**, not as content sources. Author reads the note, judges whether the idea still holds, then writes in own voice.

| File                                               | Date     | Where in 2ndbrain                           | Sections to cross-check                                                                                               |
| -------------------------------------------------- | -------- | ------------------------------------------- | --------------------------------------------------------------------------------------------------------------------- |
| [[2024-12-06 metverse thesis structure revision]] | Dec 2024 | `009_tasks/`                                | §I (technology/virtuality framing), §III (Stiegler), §IV (causal chain), §VI (squeeze examples, scenarios taxonomy)   |
| [[2024-10-27 唯研大会：メタバース発表]] | Oct 2024 | `009_tasks/`                                | §III (Stiegler/Leroi-Gourhan exosomatization), §IV (Baudrillard critique), §I (path-dependency problem)               |
| [[2024-11-30 上柿崇英ミーティング]] | Nov 2024 | `009_tasks/`                                | D5 (methodology — singularity trajectory), D6 (disciplinary positioning), §VI (counter-argument: metaverse ↔ freedom) |
| [[202209260605 元宇哲學研究m2]] | Sep 2022 | `400_courses/Soochow University/米建國 元宇宙哲學/` | §I foundations (Mi's own universe-vs-metaverse framing from his seminar), D5 (Mi's epistemological priorities)        |
| [[2024-06-02 thoughts on Metaverse thesis]] | Jun 2024 | `009_tasks/`                                | §I-2 (early framing of universe/world tension — may be superseded)                                                    |

---

## §4 Omitted / Low-Value Entries

Files confirmed to link to the target files but with no usable content for the current revision:

- [[2024-07-30 metaverse proposal hearing]] — content already captured in [[ThesisRevision/reviewers-comments]] and integrated into [[revision-tracker-v3]]
- [[202203191259 上柿崇英から配分依存についてのメール]] — primarily about the *allocation-dependence* project; recontextualize only if crossover is confirmed when read
- [[202302141447 上柿崇英先生とのお会い]] — single-line note ("transcend universalism" + metaverse), minor
- [[202209121406 元宇宙哲學研究m1]] — Mi's course logistics/intro, not substantive
- [[上柿崇英]] — author stub (`#authors [[総合人間学]]` only)
- Various daily notes and task logs — mention the thesis contextually but have no extractable content

---

## §5 Files Not Yet Read — For Future `agent compile` Pass

The Explore agent identified additional files that link to the target files but were not fully read in this session. These should be checked if a more thorough D2/D6 audit is needed:

- Task and reflection logs from 2022–2024 in `009_tasks/` and `000_daily/` (multiple entries mentioning the thesis)
- Additional meeting notes not retrieved in this session
- Any further `@citekey` files in `800_ReferenceDatabase/` beyond the confirmed four

> Use `Grep` on `C:\Users\adler-standard\Documents\Obsidian\2ndbrain\` for `"Between the Universe and the Metaverse"` to get a complete count before any future audit.

---

*Generated 2026-05-06 · status: ai-draft · agent analysis only — author verification required before acting on any content claims*
