---
title: Engine overview
---

### Overview of the GemRB Engine

GemRB is a game engine that strives to be compatible with Bioware's
Infinity Engine (IE), the engine**s** that drives Baldur's Gate, Icewind Dale
and Planescape: Torment games.

GemRB stands for **Game Engine Made with preRendered Backgrounds**. This
indeed describes the fundamental characteristics of Infinity
Engine-based games: The world, or more correctly the areas where you
move, be it cold empty plains of Icewind Dale, busy streets of Waterdeep
or damp catacombs under Sigil, was painted and/or rendered in advance,
during game development, into a series of static pictures.

The engine then transfers portions of those pictures on the screen, puts
animated player and non-player avatars on top of it, and uses clever
tricks to make the world appear lively and three-dimensional. But
remember that deep inside it's just animated sprites over a static
picture.

**Note that actual engine of each of the original games differs** from that
of other games. That of Baldur's Gate 1 is the most primitive, PS:T is
the most atypical, and Baldur's Gate 2 the one most useful for modding.

![Simplified Infinity Engine Ancestry](/assets/img/ie_chronology.png)

GemRB has to be compatible with all of them, either by adopting superset
of the features, or choosing between mutually exclusive features by
means of **GameType**, which in turn selects appropriate Game Flags,
GemRB's own override files, plugins and scripts. GameType is set in the
main config file (usually autodetected).

### GemRB Sources

GemRB sources consist of:

  - Main program
  - Core library
      - Interface class
      - UI layer
      - Plugin manager class
      - Gamescript
      - Scriptables
      - and much more
  - Plugins
      - I/O drivers
      - Resource loaders
      - Scripting language(s)
      - Effects
  - GUIScripts
  - Override and unhardcoded
  - Includes
  - Docs

#### Main program: `gemrb/GemRB.cpp`

Trivial main() function that just calls the engine's `Init()` and `Main()`
functions.

#### Core library: `gemrb/core/`

Core library is the main part of GemRB. It contains parts of the engine
common to all the games. The goal is to make it as universal as
possible, but some AD\&D rules-specific stuff is hard to get rid of.

##### Interface Class: `gemrb/core/Interface.cpp`

The library's central hub is `Interface` class, which binds the various
parts of the engine together (including the plugins), contains global
initialization, main loop, utility functions etc. It needs to lose some
weight!

##### PluginManager Class: `gemrb/core/PluginManager.cpp`

This is the class responsible for loading GemRB plugins.

##### User Interface: `gemrb/core/GUI`

These are classes defining window management, GUI controls (eg. buttons)
and our text handling subsystem.

#### Plugins: `gemrb/plugins`

Plugins in GemRB are used for:

  - I/O drivers
  - Resource loaders
  - Scripting language
  - Effects

##### I/O Drivers

These plugins are used for graphic and audio output (SDLVideo, SDLAudio,
OpenALAudio, NullSound) and input (SDLVideo again).

##### Resource Loaders

These plugins implement readers and writers for data files used by the
engine, many of which are in [custom formats](https://gibberlings3.github.io/iesdp/file_formats/index.htm)
(INIImporter, AREImporter, MVEPlayer, ...) and in case of
audio/video files also provide streaming (ACMReader, ...).

##### Scripting Language

GemRB's support for Python scripts is contained in the GUIScript plugin.
It is used in place of Lua, which the originals used to power the cheat
console.

Note that GameScript, scripting language used in Infinity Engine scripts
(sometimes called IEScritp), is implemented in the Core Library instead.

##### Effects

These plugins implement effects used in the Infinity Engine spells and
scripts like *RetreatFrom*, *SetPoisonedState*, *Damage* ... Common
effects are in the FXOpcodes plugin, game-while specific ones are in
IWDOpcodes and PSTOpcodes.

#### GUIScripts: `gemrb/GUIScripts/`

These are Python scripts implementing GemRB's user interface and many
game rules, which were hardwired into the executable in the original
games. The scripts are organized by game type, while the top dir contains
shared files. Hacking the scripts provides a gentle path into GemRB
development and you can find [specific documentation here]().

#### Overrides and unhardcoded data: `gemrb/override/`

`gemrb/override/` and `gemrb/unhardcoded/` are two directories
containing GemRB's own data files for all (`shared`) or a given game
type. This includes tables which were hardwired in the original
engine. Also the all important `gemrb.ini` internal engine settings
file is found here.

The difference between the two is that `unhardcoded` contains only
new files, while `override` is meant as what its name suggests. We
want the latter to contain as few files as possible to reduce
potential conflicts with mods.

See this [tabular overview](Modding.md#notes-to-modders) to better
understand how they relate to the data shipped with the games.

#### Includes: `gemrb/includes`

Common include files used by Core Library and the plugins.

#### Docs: `gemrb/docs`

Initial GemRB documentation. `Tables/` contains descriptions of
GemRB's override tables ([not for long](https://github.com/gemrb/gemrb/issues/685))
and the rest are mostly very very specific or already found
on this website, like the GUIScript docs.
