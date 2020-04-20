---
title:  "GemRB 0.8.2 released! (Deepwinter edition)"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new (minor) release.

It has been a while since the last release, but plenty of polishing and some new features have been
added since (particularly for iwd2).

A large refactoring of our text layouting and drawing code has been in the works for most of the
year, but is not included in this release. We plan to merge it soon and fix any stragglers, then
after intensive testing, do another release. But that's for another announcement!

Currently the sources and some packages are available. You can get them from here.

Full changelog digest:

**GemRB v0.8.2 (2015-01-01):**
  New features:
    - iwd2 spell learning
    - movie overrides (tob outro)
    - 3ed sneak attack, concentration/disruption
    - statistically fairer random number generator

  Improved features:
    - iwd2 chargen, clabs, combat, music
    - custom map notes and biographies now save properly
    - effects, tob ending, animation, actions, bg1 nights
    - bugfixes

For everyone building GemRB on their own or for others, also note:

The following build vars were renamed in the final few places:
- DATADIR -> DATA_DIR
- SYSCONFDIR -> SYSCONF_DIR
- PLUGINDIR -> PLUGIN_DIR

If you use a custom build setup, adjust appropriately. CMake setups are not affected detrimentally.
