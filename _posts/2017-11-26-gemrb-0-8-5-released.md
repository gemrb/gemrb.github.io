---
title:  "GemRB 0.8.5 released! (Lynxiversary edition)"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

It has been a while since our last release, but plenty of goodies have landed since. 
This release brings a slew of minor features and fixes, of which a select few are mentioned below.
Of those that aren't, a last minute AttackReevaluate fix stands out, since that action is used all
the time in AI scripts.

Wait a minute, but where's the promised return of biography editing, you may exclaim. That branch
is very much still alive and being worked on, with more than 1000 extra changes. The rewrite just
spiralled out of control. Interested users can take a peek at the subviews branch.

You can get the sources and packages from here.

Full changelog digest:

**GemRB v0.8.5 (2017-11-26):**
    
    New features:
    - SDL2 resolution-independent window scaling, environmental audio, IRIX compatibility
    - regeneration during sleep, time dilation
    - iwd2 ability stacking, iwd ZZ* weapon bonuses
    - portrait.2da handling, avatar shadows, dialogF.tlk handling

    Improved features:
    - infravision
    - better compatibility with bgt, 10pp, ia, kelsey, dr
    - sdl2 input, mouse scrolling, opengl driver
    - iwd2 cg&lu, item (un)usability, avatar sizes, permanent clabs
    - ambients, verbal constants, random walk, walk sounds
    - bugfixes

Packagers note that a few CMake options have been tweaked and are now togglable as true CMake options.

