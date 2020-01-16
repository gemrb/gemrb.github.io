---
title: Cheat and debug keys
---

Following is a list of cheats you can use during play or development of
GemRB.

Most of them do the same thing as the [original
cheats](https://gibberlings3.github.io/iesdp/appendices/clua/bg2.htm),
so we will list here only the differences and important ones.

Cheat keys are enabled by default. To start typing, toggle the console
with a Ctrl+Space key combination.

## Cheats and conveniences

  - Ctrl-C (different) - Force casts a hardcoded spell. The last
    selected actor is the caster and the target is the door/actor
    currently under the pointer. This currently casts knock (SPWI207).
  - Ctrl-D (different) - Trap or trapped container pointed w/ mouse is
    disarmed.
  - Ctrl-F (different) - Toggles fullscreen mode
  - Ctrl-V (unknown) - Explores a small, random part of the pointed
    area.
  - **Ctrl-W** (new) - Consolidate visible loot under the cursor into a
    single pile
  - **Ctrl-Y** (similar) - Kills pointed actor or unlocks the pointed
    door/container, even if it requires a key.
    - Ctrl-Shift-Y (new) - Kills all enemies in the area
  - ALT (same) - Toggles debug flag DEBUG\_SHOW\_CONTAINERS (show all
    containers and doors)
  - Ctrl-7 (different) - Toggle drawing of Fog of war (actually explored
    bitmap atm.).

## Debugging

  - **Ctrl-M** (similar) - Prints (on terminal or DOS window) useful info
    on pointed actor, door container or infopoint and current map
    - Ctrl-Shift-M - Prints a debug dump of the chosen actor's animations
  - Ctrl-B (different) - Draws path from start point marked by Ctrl-O to
    current mouse position.
  - Ctrl-I (different) - Triggers an interaction between the last
    pointed npc and a random party member.
  - Ctrl-L (similar) - Plays the S056ICBL animation over the actor.
    (This exists in PST only)
  - Ctrl-O (different) - Marks current mouse position as start point
    (origin) for path drawn with Ctrl-B
  - Ctrl-Shift-V (new) - Dumps the main dictionary
  - Ctrl-4 (same) - Toggles debug flag DEBUG\_SHOW\_INFOPOINTS (show all
    traps, infopoints and wallgroups)
  - Ctrl-6 (different) - Toggles debug flag DEBUG\_SHOW\_LIGHTMAP (show
    the lightmap)
  - Ctrl-8 (different) - Toggle drawing of searchmap over the area in
    GameControl.

## Animations

  - Ctrl-A (similar) - Alters the animation ID of the actor. You have to
    hover your mouse over it.
  - Ctrl-Z (unknown) - Same as Ctrl-A but backward
  - Ctrl-S (similar) - Alters the stance (animation state) of the actor.
    You have to hover your mouse over it.