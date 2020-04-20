---
title:  "GemRB 0.6.4 released!"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new (minor) release.

Since the last release was several months ago, this one brings both a bunch of bugfixes and some new
noteworthy features. A lot of work has gone into unhardcoding the Planescape projectiles and the Modron
maze, but there are still some big roadblocks on the way to make PST work properly. Then there was an
assortment of improvements to spellcasting, implementing various casting failures and wild magic.
There were also a few usability improvements - the game type can now be autodetected and the free BG2
demo can be used to try GemRB without installing any of the full games. This is also the first release
with the Android port included.

Full changelog digest:

**GemRB V0.6.4 (2011-03-27):**
New features:
- PST maze and (un)hardcoded projectiles
- full wild, dead, miscast and vocal magic support
- subspell selection (spell immunity, nahal's reckless dweomer...)
- Autodetect GameType if it is set to 'auto' or commented out
- compatibility with the bg2 demo
- VVC lightspot support

Improved features:
- travel regions, projectiles, dialog startup
- bink player has no/less artifacts, good sound quality
- combat, effects, actions, triggers, banters
- bugfixes

Applied patches:
- a set of patches for Android support from Beholder
- arm compilation fixes by ShadowJack
- patch from Thomas Klausner fixing building with libpng 1.5
- patch by Hana Dusíková to support static linking on mac

