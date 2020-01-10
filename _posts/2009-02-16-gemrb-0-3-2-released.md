---
layout: post
title:  "GemRB V0.3.2 is out"
author: Jaka Kranjc
---

A new GemRB release is out! Currently only the sources are available.

The release brings a bunch of smaller new features, a big guiscript change and a lot of polish.

**GemRB V0.3.2 (2009-02-16):**

New features:
- default cancel button, bound to the escape key
- tooltip animations and a shortcut (tab)
- wrapper python classes that simplified the GUIScripts
- trap detection, removal, triggering, xp, feedback, autopause
- modal effects
- proper xp award for dual- and multiclass actors
- double click (used in the map window)
- click-and-hold incrementing/decrementing
- accumulate kill statistics
- characters can move while the map is open
- sound on item equip
- arbitrary feat prerequisites in iwd2
- hard pause for all games (originally a ToB feature); triggered with 'h'
- extended night areas (originally a bg2 feature)

Improved features:
- walking animation timing
- formations (arbitrary sizes, rotation, cursor)
- ppc support (no more crashes)
- container/door/infopoint cursor and highlight handling
- various guiscripts
- cmake build system (now really works on *nix)
- magic item exclusion
- stores and bags
- fixed attack loop when target dies
- bugfixes

Applied patches:
- #2159734 Zefklop (Mouse activity during movies)
- #2243323 Zefklop (correct Openal cleanup)
- #2263333 Whiteclone (bg1 guiinv)
- #2380891 Amikrop (iwd1 guicommonwindows)
