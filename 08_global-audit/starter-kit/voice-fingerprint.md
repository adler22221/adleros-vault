---
tags: [global-audit, agent-out, blueprint]
date: 2026-07-05
---

# Skill: voice-fingerprint  (CN-03 · the unblocker)

**Why this is the keystone investment:** scaled outreach (CN-02) is your weakest area — only the 2016 documentary broke through — and you told me the blocker is that AI-generated public content isn't yet at acceptable *authorship quality* (clm-0039, member-checked). Everything downstream (blog, newsletter, SNS, the public-intellectual presence) is gated on solving voice. Solve voice once → CN-02 unblocks. This does **not** touch academic authorship (which stays fully human per your entropy-firewall) — it's for public-facing content only.

**Delegatable:** repurposing one approved argument into channel drafts + scoring them against your fingerprint. **Human-reserved:** the seed argument, final edit, and every publish. AI never writes in your voice without disclosure (clm-0027, clm-0039).

---

## Step 1 — Curate the voice corpus (front-loaded, ~1 sitting; this is the real work)
Pick **5–8 pieces of your OWN already-public writing** that sound most like you at your best (blog posts, the documentary's essays, public talks, SNS threads you were happy with). List their paths/links here:
```
1.
2.
...
```
**Screen out:** anything with T3/relational/family content (public corpus only), and anything ghost-edited or not-your-voice.

## Step 2 — Generate the style fingerprint
Say: *"Run voice-fingerprint on the corpus in this file."* It produces a **human-readable checklist** (not a black box) describing your voice: sentence rhythm, characteristic moves (e.g. symptom→structural-cause reframing — clm-0008), register per language (EN/ZH/JA differ), what you never do, recurring metaphors/frames. **You correct it** — this checklist is a canonical artifact you own and edit.

## Step 3 — First repurpose test
Take ONE seed argument you'd stand behind (a paragraph from the book, a claim from Modes of Dependencies). Say: *"Repurpose this seed into a blog piece and an SNS thread, then score each against my voice-fingerprint checklist."* Subagent chain: repurposer → voice-scorer → (later) translator. Output is staged in `06_agent-out/content/` for your edit + publish.

## Validation gate
**Did at least one draft clear your bar with only *light* edits?** If yes → voice is solved-enough; proceed to the translation pass + posting-staging hooks + the community digest (90-day step), and CN-02 unblocks. If no → the fingerprint checklist needs another correction round; that iteration IS the investment. Do not scale channels until a draft clears your bar — publishing off-voice content is worse than publishing nothing.

## Guardrails
- Public corpus only for the fingerprint — never train voice on journals/letters/T3.
- Trust-band review forever: even once voice is solved, spot-check every batch; never zero-review published content under your name.
- Disclosure: any AI-assisted public piece follows your existing AI-disclosure preflight.
