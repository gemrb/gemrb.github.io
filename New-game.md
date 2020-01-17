---
title: New game
---

GemRB is an open game engine, freely available for modification. So it is natural
that people wonder and sometimes want to create new games. Even some smaller studios
approached the project before, but in the end nothing came of it.

What follows is a collection of what little existing work has been done towards a
new and Free game.

## New Game

This page should serve as a list of needed things and ideas for creating
a trivial GemRB dataset (aka "game").

The goal is to create a completely free (in the OSS sense) dataset which
could be distributed with GemRB and also serve as a reference for
writing documentation if we ever get to it. Preferably it could be done
with free tools, so that the process is repeatable by users.

#### Options

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

This includes at minimum <span class="underline">area backgrounds,
character animations, gui skins, various icons (and cursors)</span>,
music and sounds. While this amounts to a lot of work, do not forget
that some appropriate art already exists out there (eg
**[this](http://opengameart.org/)** or
[this](http://search.freegamedev.net/) and
[this](http://soundbible.com/)) and possibly *just* needs a conversion
to one of the IE formats.

But, there is also some self initiative shown and we already have some
new character animations (one of the hardest/most tedius things to do):

  - [this one](http://gibberlings3.net/forums/topic/21396-a) by
    deepinthewoods (including some spell effects)
  - [this one](http://gibberlings3.net/forums/topic/20190-a),
    [converted](http://opengameart.org/content/big-one-character) by
    joc-wi

Also area graphics:

  - [18 iwd-style areas](http://gibberlings3.net/forums/topic/23598-a)
    by Aranthor

Here's a discussion about the [details of creating
them](http://gibberlings3.net/forums/topic/20189-a). You can also find a
begining of a [3d modelling tutorial
here](http://www.bhaalspawn.org/3d.html), with a focus on area graphics.

There's a special [namespace](/newgame/capabilities) (folder) on our
wiki, where myownlittlworld
[prepared](http://gibberlings3.net/forums/topic/16245-a) some templates
to get started. It's practically empty now, so you (yes, you) are
encouraged to contribute ideas, wishes etc.

**So, to create a new game or just a demo that can be bundled alongside
GemRB, both more artists and some coordinators are needed, since there
is a lot that can be salvaged from existing efforts.**

  - At least one avatar, preferably two. It does not have to be pretty,
    it just has to be able to express stand and walk animations. Could
    be done in Blender with some GIMP work. The avatars available on the
    net are mostly nonfree, unfortunately.
  - One or two rooms. They could be connected with a door and should
    contain some containers.
  - Item or two.
  - Some simple GUI and associated scripts. If the scripts are simple
    enough, only a small amount of windows is needed - intro screen,
    game window and e.g. inventory window could be enough for a humble
    beginning.
  - Half a dozen of GUI feedback sounds like pushing a button or closing
    a window. At least the former one is needed.
  - Optionally a musical score. It does not have to be a great piece of
    art, something atmospheric would be Good Enough™.
    [audio](/newgame/audio)
  - A minimal set of IDS and 2DA files to make the engine happy.
    Probably a whole lot of them is required now, but in many cases a
    skeletal one would hopefully suffice.
  - TLK and KEY files. Should be trivial to create.

Some of this is already done for the bundled demo stub, so check there
(/demo/data).

Potentially these item description and portrait graphics could be used
(consult the author): <http://ruloc.deviantart.com/gallery/?offset=72>

The custom BAMs for armor and helmet were created by Tantalus for his
Mod "Sarevok Recovery Mod" (
<http://www.baldursgate-refugium.de/mods/sarevok-wiederherstellung/> ),
licensed under CC BY-NC-SA 3.0 by Nicolas Peters.

### Other

  - GemRB internals are currently tied to the PlayerCharacter structure,
    which makes us depend on AD\&D rules to some degree. Greater
    separation would be better, like moving things (if possible) to a
    plugin.
  - Use the bundled demo as a starting point
  - WRT the ruleset, Pathfinder looks promising and is licensed under
    the Open Game License
  - WRT the setting, not much thought was given to it, but there are
    also (semi)free ones out there like
    [Porphyra](http://www.rpgnow.com/browse.php?keywords=Porphyra&x=-1052&y=-161&author=&artist=&pfrom=&pto=)

## Potential New Games

While it would be great to focus development on one game at a time,
ideas often occur for other games that are just too good to let go. This
section is for those ideas, so that they can be recorded and not lost.
If you're submitting a completely new idea, it might be good to see if
your idea can eventually be incorporated with an existing project in
some way, in effect bringing to bear the best traits of both. If you're
going to hassle about licensing issues, please license your content
under the GPL 2 to allow the greatest utility to the GemRB project... If
indeed, you want GemRB to use it.

New game development should be modeled off the [game
template](/newgame/games/template), this gives you an outline and a
couple questions directing you where to start creating an entire world,
it's inhabitants, and major events. Other, more realistically ambitious
templates include: [Plots](/newgame/plots/template),
[Characters](/newgame/characters/template),
[Locations](/newgame/locations/template),
[Items](/newgame/items/template), and
[Capabilities](/newgame/capabilities/template).

If you're filling out a template, you should fill out the sections
relating to the idea you're adding and then provide appropriate links to
the ideas in the other sections (if you're making a character, fill out
the character information, but just provide a link and short description
to the town the character lives in - fill out the town's information on
the town's own page).

### Lists of ideas for a new game

  - [Mystery of Fangdoodle](/newgame/games/Mystery%20of%20Fangdoodle) -
    You've stumbled across a town with a mystery... What is it?

## Technical GemRB start up details

When you run GemRB, here is what happens:

1.  The core initialises, loads all the plugins and preloads some data
2.  The main game loop is started
3.  Start.py in the game's guiscript directory is run
      - LoadGame(None) will set up a new game by loading the default GAM
        file and linked resources
      - Party members can be created with CreatePlayer()
      - EnterGame()
      - ...
4.  MessageWindow.py is run
5.  Game is up and drawing
6.  QuitGame() and Quit() to terminate

Other guiscripts are run on demand, but mostly by direct calls from the
guiscript side.

## Other technicalities

1.  When you need to use existing GemRB actions, add their
    (bg2/iwd2/desired) signature to `data/action.ids`. Same holds true
    for trigger, instant and object IDS files. You can look them up on
    IESDP (see sidebar).
2.  You can add new strings to dialog.tlk with `WeiDU --nogame --strapp
    "String1" demo/dialog.tlk --tlkout demo/dialog.tlk` and look them up
    with `WeiDU --nogame --string 1 demo/dialog.tlk`.
3.  New actor animations require new entries to avatars.2da with a
    matching animation id and type.
