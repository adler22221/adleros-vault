---
created: 2021-01-24T17:21
author: human
---

#_GTD_0_inbox

My note: 

#excerpts
Author: 
Source: 
https://forum.obsidian.md/t/find-and-replace-links-across-all-files-in-a-vault/4218
Retrieved {January 24, 2021}

> After adjusting my graph-view to only bubble up heavily backlinked nodes, I've noticed that some nodes are large even though they're not very important.  Those are one-word notes (e.g. “deep work” or “job” or “ideas”) that I linked up because it was so easy[^1].  At this point, I care more about the quality of connections and decided to remove this type of noise from my vault.  After testing a few ways to “Find and replace” recursively across files and folders, and failing hard[^2], here's what'...

# Find and replace links across all files in a vault
After adjusting my graph-view [to only bubble up heavily backlinked nodes 32](https://forum.obsidian.md/t/how-i-tested-a-graph-view-idea-by-adjusting-my-local-install/4182), I've noticed that some nodes are large even though they're not very important.

Those are one-word notes (e.g. “deep work” or “job” or “ideas”) that I linked up because it was so easy\[^1\].

At this point, I care more about the quality of connections and decided to remove this type of noise from my vault.

After testing a few ways to “Find and replace” recursively across files and folders, and _failing hard_\[^2\], here's what's been working reliably without hiccups:

1.  Install Atom from [https://atom.io/ 62](https://atom.io/)
2.  Open vault directory in Atom
3.  Use “Find” -> “Find in Project”
4.  Find all “\[\[Deep Work\]\]” with “Deep Work”
5.  Replace all

And done.

So, if you find yourself in need of removing links, consider using Atom and make sure you have made a backup before just in case.

\[^1\]: Those notes happen to be heavily backlinked because I got excited and went on a linking spree using the backlinks plugin a few months ago. I've since stopped using the automatic backlinking feature.

\[^2\]: I tried a bunch of bash/zsh/perl hacks found online and I messed up my vault so hard that I needed to swallow my pride, eat some humble-cake and use a UI.
