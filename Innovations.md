---
title: Innovations
---

GemRB isn't just a reimplementation of the Infinity Engine. While a lot of the changes
and enhancements are in the core or targetted specifically at
[modders](Modding.md), there are also a few that directly benefit
the players. Besides the obvious bugfixes, those include:

  - possibility to never even load the intro videos
  - [custom font support](/plugins/ttf)
  - input
      - (multi)touch input support
      - most games didn't even support mouse wheels
      - keyboard
          - if [~~cheat~~debug keys](Cheats.md) are turned on:
              - ctrl-y will also force unlock doors and containers
              - ctrl-shift-y will kill all the enemies in the area
              - ctrl-w will gather all the ground piles you've seen in
                the area under the cursor, merging items where possible 
          - windows that you can bring up using hotkeys can also be
            closed the same way
          - many extra buttons are marked as default and default cancel,
            so you can use enter and escape
  - inventory items are autoidentified if you have high enough lore
  - inventory and containers show blue borders around magic items (like
    in IWD2)
  - in BG chargen, the default portrait is randomised (for our sanity's
    sake :))
  - some GUI tweaks that allow infinite kits/spells/etc
  - an extensive array of commands for the ["Cheat" console](Cheats.md).
  - innates can be bound to quick spell slots
  - spell lists can be sorted by various attributes like offensiveness
    or spell school
  - effects of difficulty on xp and damage are configurable through
    difflvls.2da
  - arbitrary formations are supported: externalised to a 2da table, with an
    accompanying generator (for the relative coordinates)
  - Many [ToBEx](/engine/ToBEx) extensions are also implemented
  
... and more, this list is not yet comprehensive
