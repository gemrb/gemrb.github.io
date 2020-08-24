---
title: GemRB 0.8.7 released! (Updated my journal edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

The new release brings over 500 changes manifested as bugfixes, smaller features, cleanups
and an improved setup experience. More than that, it introduces a new [smarter
pathfinder](https://gemrb.org/2020/07/16/new-pathfinder-smarter-movement.html) with
bumping support and other movement related improvements. At the same time work continued
on the drawing and GUI handling rewrite — stay tuned for a deeper dive later this week.
With this anniversary release out of the way, finishing that rewrite is again our main
priority.

You can generally get GemRB from [here](https://gemrb.org).

Full changelog digest:

    GemRB v0.8.7 (2020-08-23):
      New features:
        - new smarter pathfinder with bumping support
        - animal taming, iwd2 hardcoded saving throw bonuses
        - vcpkg and out-of-the box msvc support
        - non-ascii data filename support

      Improved features:
        - disk reading speedups, ease of setup
        - iwd chargen, pst spell timing, hardcoded overlays, iwd2 casting ai
        - better actor speeds & walk sounds
        - audio, pst ini handling, savegame compatibility, morale handling
        - effects, projectiles, actions, range calculations
        - bugfixes

      Notes:
        - switched to c++11 and cmake 3.1 as a minimum
        - dropped windows 9x compatibility


Thanks to everyone that contributed their time and wit, including:

bholland, burner1024, Biswapriyo Nath, Boris Kruglov, Brad Allred, Bubb, caillean7,
fenuks, fizzet, FrElvire, HumanG33k, ifyGecko, Ignat Insarov, Jaka Kranjc, Kapizor,
Kevin Michael Frick, Laurie Chilvers, Lukáš Valenta, MarcelHB, Mingun, neula,
Northfear, Rune Morling, schyzophrene-asynchrone, stuffu.

*If anyone is wondering about the release name: a small problem was blocking
the [famoust PST line](https://www.youtube.com/watch?v=uxs3g0Xgh7k) from being
heard. And it's appropriate for the anniversary.*
