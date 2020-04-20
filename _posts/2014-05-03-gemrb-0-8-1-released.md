---
title:  "GemRB 0.8.1 released! (Fork Me edition)"
author: Jaka Kranjc
---

GemRB 0.8.1 released!

The GemRB team is proud to announce a new release.

After a slow year, this release brings several improvements to iwd2 and pst compatibility (thanks chiv!)
and the usual assortment of fixes and small features all around the place.

More notably, two experimental OpenGL renderers are now included thanks to Beholder.
While they are not ready for prime time yet, they are already usable. Some extra changes need to happen
first for them to offer a comparably lower resource footprint, but that work is already underway. Until
then, the plugin will remain **disabled by default on all platforms**. Building GemRB from source is required
for any brave souls that would like to try it.

Currently only the sources are available. Get them here:
https://sourceforge.net/projects/gemrb/files/GemRB%20Sources/GemRB%200.8.1%20Sources/

Full changelog digest:
New features:
- experimental OpenGL and OpenGL ES renderers
- spontaneous casting (iwd2) and "cast healing spells on rest"
- iwd2 spawns, saving throws
- utf-8 converter for dialog.tlk to be able to use any (cjk) font

Improved features:
- spawngroups, autopause, bg2 demo compatibility
- inventory, pst guiscripts, pst usability
- animations, scripting, dialog, touch input, mac gui
- bugfixes
