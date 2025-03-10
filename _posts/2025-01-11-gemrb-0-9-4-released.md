---
title: GemRB 0.9.4 released! (Izbelah edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

It brings two exciting major developments. First, for the first time ever, one is now able to play Icewind Dale 2 from start to end. That marks the last original game to reach this status. 
BG2EE support has been experimental and is not yet ready for wide use, but as of this release it is now playable enough to welcome testers and power users to bug hunting adventures (manually set `GameType` to bg2ee).
Besides that the release features several improvements to pathfinding, audio and ease-of-use for other projects.

Sources and packages are available. You can get them from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.9.4 (2025-01-11):
    New features:
      - iwd2 is now fully completable!
      - iwd2 turn undead, hybrid damage types, Heal Party on Rest
      - traditional bg2ee GUI is usable and the shaman class works
      - option to highlight learnable scrolls, draw empty containers gray
      - option to more easily use GemRB as a library
      - animfps.2da to set per-animation drawing speed
    
    Improved features:
      - text encoding, drawing speed, drawing, (stereo) audio, GUI internals
      - feats, animations
      - scripting, projectiles, effects, movement speed, pathfinding
      - bugfixes


**Thanks to everyone that contributed** their time, including:
Ashvith10, Bubb13, DarthRevan501st, HJ000001, MarcelHB, Mariihmp, Mingun, Peppersawce, Kassandra Pucher, arosenow, bhbuehler, burner1024, duy64, elde-n, Jan Palus, Jaka Kranjc,
Sergej Alikov, rfht, Rodrigo Santellan, Tim Lancina, Tom Kidd.

**Notes to packagers:**
- The unmaintained SDL1 backend will be removed in next release.
- A new `UseAsLibrary` key has been added to the config.
- A new bit was added to the `GUIEnhancements` bit field, so if you ship your own configs, an update to the new higher default value is encouraged.

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.
