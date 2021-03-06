---
title: New game
toc: true
---

GemRB is an open game engine, freely available for modification. So it is natural
that people wonder and sometimes want to create new games. Even some smaller studios
approached the project before, but in the end nothing came of it.

What follows is a collection of what little existing work has been done towards a
new and Free game. Some of it has been integrated into the bundled tech demo. See
[#313](https://github.com/gemrb/gemrb/issues/313)
for a growing list of things that need to be done to round it up. The list hasn't
been there since the begining, but nonetheless aims to be comprehensive.

## Creating a new game

This page should serve as a list of needed things and ideas for creating
a trivial GemRB dataset (aka "game").

The goal is to create a completely free (in the OSS sense) dataset which
could be distributed with GemRB and also serve as a reference for
writing comprehensive content creation documentation. Preferably it could be done
with free tools, so that the process is repeatable by users.

### Options

There used to be a project called DragonLance Total Conversion (DLTC)
whose goal was to create a complete game for the (original) IE engine.
Unfortunately it's not useful for us, because the licence was certainly
not free and it required the original datasets to a large degree. It's
now dead, but the files are still available.

### Needed Resources

Due to the Free/Libre software nature of GemRB, some disclaimers
[apply](http://gibberlings3.net/forums/topic/9615-a). No original data
can be redistributed, so for any Free game effort, the art has to be
done **from scratch** (modifying the original art does not exempt it).
The game data **is** the biggest issue, since the engine can be extended
much more easily from our (coder's) point of view. Scripting,
story-telling and dialog is also something the modding community is well
versed in, so it all comes down to classical art.

This includes at minimum _area backgrounds,
character animations, gui skins, various icons (and cursors)_,
music and sounds. While this amounts to a lot of work, do not forget
that some appropriate art already exists out there (eg.
**[this](http://opengameart.org/)** or
[this](http://search.freegamedev.net/) and
[this](http://soundbible.com/)) and possibly just needs a conversion
to one of the IE formats.

But, there is also some self initiative shown and we already have some
new character animations (one of the hardest/most tedius things to do):

  - [this one](https://gibberlings3.net/forums/topic/21396-a) by
    deepinthewoods (including some spell effects)
  - [this one](https://gibberlings3.net/forums/topic/20190-a),
    [converted](http://opengameart.org/content/big-one-character) by
    joc-wi
  - a full workflow is being drafted [on this wiki page](https://github.com/gemrb/gemrb/wiki/Production-workflow-for-sprite-creation)
    and its linked bug

Also area graphics:

  - [18 iwd-style areas](http://gibberlings3.net/forums/topic/23598-a)
    by Aranthor

Here's a discussion about the [details of creating
them](https://gibberlings3.net/forums/topic/20189-a). You can also find a
begining of a [3d modelling tutorial
here](http://www.bhaalspawn.org/3d.html), with a focus on area graphics.

**So, to create a new game, both more artists and some coordinators are needed, since there
is a lot that can be salvaged from existing efforts.** Additional programming is the
smallest of the problems.

To see what a minimal playable dataset looks like, inspect the bundled demo in `demo/data`.

Potentially these item description and portrait graphics could be used
(consult the author): <http://ruloc.deviantart.com/gallery/?offset=72>

The custom BAMs for armor and helmet were created by Tantalus for his
[Sarevok Recovery Mod](http://www.baldursgate-refugium.de/mods/sarevok-wiederherstellung/),
licensed under CC BY-NC-SA 3.0 by Nicolas Peters.

For various [icons these CC-BY](https://game-icons.net/) licensed ones
could be used.

### Audio

In order of importance:
  - area music, intro music
  - sfx: gui click/press, window open/close, 
  - game mechanic effect sounds
  - voice acting: selection/command sounds

Much of this can be reused from other open game art projects until
better versions are made, as needed\&available.

Camille from hvnrecordings (see forum) studio is interested in helping
out once the other parts of the project are working well.

<http://soundimage.org/> (original and free)

Look up Nox Arcana on YouTube for ideas :-)

<https://www.youtube.com/user/AdrianvonZiegler> (original and
conceptually free for non-commercial)

### Other

  - GemRB internals are currently tied to the PlayerCharacter structure,
    which makes us depend on AD\&D rules to some degree. Greater
    separation would be better, like moving things (if possible) to a
    plugin.
  - Use the bundled demo as a starting point
  - WRT the ruleset, Pathfinder and most D&D editions are licensed under
    the Open Game License
  - WRT the setting, not much thought was given to it, but there are
    also (semi)free ones out there like
    [Porphyra](http://www.rpgnow.com/browse.php?keywords=Porphyra&x=-1052&y=-161&author=&artist=&pfrom=&pto=)


### Lists of ideas for a new game

#### Mystery of Fangdoodle
You've discovered a town with a mystery. What is it? Which mystery? Why is everyone here scared to do anything?

Characters
 - Samuel L. Fortune Teller Loosely based off of Samuel L. Jackson (the one character in every movie who's sure to lead everyone to safety), this fortune teller can impart no useful information, other than a couple ominous warnings… Though he's getting impressively rich off of doing just that, promising everyone that if they come back next week, he'll be able to tell them exactly what's lurking in their Mysterious future.

Locations
 - Dale of Fangdoodle The dale of Fangdoodle is a silly little place, where nothing much happens… Because the residents are scared to do anything. They've long ago forgotten what the mystery is, and are absolutely afraid of setting off whatever horrific consequences might come from upsetting it.

Items
 - Sam's Crystal Ball - The Mysterious crystal ball that Samuel L. uses ceaselessly - though rumor has it that it's not actually his…
 - Night's Rest in a Bottle - Upon quaffing this fantastically horrible tasting brew, characters will feel as rested as a full 8 hours of sleep. Restrictions/Disadvantages: Drinking more than one of them in a row will disorient and aggressively confuse the character until a full 8 hours of rest is actually had - a side effect of the excessive stimulants and horrid taste. Limits: 1 between rests. Some characters will refuse to drink it because of its disgusting odor. Acquiring method: Bought from alchemists with proper supplies. Only major alchemical operations can acquire the ingredients necessary to make the foul tasting brew. Graphical Representation: Probably a pure black bottle… Hinting at something evil inside.


## Other technicalities

1.  When you need to use existing GemRB actions, add their
    (bg2/iwd2/desired) signature to `data/action.ids`. Same holds true
    for trigger, instant, object and effect IDS files. You can look them up on
    [IESDP](https://gibberlings3.github.io/iesdp/).
2.  You can add new strings to dialog.tlk with `WeiDU --nogame --strapp
    "String1" demo/dialog.tlk --tlkout demo/dialog.tlk` and look them up
    with `WeiDU --nogame --string 1 demo/dialog.tlk`.
3.  New actor animations require new entries to avatars.2da with a
    matching animation id and type.
4.  See this wiki page with [various asset creation notes](https://github.com/gemrb/gemrb/wiki/Asset-creation-notes).
