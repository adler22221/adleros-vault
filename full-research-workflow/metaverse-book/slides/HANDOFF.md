# Handoff: 7/30 presentation deck → Windows Claude Code

## What this is
A 27-slide Japanese-language deck for a talk responding to Prof. Uegaki Takahide
at a 2026-07-30 academic session. Built on a headless Linux box ("Cubi") with
**no display, no LibreOffice/soffice, no PowerPoint, and no font rendering** —
so it was built entirely blind, verified only at the XML level (correct fonts
tagged, no clipped text detectable, all cells populated), never actually seen.
**That's almost certainly why the design is "ok but not very good" — it has
never been rendered and looked at by anyone, human or AI.**

## Files in this folder
- `260730_response_to_uegaki.pptx` — the compiled deck, 27 slides, 16:9, Yu Gothic
- `build_0730.py` — the generator script (python-pptx). **This is the real source.**
- `jp_slide_kit.py` — shared helper module (fonts, tables, shapes, color palette)
  imported by `build_0730.py`. Ported from an earlier working deck
  (`2026JASAconf/build/build_slides_v3.py`), so its low-level primitives
  (`cjk()`, `tb()`, `table()`, `shape()`) are already proven to render Japanese
  correctly in real PowerPoint — don't rewrite these from scratch, extend them.
- `gemini-prompts_0730.md` — prompts for 5 illustrations (organs loop,
  stele-vs-server, squeeze-types stack, etc.) that were never generated because
  this box can't call image-gen or preview results either. Still needed.

## The actual instruction to give Windows Claude Code
**Don't hand-edit the .pptx and don't just "make it prettier."** Two things it can
do that this box couldn't, in order:

1. **Open the .pptx in real PowerPoint and actually look at it.** Check for
   text overflow, cramped tables, weak visual hierarchy, awkward whitespace,
   inconsistent slide rhythm — the stuff that's invisible from XML.
2. **Edit `build_0730.py` (and `jp_slide_kit.py` if a primitive itself is weak),
   then regenerate**, rather than patching the output file directly — so the
   deck stays reproducible and the next round of edits doesn't fight stale
   manual tweaks.

Then, only for the 5 illustration slots: run the prompts in `gemini-prompts_0730.md`
through Gemini, drop the images into the placeholder frames already sized and
positioned in the deck, and add the Japanese labels natively in PowerPoint
(the prompts deliberately generate text-free images — baking CJK into an image
is the wrong move; Gemini's script-accuracy for Japanese is not good enough
for terms this precise).

## One thing worth telling it explicitly
This box verified "does not visibly fail" (right font tags, no empty notes,
no baked-in images) — not "looks good." Those are different bars. Ask it to
clear the second one.
