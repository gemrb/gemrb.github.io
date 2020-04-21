---
title: Common problems
toc: true
---

GemRB logs its output to a terminal (if ran from one) and to a file — **GemRB.log**.
It's saved to the game directory (GameDir setting) or its SaveDir (save or mpsave) if the first
isn't writable). **This is the first thing you should look into when you have problems.**
Don't worry about printed ERRORS and WARNINGS — when they are critical, they will be fatal.

# Top 4 problems

## 1. GemRB exits just after starting it up.
GemRB needs a [configuration file](/Install.md#configure-gemrb) to know
where to look for the installed game.

If you have it and GemRB sees it (first lines in the log), check the
file again, as you probably have the **GamePath** variable
misconfigured. You can use the CDx paths to add additional search paths
(up to CD6). When in doubt, use absolute paths (beginning with / or the
drive letter). The GemRB log may give you a hint on what is missing.

## 2. After entering a game the area is blue and GemRB quickly crashes.
This is the same problem as the one before. If you check the log, you'll
see we couldn't find the area tilemap (WED file). Fix up the game path.

## 3. The GUI freezes and you can't click anything or there are leftovers from previous screens drawn over the current one.
One of our python guiscripts encountered an error and it just happens to
be on the critical path, so the rest of the code is not being
executed.  

Check the log and search for the first occurrence of "Traceback", which
in the next few lines will show you the actual error. Send us this part
and we should be able to fix it pretty fast.

## 4. Playing X at larger resolutions messes up the GUI. Parts are overlapping and flickering.
You couldn't play the original game at high or random resolutions either. To
fix this, you have to install the [Widescreen
mod](http://www.gibberlings3.net/widescreen/). For IWD install Heart of
Winter too (if it is not preinstalled), since it brought some higher
resolutions and lots of other improvements.

GemRB supports both linear scaling (start in windowed mode and resize the
window, integer factors work best) and an approximation to the widescreen
mod, where we skip the window frames and center the windows to arbitrary
resolutions. The game area is the main thing that increases in size. You
can also increase the font size through mods or using TTF fonts.


# Uncommon problems

## On Windows, compiling in debug mode with MSVC results in wierd linker errors

Probably the python library is the culprit. See [these
posts](http://stackoverflow.com/questions/1236060/compiling-python-modules-whith-debug-defined-on-msvc)
on how to amend that.

## On Windows, a crash occurs right after GemRB created the display (in SetGamma). Using SDL 1.2.13.

Cause: SDL 1.2.13 on Windows has a bug, which was fixed in Revision
\#3533. Get a newer versions of SDL.

## On Windows, a crash occurs right after it tried to initialize OpenAL.

Possible cause: You clicked on another window, pushing the initializing
game into background. This causes OpenAL to fail opening the sound
device, which causes GemRB to fail startup.

Solution: Try running again, without clicking too wildly.

## On Windows, I don't always hear sound, especially when clicking buttons.

Possible cause: You have got a wrong version of OpenAL.

Solution: Install OpenAL Soft 15.1. The best is if you copy
soft\_oal.dll as OpenAL32.dll somewhere on your game's dll path.


# Game bugs
The games are full of complexity which inevitably led to a large amount
of bugs and inconsistencies. You're **advised to install the community
fixpacks** (especially for bg2 and pst) and to consider whether a problem
you're having is from a fault in the data or in GemRB.

Fixpacks for:
- [bg2](https://www.gibberlings3.net/mods/fixes/bg2fixpack/) at Gibberlings3
- [pst](http://www.spellholdstudios.net/ie/pst-fixpack) at Spellhold Studios
- [iwd](https://www.gibberlings3.net/mods/fixes/iwd_fixpack/) at Gibberlings3
- [iwd2](http://www.shsforums.net/files/file/1085-almaterias-iwd2-fixpack/) at Spellhold Studios
- [bg1](https://sasha-altherin.webs.com/baldursgatefixpack.htm) from plainab

Here's a list of bugs that keep getting reported, but are not for us to fix:

  * BG1: Kelddath at the Song of the Morning in Temple (AR3400) should buy
    Wyvern heads (MISC52)- he does not. He gives gp for first one, but
    you can't sell anything in his store. 
      * like any temple, you can't sell stuff there; he is also scripted
        to only accept one wyvern head
  * BG1: Flooding mine (Cha.5) should trigger Wyrm's Crossing opening- does
    it? Here not, but maybe I didn't use elevator (trigger) like I
    should (prior to talking to miner)... (Pure speculation- similar
    thing reported in original, as well as in
    [BGT](http://www.shsforums.net/topic/45020-killing-davaeron-and-going-up-via-lift-do-not-trigger-chapter-5/)
    ).
  * BG2 (fixed by fixpack): in the Slums, the crazy scimitar wielding
    scimitar-thrower breaks your quickslots after attacking you (weapons
    are marked as magic claws and can't be removed)
  * some traps/infopoints are autodetected (already marked as
    detected in the area file)
      - BG2 (fixed by fixpack): bodhi's sanctum left chamber
      - BG1: Bogus trap detected in one of the containers on the upper
        floor in Travenhurst Manor (ar3320-22) in some versions of bg1. 
      - PST: AR0403 - The trapped container at 2350, 2600 shows up red
        when you havent searched for it

For the curious, some data problems and oddities can also be read from this old
[listing](https://github.com/gemrb/gemrb/wiki/The-Infinity-Engine-Games-Walkthrough-Addenda,-Bugs-and-Stuff-Repository).
