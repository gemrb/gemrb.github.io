---
layout: post
title:  "GemRB 0.2.3 released"
author: Jarda Benkovsky
---

Hi all,

your long waiting is over, a new release of GemRB is here! 
It's not as Stable-And-Bugfree (tm) as we have hoped, but at least it's done. 
Please read release notes and a thread about 0.2.3 on our forums before reporting problems.

Highlights of this release:

New features:
- GUI for most of the games, especially interactive Inventory and Spellbook
- Map and WorldMap
- Load screen interstitials with progress bar
- Spell and item cache to speed up object management
- Added gamescript actions/triggers
- Selection of spells during character generation
- First attempt on effects code
- First attempt on Fog-Of-War
- Tooltips
- Overhead text
- Ambient sounds
- Volume control
- Manual page gemrb(1)
- Documentation for GemRB Python API and our custom override files

Improved features:
- Character generation
- GUI
- Build infrastructure on Linux and Un*x systems
- Progress towards portability to 64 bit and big endian machines
- Many bugfixes and new bugs as well ;-)
- Shortened version numbers
- Simplified user configuration, game specific settings are now
in gemrb/override dir

Enjoy,
Edheldil, the delayed Santa 
