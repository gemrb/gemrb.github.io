---
layout: post
title:  "GemRB 0.7.2 released!"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new (minor) release.

The biggest novelty is a cleanup of the ingame configuration guis and the ability to save the
configuration back to the disk. It is written to the GameDir or if that is unwritable, to the
SavePath as gem-baldur.ini (or equivalent). *All* subsequent reading and writing will be done
with that file, so changing the original will have *no effect on GemRB*.

In case you want just a quick peek at the debug console, it can now be redirected to the
ingame message window — open the console and type debug(LOG_DEBUG).

As far as we know, Trials of the Luremaster can now also be played until the end. We're
looking for brave warriors to test this claim.

Currently only the sources and some packages are available. You can get them from here.

Full changelog digest:

**GemRB v0.7.2 (2012-11-20):**
New features:
- configuration changes are now saved to gem-baldur.ini (or equivalent)
- GemRB now asks for confirmation when exiting
- output can now be shown in the ingame message window (run debug(5))
- ToBEx flags for effect damage: bypass mirror image, ignore difficulty
- SDL2 software keyboard

Improved features:
- custom dialog.tlk encoding support
- fonts, effect icons, initials, chapter text
- option windows
- actions, triggers, effects, invisibility handling
- assorted bugfixes
