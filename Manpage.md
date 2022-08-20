---
title: Manual page
toc: true
---

# NAME

GemRB - a reimplementation of the Infinity Engine

# SYNOPSIS

**gemrb** \[-q\] \[-c *CONFIG-FILE*\]  
**gemrb** *PATH-TO-GAME*  
**torment**  

# DESCRIPTION

**GemRB** is a portable open-source implementation of Bioware’s Infinity Engine, which run
fine RPGs like Baldur's Gate, Icewind Dale and Planescape: Torment.

**GemRB** reimplements only the game engine. To actually play anything,
you have to have the data from the original game(s), installed or
unpackaged where GemRB can find it. See the *GamePath* and *CDn*
settings in the engine configuration file below. A full install is
recommended.

# OPTIONS

  - **-q**  
    Disable audio completely, regardless of supported audio plugins.

  - **-c** *FILE*  
    Use the specified configuration file *FILE* instead of the default
    *gemrb.cfg*.

**Note:** You can also use the program's name as a mean to select the
configuration file. For example, if the program's name is *torment*
instead of *gemrb*, the engine first searches for *torment.cfg* and only
if it's not found it searches for *gemrb.cfg*.

To use this feature, just create a symbolic link *torment* pointing to
the *gemrb* binary and then run *torment* instead.

# CONFIGURATION

A configuration file consists of pairs *PARAMETER=VALUE*, each on its
own line. The case of PARAMETER is not significant, GameType is the same
as GAMETYPE. If the same PARAMETER is defined more than once, only the
last occurrence is used.

