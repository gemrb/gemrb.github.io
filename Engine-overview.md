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
  - override and unhardcoded
  - includes
  - docs

#### Main program

`gemrb/GemRB.cpp`

Trivial main() function that just calls engine's Init() and Main()
functions.

#### Core library

`gemrb/core/`

Core library is the main part of GemRB. It contains parts of the engine
common to all the games. The goal is to make it as much universal as
possible, but some AD\&D rules-specific stuff is hard to get rid of.

##### Interface Class

`gemrb/core/Interface.cpp`

The library's central hub is `Interface` class, which binds the various
parts of the engine together, contains global initialization, main loop,
utility functions etc.

##### PluginManager Class

`gemrb/core/PluginManager.cpp`

This is the class responsible for loading GemRB plugins.

##### User Interface

`gemrb/core/GUI`

#### Plugins

Plugins in GemRB are used for:

  - I/O drivers
  - Resource loaders
  - Scripting language(s)
  - Effects

##### I/O Drivers

These plugins are used for graphic and audio output (SDLVideo, SDLAudio,
OpenALAudio, NullSound) and input (SDLVideo again)

##### Resource Loaders

These plugins implement readers and writers for data files used by the
engine (INIImporter, AREImporter, MVEPlayer, ...) and in case of
audio/video files also provide streaming (ACMReader, ...)

##### Scripting Language(s)

GemRB's support for Python scripts is contained in GUIScript plugin.
There's also a LUAScript plugin in the making. Note that GameScript,
scripting language used in Infinity Engine scripts, is implemented in
the Core Library instead.

##### Effects

These plugins implement effects used in the Infinity Engine scripts,
like *RetreatFrom*, *SetPoisonedState*, *Damage*, ... Common effects are
in FXOpcodes plugin, game-specific ones are in IWDOpcodes and
PSTOpcodes.

#### GUIScripts

`gemrb/GUIScripts/GAMETYPE/`

These are Python scripts implementing GemRB's user interface and game
rules, which are hardwired into executable in the original games. The
scripts are organized by game type. Hacking the scripts is traditionally
a gentle path into GemRB development, especially if you read
[start](/guiscript/start).

#### Overrides and unhardcoded data

`gemrb/override/GAMETYPE/`

Override contains GemRB's own data files for a given game type, e.g.
tables which were hardwired in the original engine. Also the all
important `gemrb.ini` is found here.

#### Includes

`gemrb/includes`

Common include files used by Core Library and the plugins.

#### Docs

`gemrb/docs/en`

GemRB documentation. Really :-). `Tables/` contains descriptions of
GemRB's override tables, `GUIScript` covers API used by the Python
scripts.
