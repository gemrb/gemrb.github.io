---
title: GemRB 0.9.5 released! (Riches beyond compare edition)
author: Jaka Kranjc
---

The GemRB team is proud to announce a new major release.

It features significant changes in several areas. The audio subsystem received many improvements and input handling was upgraded especially for users of controllers. The pathfinding performance was dramatically increased, some tests quantifying that as 13-161 % for short paths, 48-196 % for medium paths, 68-146 % for long paths. EE-like zoom is now available in all games, just set "Zoom Lock" to 0 in the gem-*.ini file in your game folder.

On the game support side of things this release brings many improvements for IWD2, now considered as polished as the other games, several fixes for PST and more work on compatibility with the EEs. Support for BG2EE is still experimental, but the Shadows of Amn portion is known to be completable. Our demo received a much nicer avatar and new asset creation capabilities were added (like animations not limited to 15 FPS).

Due to user feedback the SDL1 backend has not been deprecated, but provisionally updated. There is a wish to move to C++17 in the next release cycle. If this would negatively impact your platform, do let us know.

Sources and packages are available. You can get them from [here](https://gemrb.org/Install).

Full changelog digest:

    GemRB v0.9.5 (2026-03-23):
      New features:
        - partial audio system rewrite for better (spatial) audio and music
        - iwd2: customizable action bar, weapon set switching, item usability info
        - detect illusions, spell info on right-click, various hardcoded pst bonuses
        - smooth keyboard scrolling, in-game zoom
        - GUI enhancements are now configurable from within the game

      Improved features:
        - pathfinder and drawing speedups
        - video players, animations, controller input
        - iwd2 weapon sets, pst GUI, pst level up, ee compatibility
        - scripting, effects, projectiles
        - bugfixes

**Thanks to everyone that contributed** their time, including:
2play, Andrej Pancik, ArminiusTux, arosenow, Ashvith10, Balxkodehodet, BinBashBanana, Boris Kruglov, Brad Allred, Bubb13, burner1024, CalamariDetective, Clort, CodeSpartan, Dariusz Pyś, DartPower, dbojan, dolio, exhuman, Florian Piesche, HugeTaffer, Jaka Kranjc, Jens Kleine-Herzbruch, JohnSmithBH84, Juan Mathews Rebello Santos, jvgp100, Lucas Z., MarcelHB, mark-314159, markfoged, MvKord, orcutt989, packrat0x, nerifuture, Peppersawce, quangtrinhvan93, Rodrigo Santellan, rubyFeedback, Stefan Schlosser, StVitruvius, Timo Gurr, traveler-gemrb, Tugcga, Ulroxiel, Warphi.

**Notes to packagers:**
 * There is a wish to move to C++17 in the next release. If this would negatively impact your platform, let us know.
 * New config keys were added and some removed, so if you ship your own config defaults, we recommend syncing them with these changes:
   * `GUIEnhancements` has been removed and is now stored in the main game ini file plus configurable through the options screen
   * `GamepadPointerAccel`, `GamepadLDeadZone`, `GamepadRDeadZone` are keys for customizing controller input parameters
   * `UseSoftKeyboard` was unused and has been removed
   * `EdgeScrollOffset` determines when to trigger area scrolling when the cursor is close to the window edge
   * `GamepadSupport` replaces the compile time define `USE_SDL_CONTROLLER_API`

If you want to be notified of GemRB releases via email, subscribe to the
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release)
mailing list.

**What's next?**

The plan for 0.9.6 is to work on polishing, improving moddability and new game support,
maybe getting bg2ee out of experimental status, deal with some postponed issues, and
whatever piques the contributor's fancy.

We're looking for ninjas to help with replacing FreeType (with SDL_ttf) and libvlc,
[GLESv2 support](https://github.com/gemrb/gemrb/issues/938)), general Enhanced Edition
[compatibility](https://github.com/gemrb/gemrb/labels/game%3A%20ees) and several
problems unique to [apple devices](https://github.com/gemrb/gemrb/labels/portability).
Other contributions are of course [welcome as well](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md).
