---
title: GemRB 0.9.2 released! (Dragon's horde edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new major release.

It brings in many improvements for Planescape: Torment, configurable
AI speed, improved performance and others. Notably GemRB now also
supports PVR(Z) based formats, making content creation easier, most new 
opcodes/actions/triggers and together with some infrastructural changes,
BG2EE games can now be loaded (still not playable though!).

Sources and packages are available. You can get them from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.9.2 (2023-07-08):
      New features:
        - PVR(Z), BAM2, MOS2 and TIS2 support
        - support for higher AI speeds ("FPS") and VSync
        - support for EE-style saves, TLK locations and many more tables
        - PST's floating text and personalized pc comments
        - optional smooth fog of war on SDL >= 2.0.18
        - 3e-style sneak attack and crippling strike from HoW/iwdee
        - Anbernic device support

      Improved features:
        - PST effect durations
        - performance, pathfinding, formations
        - combat, opcodes, EE compat, hp handling, demo
        - bugfixes

Thanks to everyone that contributed their time, including:


(**Notes to packagers:**)
- optional `CapFPS`, `GameLanguagePath` and `GameMoviesPath` keys have been added to the sample configs
- an upgrade to C++14 standard will occur after this release

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.
