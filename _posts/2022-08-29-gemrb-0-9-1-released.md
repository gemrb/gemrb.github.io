---
title: GemRB 0.9.1 released! (Life is strength edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new release.

It features loads of improvements in core game systems, making Icewind Dale II almost completable,
but also in the rest of the engine. Among other things this means further improved speed, better
unicode support and deprecation of Python 2 support. As usual the release also comes with many
smaller features, bug fixes, polishing and code cleanups.

Sources and packages are available. You can get them from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.9.1 (2022-08-29):
      New features:
        - iwd2 can be progressed to well into chapter 5
        - faster loading and saving, faster OpenGL rendering
        - Use magic device skill, precise shot, iwd1 bard song choice
        - SDLAudio plugin now supports ambients
        - console history is now preserved, more text colors externalized
        - logging is now done via fmt (bundled headers)

      Improved features:
        - python3 support (now the only option)
        - unicode support (iconv not optional any more!)
        - spellcaster ai, effects, scripting, projectiles, weapon style customization
        - audio, drawing, appimage, ini spawns
        - bugfixes

Thanks to everyone that contributed their time, including:
Adrien2002, Arc0re, Argent77, Brad Allred, Bubb, burner1024, chilvence, Clemens Tiedt, Cowcat5150,
dagdha2002, Dan Church, Dariusz Okoń, Darpaek, DudeMcDude, Emwues, fizzet, FrElvire,
Gabriel Sztorc, goduck777, Isso4820, jabaldwin, Jaka Kranjc, jheronimus, Laulajatar, m7600,
MarcelHB, Michael Schellenberger Costa, Mingun, Northfear, reallyhairydave, Rhastor,
Rodrigo Santellan, romadu, Sébastien Noel, shinra-electric, skellytz, Steamcrusher,
Stephen E. Baker, Stephen Kitt, STyx2909, syzygos-mideias, Timothy Hyers, Tomsod,
TotalCaesar659, Zimmermann Gyula.

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.

**Notes to packagers:**
- python2 support is gone
- iconv is now a required dependency (external or provided by your libc)
- minimum cmake version has been bumped to 3.11
