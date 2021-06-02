---
title: GemRB 0.8.8 released! (The calm before the storm edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new (minor) release.

This release features improvements in several areas, with no new major subsystems.
You might be thinking: "What's this, weren't we promised subviews?!" and the answer
to that is: yes! Stay tuned for another release in the following days as we integrate
the branch back and do some final retesting.

You can get the new GemRB from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.8.8 (2021-06-02):
      New features:
        - gameplay content for the demo
        - Heart of Fury support
        - SDLAudio caching and volume control
        - PlayStation Vita port
        - simpler invocation, AppImage packages

      Improved features:
        - lightning bolts, iwd2 stealth, iwd effects, pst levelup
        - scripting, audio backends, logging
        - build system, portability and performance improvements
        - externalized summoning limit, trap limit, narration text speed
        - bugfixes


Thanks to everyone that contributed their time and wit, including:

2play, Alan1616, Alan1616, Balrog994, Bernd Schmidt, Brad Allred, Bubb13, Cowcat5150,
Cristi Mitrana, Destroyer5150, FrElvire, Jaka Kranjc, Jan Petykiewicz, Kevin Michael
Frick, Khaled Hosny, Laurie Chilvers, MarcelHB, Mariusz Obajtek, Northfear, Poligraf,
Rodrigo Santellan, Ryein Goddard, SharkyRawr, Toulonnais72, afxgroup, bittin,
burner1024, emorrp1, escalade, fenuks, fizzet, luke243, m7600, nerd-rage, neula,
psilyntdev, rfht, samo79, tonyRecordOn.

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.

**Notes to packagers:**
- new things in the config options:
  - Logging=0 to disable all logging
  - GamepadPointerSpeed and VitaKeepAspectRatio settings
- see the man page for new ways to run GemRB and the -q option (same as AudioDriver=none)
- since another release is on the horizon, consider skipping packaging this one
