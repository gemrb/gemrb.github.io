---
layout: post
title:  "GemRB V0.5.1 is out"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new "minor" release. A lot more work has been done on projectiles,
the scripting system, effects and combat. Combined with the numerous bugfixes, this enabled the first
rough, but hackless BG2:SoA runthrough!

Currently only the sources are available.

Full changelog digest:

New features:
- BG2:SoA is roughly completable!
- almost all missing IE's hardcoded projectiles, spell hit projectiles,
projectile trails, projectile failure (spell), projectile effectlists
- auto-reloading of projectile weapons in case the ammo stack runs out
- damage resistance
- sorcerer style spellbooks, reading of iwd2 spellbooks
- target following to other areas
- the null sound plugin is now always loaded last by default; for old
installs see the provided configuration example (DelayPlugin)
- intelligence and wisdom dictated lore bonus
- a GUIEnhancements config option (on by default) that enables a few
extra controls (for convenience and larger mods)
- PST death counters (don't anger the Lady)
- initial support for targetting by portrait

Improved features:
- actions, effects and triggers
- pathfinding, feet circles, fog of war and worldmap travel
- combat and spellcasting (especially summoning)
- projectiles
- config and default table value parsing is smarter about spaces
- various guiscripts
- bugfixes

Applied patches:
- various patches from nugrud for bg2 gui enhancements
- fix compilation (with cmake) on OS X, by hanicka
