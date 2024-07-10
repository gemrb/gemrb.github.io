---
title: GemRB 0.9.3 released! (Dragon's hoard edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

As a year's worth of work this release brings a bunch of improvements. Players will notice
pathfinder speed optimizations, better sound logic, chunking and plenty of polishing.
Non-English player woes have been fully laid to rest, with any combination of game, system
and filesystem encoding properly taken into account.

Sources and packages are available. You can get them from [here](https://gemrb.org/Install).

Full changelog digest:

		GemRB v0.9.3 (2024-07-10):
			New features:
				- full i18n (language) support, custom journal entries
				- chunking approximation
				- BMP v3 and v5 support
				- small test suite, tracy support
				- iwd2 identification variants and speed data
				- nwn-for-bg2 compatibility

			Improved features:
				- area music, creature & area sounds
				- colored logging, pathfinding, drawing
				- ee compat, effects, modals, projectiles, familiars
				- iwd2 & pst worldmap
				- switched to c++14, build system
				- bugfixes

**Thanks to everyone that contributed** their time, including:
11jo, akdjka, alvv-z, Andrea Cardaci, Andrea Palmatè, anijatsu, ArtemS2, blender-girl, Brad Allred, Bubb, burner1024, DarkMalex, davidagnome, DDQW, Domagoj Stolfa, Dreamkins, Fernside2, i30817, Jaka Kranjc, K1ngst0m, Rod Batten, Rodrigo Santellan, MarcelHB, mariomartinezm, Mateusz Hercuń, Matthieu Volat, Mingun, orcutt989, Piotr Kubaj, PowaBanga, SilentMRG, skellytz, Solène Rapenne, Stefan Schlosser, tomasz89, Tom Kidd, traveler-gemrb, ynorsa, zebez.

**Notes to packagers:**
- an optional ScaleQuality key has been added to the sample configs,
- the Fullscreen key has been removed (the in-game setting is preferred)
- the build system is now even more modular, so you can tweak more of it

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.
