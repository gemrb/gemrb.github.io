---
layout: post
title:  "GemRB 0.7.1 released!"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new (minor) release.

It has been a good half year since the last release, but we were not slacking off the whole
time. While the android SDL2 situation is still unfavourable, the engine continues to mature.
This time much of the effort was spent in adding missing iwd2 functionality like feats and
subtle rule differences. Besides the usual cohort of bugfixes, this release also brings
automatic logging to a GemRB.log file (under GamePath, CachePath, /tmp or none in that order)
and a VLC plugin for the few unlucky players with game video in non-MVE/BIK format.

Currently only the sources are available. You can get them from http://gemrb.org

Full changelog digest:

**GemRB V0.7.1 (2012-07-15):**
New features:
- almost all iwd2 feats
- encumbrance penalties in movement
- configurable xp/damage adjustments per difficulty level
- support for logging to file directly
- iwd2 armor penalty and critical hit multiplier
- beginnings of iwd2 spellbook support
- vlc plugin for extra video formats

Improved features:
- (iwd2) effects, actions, combat, action bar, infravision
- sdl renderer and an initial sdl2 port
- config loading, logging
- cocoa wrapper and mac build, cursor handling, touch input
- bugfixes