Empty lines and lines starting with \`\#' (hash sign) are ignored.

At least the *GamePath* parameter needs to be changed.
That is often enough, so do not fiddle with the other paths too much.

# General Parameters:

  - **GameType**=(auto|bg1|bg2|iwd|iwd2|how|pst)  
    Type of the game. The value is a name of subdirectory in override/
    and GUIScripts/ directories with game type-specific files and
    scripts. It is at present also used for various tweaks hardcoded in
    the GemRB engine. To autodetect the game type, use the default "auto".

<!-- end list -->

  - **GameName**=STRING  
    Arbitrary name of the game. It will be displayed in the window's
    title bar.

<!-- end list -->

  - **Encoding**=(default|polish|czech|german)  
    Specify language used in the game data.

<!-- end list -->

  - **GUIEnhancements**=INT  
    The value is a bitfield. Set it to 1 to enable a few GUI
    enhancements, mostly in BG2. Add or set to 2 to try to autoidentify items on
    transfer (if the character has enough lore). Add or set 4 if you want to skip
    the item description window when opening bags. Enabled by default.

<!-- end list -->

  - **MultipleQuickSaves**=(0|1)  
    EXPERIMENTAL. Set this to 1 if you want GemRB to keep multiple
    quicksaves around. Disabled by default.

<!-- end list -->

  - **MaxPartySize**=INT  
    Set this to 1-10 if you want more party members or enforce fewer. 6 by default. **NOTE:** 
    For bigger parties you need to choose a big enough resolution, so there will be
    enough room for all the party portraits! No space for that in PST or IWD2. The
    10pp mod is required to fix various game scripts, so the extra party members
    don't get stuck in cutscenes.

  - **Logging**=(0|1)
    By default (set to 1) logging is enabled and several loggers are used depending
    on the plaftorm. Use 0 to disable all logging, which can help in performance
    critical settings.


# Video Parameters:

  - **Width**=INT  
    Game window width (in pixels).
This can be arbitrary, but results depend on the game data.
Check the website for a detailed explanation of resolution modes.

  - **Height**=INT  
    Game window height (in pixels).

  - **Bpp**=INT  
    Color depth of the game window (in bits per pixel).

<!-- end list -->

  - **Fullscreen**=(0|1)  
    Whether the game should run in fullscreen mode.

<!-- end list -->

  - **SkipIntroVideos**=(0|1)  
    If set to *1*, the intro and logo videos are skipped to save
    developer's nerves. The default is *0*.

<!-- end list -->

  - **GCDebug**=(0|2047)
    Bitfield with reserved bits for drawing Map debug layers.
     * No Debugging features = 0 (default)
     * DEBUG_SHOW_INFOPOINTS                = 1
     * DEBUG_SHOW_CONTAINERS                = 2
     * DEBUG_SHOW_DOORS                             = 4
     * DEBUG_SHOW_DOORS_SECRET              = 8
     * DEBUG_SHOW_DOORS_DISABLED            = 16
     * DEBUG_SHOW_DOORS_ALL                 = 28
     * DEBUG_SHOW_LIGHTMAP                  = 32
     * DEBUG_SHOW_WALLS                             = 64
     * DEBUG_SHOW_WALLS_ANIM_COVER  = 128
     * DEBUG_SHOW_WALLS_ALL                 = 192
     * DEBUG_SHOW_SEARCHMAP                 = 256
     * DEBUG_SHOW_FOG_UNEXPLORED            = 512
     * DEBUG_SHOW_FOG_INVISIBLE             = 1024
     * DEBUG_SHOW_FOG_ALL                   = 1536

# Audio Parameters:

  - **AudioDriver**=(openal|sdlaudio|none)  
    Use the specified plugin as the audio driver. The default is openal,
    while *none* will disable all audio.

# Path parameters:

  - **CaseSensitive**=(0|1)  
    When this parameter is set to *1*, the engine will try to find files
    regardless of their names' case at the cost of a slight speed
    penalty. This is especially important when using game files on
    CD-ROMs, where the files can't be renamed. Like many Windows
    programs, the original games use inconsistent mix of lower/upper
    case letters for naming and referencing their files.

Set this parameter to *1* on Unix-like systems.

  - **GamePath**=PATH  
    Path to the directory where the original game is installed. If you
    can't install the game under MS Windows or with WINE, you can try to
    unpack the data files with the *unshield* program found at
    *http://synce.sourceforge.net*.

<!-- end list -->

  - **CD1**=PATH  

  - **CD2**=PATH  

  - **CDn**=...  
    Path to the data files for the game's particular CDs or any other
    data sources.

<!-- end list -->

  - **CachePath**=PATH  
    User-writable directory where the engine caches uncompressed and
    temporary files. Defaults to a subdirectory of the current
    directory.

<!-- end list -->

  - **GemRBPath**=PATH  
    Path to the GemRB installation. (To be obsoleted; preset at build
    time).

<!-- end list -->

  - **GUIScriptsPath**=PATH  
    Path to the directory with scripts controlling the game's GUI. (To
    be obsoleted; preset at build time).

<!-- end list -->

  - **GemRBOverridePath**=PATH  
    Path where GemRB looks for its game override directory. It defaults
    to *GemRBPath*. GemRB reuses some of the unused files from the
    original or replaces them and this is the where they can be found.
    The path is preset at build time. This directory has the highest
    priority when searching, so putting files in the game override will
    not affect them. Use another directory and add it as *ModPath* to
    the GemRB config.

<!-- end list -->

  - **GemRBUnhardcodedPath**=PATH  
    Path where GemRB looks for its unhardcoded engine data. It defaults
    to *GemRBPath*. The original games hardcoded this information in the
    engine. The path is preset at build time.

<!-- end list -->

  - *The following variables do not need to be altered, unless you are
    doing something really special\!*  

<!-- end list -->

  - **SavePath**=PATH  
    Path to the directory with save games. Note that this directory has
    to contain *save/* and/or eventually *mpsave/* subdirectories and
    that only these subdirectories contain the actual saved games.

*SavePath* defaults to *GamePath*.

  - **GameDataPath**=PATH  
    Path to the original game's installed data files, relative to
    GamePath. Usually it's *data*.

<!-- end list -->

  - **GameOverridePath**=PATH  
    Path to the original game's override dir, relative to GamePath.
    Usually it's *override*. Original games use this directory to place
    last-minute patches.

<!-- end list -->

  - **GameCharactersPath**=PATH  
    Path to the original game's installed data files, relative to
    GamePath. Usually it's *characters*.

<!-- end list -->

  - **GamePortraitsPath**=PATH  
    Path to the original game's installed data files, relative to
    GamePath. Usually it's *portraits*.

<!-- end list -->

  - **GameScriptsPath**=PATH  
    Path to the original game's installed data files, relative to
    GamePath. Usually it's *scripts*.

<!-- end list -->

  - **GameSoundsPath**=PATH  
    Path to the original game's installed data files, relative to
    GamePath. Usually it's *sounds*.

<!-- end list -->

  - **ModPath**=PATH  
    Path where GemRB looks for additional engine override files. It is
    not set by default. This directory has precedence over
    *GemRBOverridePath*.

  - **CustomFontPath**=PATH  
    Path where GemRB looks for additional font files. It is meant to be
    used with the TTF font plugin and fonts.2da as a way to specify
    where to look for system or other external fonts. Check the online
    documentation for the details. It is not set by default.

# Input Parameters:

  - **DoubleClickDelay**=INT  
    Millisecond threshold for detecting a double click. The default is
    250.

<!-- end list -->

  - **RepeatKeyDelay**=INT  
    Millisecond threshold for detecting a repeated key press. The
    default is 250.

<!-- end list -->

  - **UseSoftKeyboard**=(0|1)  
    Toggles use of software keyboard on devices that support one. It
    pops up when text input is required. Disabled by default.

<!-- end list -->

  - **NumFingScroll**=(2|3|4)  
    Number of fingers for multitouch to trigger scrolling. The default
    is 2.

<!-- end list -->

  - **NumFingKboard**=(2|3|4)  
    Number of fingers for multitouch to open up the software keyboard.
    The default is 3. The value should not be equal to *NumFingScroll*
    above.

<!-- end list -->

  - **NumFingInfo**=(2|3|4)  
    Number of fingers for multitouch to emulate a special keypress (alt,
    tab). The default is 2.

<!-- end list -->

  - **MouseFeedback**=(0-3)  
    Bitfield with reserved bits for disabling the mouse. Show
    mouse+tooltips = 0 (default) Hide mouse = 1 Hide tooltips = 2 Hide
    mouse+tooltips = 3

  - **TouchInput**=(0-1)
    Override setting for when autodetection does not have satisfactory results.
     * Autodetect         = -1 (default)
     * Force disable      = 0
     * Enable             = 1


# Development parameters:

  - **EnableCheatKeys**=(0|1)  
    This parameter is meant for developers. If set to *1*, certain keys
    allow you to inspect the internal state of objects, do forbidden
    things, etc. The keys are listed in the *CheatKeys.txt* file. Do NOT
    use this option unless you want to make your hands dirty :-). The
    default is *0*.

  - **DrawFPS**=(0|1)  
    This parameter is meant for developers. If set to *1*, the current
    FPS (Frames per Second) value is drawn in the top left window
    corner. The default is *0*.

<!-- end list -->

  - **DebugMode**=(n)  
    This parameter is meant for developers. It is a combination of bit
    values

*1* - count references,

*2* - display cutscene warnings,

*4* - display variable warnings,

*8* - display action warnings,

*16* - display trigger warnings.

*32* - enable views debug mode.

*64* - enable window debug mode.

*128* - enable font debug mode.

*256* - enable text debug mode.

*512* - enable pathfinding debug mode.

The default is *0*.

  - **DelayPlugin**=FILENAME  
    Named plugin will be loaded after other (nondelayed) plugins were
    loaded. *FILENAME* is a name without path, but with extension, for
    example *libNullSound.so* or *libNullSound.dll*. You can use this
    parameter more than once.

<!-- end list -->

  - **SkipPlugin**=FILENAME  
    Named plugin will not be loaded. *FILENAME* is a name without path,
    but with extension, for example *libNullSound.so* or
    *libNullSound.dll*. You can use this parameter more than once.

<!-- end list -->

  - **SaveAsOriginal**=(0|1)  
    Set this parameter to *1*, if you want to keep the save game
    compatible with the original engine. It is enabled by default.

<!-- end list -->

  - **KeepCache**=(0|1)  
    Set this parameter to *1*, if you want to keep the cache after
    exiting GemRB. It is disabled by default.

<!-- end list -->

  - **GamepadPointerSpeed**=INT
    Pointer movement speed with gamepads. The default is 10.

  - **VitaKeepAspectRatio**=(0|1)
    If set to *1*, original aspect ratio is preserved while game area is scaled to native PS Vita resolution. It is enabled by default.


# FILES

  - **@SYSCONF\_DIR@/gemrb.cfg**  
    system-wide configuration file

<!-- end list -->

  - **@DATA\_DIR@/unhardcoded/**  
    directory with **GemRB**-distributed data files. These used to be
    hardcoded in the original engine. The files are sorted into
    directories for specific games.
    
<!-- end list -->

  - **@DATA\_DIR@/override/**  
    directory with **GemRB**-distributed data files. These files
    override their namesakes in the original data.

<!-- end list -->

  - **@DATA\_DIR@/GUIScripts/**  
    directory with Python scripts providing GUI setup and interaction.
    The files are sorted into directories for specific games.

<!-- end list -->

  - **\~/.gemrb/gemrb.cfg**  

  - **\~/.gemrb/override/**  

  - **\~/.gemrb/GUIScripts/**  
    user's own configuration and data files.

  - **\~/.gemrb/cache/**  
    cache directory

# BUGS

Many. **GemRB** is still in development stage and not complete.

If you stumble over something which is supposed to work but doesn't,
file an issue at https://github.com/gemrb/gemrb or first visit the 
official IRC channel *\#GemRB* on the FreeNode IRC network.

# AUTHOR

The GemRB Project development team at https://gemrb.org

# COPYING

Copyright (C) 2003-2021 The GemRB Project

This program is free software; you can redistribute it and/or modify it
under the terms of the GNU General Public License as published by the
Free Software Foundation; either version 2 of the License, or (at your
option) any later version.

This program is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU General
Public License for more details.

You should have received a copy of the GNU General Public License along
with this program; if not, write to the Free Software Foundation, Inc.,
51 Franklin Street, Fifth Floor, Boston, MA 02110-1301, USA.
