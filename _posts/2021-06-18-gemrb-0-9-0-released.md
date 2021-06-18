---
title: GemRB 0.9.0 released! (A view to the future edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new major release.

Over six years in the making, growing in scope with time, the subviews branch
was a true monster. But the quest to lay it to rest has now been successfully
completed, among other things modernizing the GUI, drawing and input handling.
For most use cases, there is no need for the Widescreen mod any more
([see screenshot](https://gemrb.org/assets/img/screenshots/bg24hires.jpg)
or [video explainer](https://youtu.be/nn1v-yG4-lo)).

The SDL2 backend is now mature and default, OpenGL support is not experimental
any more, most benefiting Mac users. Additionally, in the last minutes between
the merge and this release, Python 3 support was added and our demo
received an ending.

If you don't believe that this is a big upgrade, consider just the changes from
the branch. It included 3527 commits, 668 changed files, and over 30,000
changed lines of code. That's about every fifth line!

You can get the new GemRB from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.9.0 (2021-06-18):
      New features:
        - basic resolution independence
        - python3 support
        - arbitrary window dragging support
        - improved debug console
        - subtitle support for BIK videos

      Improved features:
        - window management, drawing and input handling
        - performance: SDL2 video playback, general and text rendering
        - smoother movement animations, demo
        - bugfixes

Thanks to everyone that contributed their time and wit, including:

Bernd Schmidt, **Brad Allred** (main author), Diego J., fizzet, FrElvire, Jaka Kranjc,
Laurie Chilvers, m7600, MarcelHB, Northfear, Rodrigo Santellan.

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.

**Notes to packagers:**

Python 3 support has been added.

SDL2 is now the default backend and anyone still on SDL1 is encouraged to switch.

If you are packaging from git sources, not the archive, either run
`make fetch-demo-data` first or manually include the files.
These are (currently two) bigger assets kept in a separate repository.

Configuration notes ([details](https://gemrb.org/Manpage.html)):

  - key TooltipDelay was deprecated (was unused, there is an ingame option)
  - key ScriptDebugMode was renamed to DebugMode and received more values
  - key FogOfWar was deprecated for GCDebug
  - new key GCDebug can be used to draw various debug features of maps
  - new key TouchInput for force disabling or enabling ...
