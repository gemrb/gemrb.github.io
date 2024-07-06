---
title: Innovations
---

GemRB isn't just a reimplementation of the Infinity Engine. While a lot of the changes
and enhancements are in the core or targetted at [power users and modders](Modding.md),
there are also a few that directly benefit the players. Besides the obvious bugfixes,
those include:

  - an extensive array of commands for the ["Cheat" console](Cheats.md).
  - effects of difficulty on xp and damage are configurable through
    difflvls.2da
  - arbitrary formations are supported: externalised to a 2da table, with an
    accompanying generator for the relative coordinates
  - more file formats are supported (eg. PNG, OGG), so custom portraits and sound sets
    are easier to create
  - many [ToBEx](ToBEx.md) extensions are also implemented
  
... and more, this list is not yet comprehensive

## Ease of use
  - possibility to never even load the intro videos
  - inventory items are autoidentified if you have high enough lore
  - innates can be bound to quick spell slots
  - spell lists can be sorted by various attributes like offensiveness,
    level or spell school
  - inventory and containers show blue borders around magic items (like
    in IWD2)

## GUI and high resolutions
 - [window scaling, high resolutions support](http://gemrb.org/Features.html#wide-screen-higher-resolutions)
   - for arbitrary higher resolutions at the same pixel count (resize the window while in windowed mode)
   - game window scaling, for more game real estate even without the Widescreen mod (just set a higher resolution)
 - [custom font support](Fonts.md)
 - drawing FPS is settable and defaults to matching the screen refresh rate, rather than 30
 - expanded debug console
 - general window dragging support
 - in character generation, the default portrait is randomised (for our sanity's
   sake :))
 - some GUI tweaks that allow infinite kits, spells and so on or improve usability
   in other ways
 - better support for [internationalization](Text-encodings.md) of game resources


## Input
 - (multi)touch input support
 - mouse
   - most games didn't even support mouse wheels
   - holding shift while scrolling with the mouse wheel simulates horizontal scrolling
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
