---
layout: post
title:  "GemRB V0.5.0 is out"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new major release. 
The berserking development rage still hasn't ended and only a month since the last release a few 
important milestones have been reached. Combat and various actions are now much improved, many of 
the projectiles that were hardcoded in the IE now work, time is handled better ... Coupled with a bunch of other
bugfixes and new features this means that now a few of the games are roughly playable beyond their starting areas!

Currently only the sources are available.

Full changelog digest:

New features:
- SoA, ToB and PST are roughly playable beyond their first levels
- combat: dual-wielding, APR, proficiency and style boni, dexterity
bonus, initiatitive and speed factor, individual combat rounds
- many IE's hardcoded projectiles and support for projectile sounds
- IWD2 GUI now works after chargen too
- bg2 chargen now levels to the correct level
- summoned and charmed creatures can be ordered around
- actor tooltips (name and injury status)
- running, initial variable values and portal animations in PST
- hardcoded monk bonuses

Improved features:
- dialog, actions and triggers
- combat mechanics, animation, feedback, ranged combat
- matters of time and matter
- levelup, dual classing, multiclass handling
- focus: scrolling while paused is now possible
- animations (projectile, creature)
- pathfinding
- area music restarts when there's no music playing
- disarm trap checks skills
- various guiscripts
- bugfixes

Applied patches:
- #2802190 jbmetz (improve the rpm spec handling)
- #2802437 danamin (patch bomb sanitizing bg1 chargen + bg2 code share)
