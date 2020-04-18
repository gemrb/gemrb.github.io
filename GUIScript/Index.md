---
title: GUIScript documentation
---

This page is intended as a brief overview for one of two scripting
systems in GemRB: GUIScript. You should read it if you want to hack on
GemRB's GUI or related logic.

## GUIScript and GameScript

As said above, there are two scripting systems within GemRB - GUIScript
and GameScript. What's the difference between them?

The first one, **GUIScript**, concerns mostly with game GUI, i.e. user
interaction, opening and closing windows, pushing of character sheet
buttons, inventory, etc. This functionality has been hardwired in the
original games and so we need to implement it anew. GUIScript scripts
have to be tailored for each game type, because each game uses more or
less different GUI, string refs, and so on. We program these scripts in
Python.

The second one, **GameScript**, governs almost all AI and "AI" in game,
effects of opening a trapped chest, annoying an important NPC or putting
together pieces of a puzzle. These scripts are of course totally story
(and hence game) dependent, but fortunately they are stored in game's data
files. They are written in special language and usually compiled in
\*.bcs files. Some of them are uncompiled (\*.bs files and within \*.dlg
files) or even stored raw in dialog.tlk and shops (in Planescape: Torment).

This page concerns itself with the first type of scripts, GUIScripts. GemRB
implements python bindings into the core engine to enable quick and easy
development.

Most functions are available in the **GemRB** python module, while the rest can be
found in the internal **_GemRB** module. Both are implemented in 
[GUIScript.cpp](https://github.com/gemrb/gemrb/tree/master/gemrb/plugins/GUIScript).
The internal module is not to be used directly, but through python metaclasses (see
[GUIClasses.py](https://github.com/gemrb/gemrb/blob/master/gemrb/GUIScripts/GUIClasses.py)).
If a function documentation has a metaclass prototype definition, use that instead of
the main one!

## Script execution

GUIScripts are stored in gemrb/GUIScripts/. In the top level, there are
shared scripts, while directories named after the chosen GameType
contain the rest. Where there is a name clash, the more specific file
is used.

First script to be run is always named `Start.py`. The main window with
messages, map display, character portraits, action buttons and so on are
all set up starting with the script `MessageWindow.py`. Other scripts
are usually named after \*.CHU resource file they mostly use.

Example:
``` 
Baldur's Gate 2 inventory:
  gemrb/GUIScripts/bg2/GUIINV.py

Shared inventory logic:
  gemrb/GUIScripts/InventoryCommon.py
```

A contrived example of a script could look like:
```
import GemRB
RacesTable = GemRB.LoadTable ("RACES")
print RacesTable.GetValue ("ELF", "CANDUAL")
```

A description of all functions in the huge GemRB module is available
[below](#list-of-functions).

All scripts to be run have to define an `OnLoad()` function, which is
called by GemRB each time the script is loaded. Python files without
an `OnLoad()` function are merely modules imported into other scripts.

The control between scripts is passed with the `GemRB.SetNextScript()`
function, which causes another script to be loaded. Repeated loading of
a script causes repeated calling of its `OnLoad()` function.

All scripts automagically import all symbols from
`gemrb/GUIScripts/GUIDefines.py`, which contains definition of constants
commonly used in the scripts. Other files in this directory can be
imported too.
GemRB.SetNextScript ("MessageWindow")



# Extra documentation
**TODO: generate from ./***

# List of functions

**TODO: generate from functions/***
