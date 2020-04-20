---
title: GUIScript documentation
toc: true
---

This page is intended as a brief overview for one of two scripting
systems in GemRB: GUIScript. You should read it if you want to hack on
GemRB's GUI or related logic.
  
Also check out the [list of functions](Functions.md).

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
```python
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

## Typical GUIScript

A typical script's task is to open a window, setting button labels and
callbacks and then return control back to core GemRB. The script also
provides a mean to close the window created.

For a short example, take a look at iwd2's journal window script at
[GUIJRNL.py](https://github.com/gemrb/gemrb/blob/master/gemrb/GUIScripts/iwd2/GUIJRNL.py).

## GUI controls

Remember, the original GUI layout is in a proprietary binary format: 
[CHU](https://gibberlings3.github.io/iesdp/file_formats/ie_formats/chu_v1.htm). 

Check the [GUI structure](GUI-structure.md) page to see the common controls,
how data passes between them and the core, and how to access them.

## Reserved functions

The following functions have a special meaning, usually because they also
sometimes have to be invoked directly by the core via a callback.

- `OnLoad()`: called when the GUI script was loaded by GemRB.

- `StartTextScreen()`: called when the engine encountered a TextScreen or an
IncrementChapter game script action.

- `OpenWorldMapWindow()`: called when the worldmap window must be opened.

- `UpdatePortraitWindow()`: called when there was a change in the party, this
includes party order and PC hitpoints or state changes that may affect
portraits.

- `SelectionChanged()`: called when there was a change in selection of team
members.

- `OpenStoreWindow()`: called when the StartStore scripting action was called.
Or a container item was accessed.

- `UpdateControlStatus()`: called when a pane changed on the game screen.

- `OpenContinueMessageWindow()`: called when the player may choose to continue a dialog.

- `OpenEndMessageWindow()`: called when the player may choose to end a dialog.

- `DeathWindow()`:s called when the team/protagonist is killed. See also
`GameSetProtagonistMode()`.

- `OpenReformPartyWindow()`: called when there are too many teammembers.

- `OpenContainerWindow()`: called when the player accessed a ground pile or
container.

- `CloseContainerWindow()`: called when GemRB requests the container window to be
closed.


## GUIScripter's Workflow

Check the following list for adding new windows, which while mostly
unnecessary nowadays, contains good exploration tips. So it's also useful for
various control issues and questions about their default state.

1.  Run GemRB and an original game in parallel and notice GUI parts
    missing or badly done in GemRB.
2.  Divine the CHU file containing the window resource. It can either be
    guessed by comparing names of all CHU files in the game to required
    functionality, from GUIScript already implementing related part of
    the GUI or by viewing all CHU files in CHU/BAM/MOS viewer (DLTCEP,
    NearInfinity) and finding the right looking one.
3.  Find the ID of the window to be implemented in the CHU file, usually
    with DLTCEP or NearInfinity.
4.  Copy & paste common parts of the script from another one opening
    similar windows. Use shared code where possible.
5.  Using a CHU viewer find control IDs for the controls you need to
    configure in the script and add their setting into the script, again
    copy & pasting from another script. Usually start with magic trinity
    of GetControl, SetText, SetEvent for each button. Use dummy numbers
    for now. Beware, NearInfinity displays wrong IDs for labels. You
    will have to add the label's control ID to "buffer size" \<\< 32 to
    get the right control ID.
6.  Write down button labels as they are seen in the original game and
    find their strrefs using DLTCEP or NI. Alternatively, you can set
    "Strref On=1" in \*.INI of the original games and write down
    directly the strrefs as they are displayed instead of the labels.
    This however does not work with Planescape: Torment.
7.  Put the strrefs into the SetText() functions in the script.
8.  Now that the trivial parts are done, the real fun can begin. But
    that's a subject too advanced for this page. :-)

## Coding style

Please try to follow the indentation style of other GUIScript scripts,
in particular:

  - indent each level with 1 TAB character
  - insert space between function name and opening parenthesis in
    function calls and around operators and after the hash sign in text
    comments
  - insert blank lines between logically separated chunks of code, e.g.
    between setting of different controls
  - insert blank lines after functions and a row of hashes
  - if a function does not return a value, do NOT end it with 'return'
  - keep naming convention for windows, callback etc.
  - comment your code
