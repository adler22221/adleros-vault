# Fact-checking protocol (manuscript-wide)
> Established 2026-06-08 after a post-mortem on missed Ch II errors (altered Stiegler quote, Eric→Daniel Ross, Brague 2004→2003, 偽 會意 self-contradiction, whale-song→Allen 2022). Supersedes the ad-hoc Pass-4 method. Reusable for future submissions.

## 0. Why the old method failed (the gaps this protocol closes)
1. **Checklist-driven, not text-driven** — verified items on an inherited list (scaffold `[VERIFY]` flags, prior notes), so off-list claims (the altered Stiegler quote) were never examined.
2. **Inherited the scaffold's blind spots** — its *confident, unflagged* assertions were treated as settled; they are in fact the highest risk.
3. **Single-axis** — only "does the source support this?", missing attribution / internal-consistency / self-contradiction / paraphrase-in-quotes.
4. **Reconciliation auto-fixed instead of flagging** — the references rebuild took the in-text as truth, hiding year/name mismatches.
5. **"Scaffold-clean" conflated with "verified"; sampled not swept; adversarial energy aimed at verdicts, not the text.**
**Through-line:** the manuscript text itself was never the object of an exhaustive, multi-axis, adversarial, source-grounded sweep.

## 1. What is a verifiable claim — the eight criteria classes
Every chapter is swept for ALL eight; each item is extracted **from the manuscript text**, never from a prior list.

1. **Quotation fidelity** — every `"…"` attributed to a source: word-for-word vs source (only marked `[…]` elisions; note "emphasis added"). Catch altered quotes, **paraphrase-presented-as-quotation**, meaning-distorting ellipses.
2. **Citation locus** — every `(Author, Year: page)`: claim/quote is on that page in the **edition actually held**; year + edition/pagination correct.
3. **Attribution / provenance** — right person & work; who *coined* a term; primary vs "as cited in"; translator/editor names.
4. **Internal consistency** — in-text↔references **both ways** (flag discrepancies, never auto-fix); one rendering per term (glossary lock); **no self-contradiction**; cross-chapter agreement; numbers/dates consistent throughout.
5. **Empirical / factual claims** — scope = **(a) every number, date, magnitude, count; (b) every contested or examiner-attackable claim (馬/米/劉 lens); (c) every load-bearing claim the argument rests on.** Sub-types: scientific/biological · historical · current/post-cutoff (date-stamp + hedge) · quantitative · field-characterizations (not a strawman).
6. **Interpretive fidelity** — does the thesis represent a thinker's *position* accurately (beyond the quote)? Run **T0 (read the source) BEFORE characterizing/attacking** a thinker.
7. **Self-citation** — Yang 2024/2026 / 交換様式: what was argued where; senior-work direction; term-introduction dates (e.g. 思念体=2022 term, tulpa=2024 rendering).
8. **Translation / foreign-term** — CJK/Greek/German rendering + original script + gloss all correct.

## 2. How to run it — operating rules
1. **Text-driven extraction.** Parse every quotation mark, `(Author, Year)`, number/date, "X argues/holds", and named position straight from the manuscript. Flag-status is irrelevant to selection.
2. **Unflagged-confident = top priority** (invert the scaffold's risk ordering).
3. **Multi-axis per item** — run all applicable classes on each citation, not just source-support.
4. **Reconciliation flags, never auto-fixes** — a year/name mismatch is a finding for the author, not a silent merge.
5. **Source-grounded, tiered, NEVER from memory** — resolve against: held primary text (**NLM**) → **Zotero** (editions/metadata) → **web** (empirical/current) → **needs-author** if not held. Memory is never evidence.
6. **Adversarial on the text** — a second pass whose job is to *find an error* in each claim, defaulting to "suspect" when unconfirmed.
7. **Provenance trail + hard gate** — per claim: `claim → source checked → verbatim excerpt → verdict → confidence`. Nothing marked "verified" without an excerpt.

## 3. Verdicts & gate (author-confirmed 2026-06-08)
- Verdicts: `verbatim/confirmed` · `corrected` (give the fix) · `altered` · `fabricated/not-found` · `paraphrase-in-quotes` · `contested-hedge` · `claim-confirmed·page-needs-author` · `needs-author`.
- **Gate = pragmatic:** if the quote/claim is verbatim-confirmed but only the exact page/edition is unconfirmable against a held source, mark **"claim-confirmed · page-needs-author"** (one combined flag) — do NOT withhold the whole item.
- **Confidence tier on every item:** `NLM-verified` / `Zotero-verified` / `web-verified` / `author-must-confirm`. The author triages by tier.
- No chapter clears the gate with an open "verified-from-memory" item.

## 4. Execution shape (per chapter)
**extract** (deterministic grep of `"…"`, `(Author, Year)`, digits/dates + agent for positions/empirical) → **classify** into the 8 classes → **verify** each against its tier source (NLM/Zotero/web) → **adversarial refute** (find-the-error on the text) → **ledger** (provenance table) → **author-gate** the discrepancies. One workflow per author-notebook (Class 1–3/6/8) + one per empirical sub-type (Class 5) + a deterministic reconciliation script (Class 4).

## 5. Standing additions to the workflow
- **Cross-reference any `30Drafts/_audits/` file** for the chapter first (don't re-discover known errors).
- Output → `fact-check-log.md` (running, per-claim) + discrepancies → `review-queue.md`.
