---
layout: post
title:  "GemRB 0.8.6 released! (Revenge of the squirrels edition)"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

Two years in the making, this release is as full of fixes and polishing as Tiax is of himself. 
The most noticeable changes are for BG1 players, since it lacked more audio mechanics than any other game,
but all the rest received ample attention as well. Modding is now also easier, but you'll have to wait for
the next WeiDU release to see the benefits. The pathfinder upgrade was delayed, but you can expect a
state-of-the-art version in the next release, which will focus on finishing the GUI handling rewrite.
You can [help us get there faster](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md)!

You can generally get GemRB from [here](http://gemrb.org).

Full changelog digest:

    GemRB v0.8.6 (2019-11-24):
      New features:
        - more audio, especially in bg1 and pst
        - sndchann.2da support
        - using bags in stores, NPC breaking points, worldmap travel in pst

      Improved features:
        - better megamod and detectable spells compatibility
        - iwd2 and pst levelup, infopoints, gui feedback, dualclassing, ranges
        - verbal constants, (tobex) opcodes, falling, paperdolls, projectiles
        - pst area animations, multipalette animations
        - bugfixes

Thanks to everyone that contributed their time and wit, including:

Askmewho, Beren Minor, bholland, Brad Allred, Bubb, caillean7, countbuggula, cygarniczka, Dan Church, edheldil,
Eitan Adler, fizzet, fogobogo, FrElvire, ifyGecko, Ilya Zhuravlev, Jaka Kranjc, Jérôme Duval, Kevin Michael Frick,
khelban12, Lyle Hanson, Manuel Alfayate Corchete, MarcelHB, MesmericOrb, Mingun, miqlas, nerd-rage, Nicolás Clotta,
skellytz, sten13, Tomsod, tomudo, Wisp and Yorick Hardy.

*If anyone is wondering what's up with the release name: squirrels didn't land any hits before, due to the way
a detail in our combat code was implemented. Now the immortal squirrel of Easthaven can have its revenge.*
