---
title: Cheat and debug keys
toc: true
---

Following is a list of cheats you can use during play or development of
GemRB.

Most of them do the same thing as the [original
cheats](https://gibberlings3.github.io/iesdp/appendices/clua/bg2.htm),
so we will list here only the differences and important ones.

Cheat keys are enabled by default. 

## Pop-up console

You can toggle the console with the **Ctrl+Space** key combination, which will
open or close it respectively at the top of the screen. It accepts all
[GUIScript commands](GUIScript/Functions.md)  and python expressions. The GemRB
module is already imported, so it's enough to call `GameSetPartyGold(1000)`
instead of `GemRB.GameSetPartyGold(1000)`.

Additionally, a few common functions have [shorthands defined](https://github.com/gemrb/gemrb/blob/master/gemrb/GUIScripts/Console.py#L40),
so things can be done faster (eg. `mta()` for `MoveToArea()`).

When you want to see the output of functions, remember to `print` it. You can also redirect
the log to also display in the game message window with `MessageWindowDebug(5)`.

## Cheats and conveniences

  - [Ctrl-C](){: .btn .btn--info} (different) - Force casts a hardcoded spell. The last
    selected actor is the caster and the target is the door/actor
    currently under the pointer. This currently casts knock (SPWI207).
  - [Ctrl-D](){: .btn .btn--info} (different) - Trap or trapped container pointed w/ mouse is
    disarmed.
  - [Ctrl-F](){: .btn .btn--info} (different) - Toggles fullscreen mode
  - [Ctrl-V](){: .btn .btn--info} (unknown) - Explores a small, random part of the pointed
    area.
  - [Ctrl-W](){: .btn .btn--success} (new) - Consolidate visible loot under the cursor into a
    single pile
  - [Ctrl-Y](){: .btn .btn--success} (similar) - Kills pointed actor or unlocks the pointed
    door/container, even if it requires a key.
    - [Ctrl-Shift-Y](){: .btn .btn--success} (new) - Kills all enemies in the area
  - [ALT](){: .btn .btn--success} (same) - Toggles debug flag DEBUG\_SHOW\_CONTAINERS (show all
    containers and doors)
  - [Ctrl-7](){: .btn .btn--info} (different) - Toggle drawing of Fog of war and the explored
    bitmap.

## Debugging

  - [Ctrl-M](){: .btn .btn--success} (similar) - Prints (on terminal or DOS window) useful info
    on pointed actor, door container or infopoint and current map
    - [Ctrl-Shift-M](){: .btn .btn--info} - Prints a debug dump of the chosen actor's animations
  - [Ctrl-B](){: .btn .btn--info} (different) - N/A
  - [Ctrl-I](){: .btn .btn--info} (different) - Triggers an interaction between the last
    pointed npc and a random party member.
  - [Ctrl-L](){: .btn .btn--info} (similar) - Plays the S056ICBL animation over the actor.
    (This exists in PST only)
  - [Ctrl-O](){: .btn .btn--info} (different) - N/A
  - [Ctrl-U](){: .btn .btn--info} (different) - Dumps GLOBAL GameScript variables.
  - [Ctrl-Shift-U](){: .btn .btn--info} (different) - Dumps death variables.
  - [Ctrl-Shift-V](){: .btn .btn--info} (new) - Dumps the main dictionary (eg. baldur.ini options and other engine vars).
  - [Ctrl-4](){: .btn .btn--info} (same) - Toggles debug flag DEBUG\_SHOW\_INFOPOINTS (show all
    traps, infopoints and wallgroups).
  - [Ctrl-5](){: .btn .btn--info} (different) - Cycles through a few debug modes related to wall polygons
  - [Ctrl-6](){: .btn .btn--info} (different) - Toggles debug flag DEBUG\_SHOW\_LIGHTMAP (show
    the lightmap).
  - [Ctrl-8](){: .btn .btn--info} (different) - Toggle drawing of searchmap over the area in
    GameControl.

## Animations

  - [Ctrl-A](){: .btn .btn--info} (similar) - Alters the animation ID of the actor. You have to
    hover your mouse over it.
  - [Ctrl-Z](){: .btn .btn--info} (unknown) - Same as Ctrl-A but backward
  - [Ctrl-S](){: .btn .btn--info} (similar) - Alters the stance (animation state) of the actor.
    You have to hover your mouse over it.
