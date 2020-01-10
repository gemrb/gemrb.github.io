---
layout: post
title:  "GemRB V0.4.0 is out"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release. 
Development pace has skyrocketed and a few important milestones have been reached. 
You can now level up in bg2 (dual classing included), area-of-effect spells are now drawn, 
ranged attacking works ... Add a bunch of bugfixes and polishing and you get this great release.

Currently only the sources are available.

New features:
- level up support in bg2
- basic party reordering
- bashing of containers and doors
- persistent area effects (cloudkill, stinking cloud, web, etc.)
- item amount window for stack splitting (shift+click or doubleclick)
- depletion of item charges
- opcodes: disable spellcasting, cutscene2 (pocketplane travel), knock,
clear air, polymorph, disable button
- dynamic scrollbar creation (display of more than 10 kits, 24 spells)
- portrait effect icons
- item ability selection
- character customization

Improved features:
- fog of war
- party reformation
- iwd and how guiscripts have been merged
- traps
- pst dialogs
- regeneration, hp bonuses, healing
- animations and projectiles
- rewritten MVE player
- ranged combat
- various guiscripts
- bugfixes

Applied patches:
- #2770564 Whiteclone (pst options window bug)
- numerous patches from mattinm finishing the level up support
- a few patches from ape fixing and extending iwd
- #2579743 jbmetz added RPM spec files
