---
title: Modding
toc: true
---

GemRB works with mods for the original games, which should work out of the
box ([let us know](https://github.com/gemrb/gemrb/issues/new/choose) otherwise).
Of course, any that modify the EXE files could lack the functionality those hacks achieved.

Additionally, there are cool mods that are only possible with GemRB and can be found in this
[mod repository](https://github.com/lynxlynxlynx/gemrb-mods). The most famous one of them is
the 10 player party mod, enabling larger adventuring parties.

Lastly, GemRB made many aspects of the games configurable by editing text files. What
follows is a list of mod ideas, with the simpler ones requiring minimal effort on your
part. Many have been gathered in the [**gemrb-tweaks**](https://github.com/lynxlynxlynx/gemrb-mods/tree/master/gemrb-tweaks)
mod for an easier install and have been removed from this list.

## Installing mods

If you're new to modding IE games, first install the latest release of
[WeiDU](https://github.com/WeiDUorg/weidu/releases). It's a tool that allows
several mods to be installed at once, even if they modify the same files. Most
mods already bundle the Windows version — this will be the EXE file in the 
downloaded mod. You can run it to trigger the install.

Each mod has to be extracted to the game dir, so there's one folder per mod.
Then you just run it through WeiDU to install: `weinstall somemodfolder`.

## Mod ideas

Separated by difficulty/time requirement. If you don't know how doable
is your idea, just write it here and someone else will categorise it.

### Trivial

These mods are just configuration tweaks or file drop-ins. A few game
tweaks can be achieved by simply toggling variables in gemrb.ini ([check
the note in the
introduction](https://github.com/gemrb/gemrb/blob/master/gemrb/docs/en/gemrb_ini.txt#L21-L26)
to learn about the candidates).

Some of the table editing can be more complex due to the data involved.
For example, to add brand new spells to the wild surge table, one would
also have to create them first, not just replace the existing entries.

  - divine spellcaster classes with sorcerer style spellcasting -
      - just set the booktype to 3 in the gemrb `clskills.2da` (caveat: it
        will affect every npc with that class)
  - different and extra boni for weapon styles 
      - just edit `unhardcoded/ws*.2da` as you see fit
  - different wild surges: just edit `unhardcoded/wildmag.2da`
      - replace spell resrefs with your own and/or add modifiers
          - check `Scriptable::HandleHardcodedSurge` to see how the
            extra modifiers work (+ and all the numbers)
  - different wild magic casting level modifications: arbitrarily extend `unhardcoded/wildmag.2da` (column limit was removed)
  - spell icon sorting in the action bar: just edit `unhardcoded/shared/spldisp.2da`
  - different damage and/or XP boni/mali for game difficulty levels: just edit `unhardcoded/*/difflvls.2da`
  - simplified "concentration" ala ToBEx — just set
    SimplifiedDisruption=1 in gemrb.ini
  - autocast any memorized self-targetting spells on rest (stoneskin
    anyone?)
      - add their resref to `splspec.2da` and use a value of 8
  - game is not over if protagonist dies (only if the whole party does)
      - in `GUIScripts/bg/*/Game.py` change protagonist
        mode from 1 to 2 (`GemRB.GameSetProtagonistMode(2)`)
  - change the class restrictions for extraordinary strength (bgs,
    iwd1):
      - just edit 0 to 1 of STREXTRA in `unhardcoded/*/classes.2da`
  - change how many spells mages and bards get for free at character
    generation
      - just edit `unhardcoded/*/splwizkn.2da` (or `splbrdkn.2da`)
  - different monk ac/apr progression: just change `unhardcoded/bg2/monkbon.2da`
  - different turn undead level differences, reputation cut-off points for falling, default AC/save/attack dice size (`unhardcoded/shared/miscrule.2da`)
  - XP award for successful pickpocketing: add a line with the awards to the existing `xpbonus.2da`
  - change animation based immunity to wing buffet: modify `wingbuff.2da`

### Easy

  - monk/sorcerer kits: normal kit process for creation
      - barbarian kits are not possible, since they are fighter kits
        themselves
  - quickload button on the startup screen for the games that lack it
      - edit start.chu to add the button
      - edit all the `Start.py` scripts to use it and make it quickload
        (see iwd2 for the code)
  - different layout for the PST modron maze
      - change `unhardcoded/pst/easymaze.2da` (or others when they become
        available)
      - for more complications also change `GUIScript/pst/Maze.py`
  - new feats for iwd2
    * edit `feats.2da`
    * create the wanted spell to be applied (like with class abilities)
    * if you want something more complex like Critical Strike, code changes will be needed, pushing this into the hard category
* new formations:
  * edit/extend `unhardcoded/*/formatio.2da` (the easiest way by modifying `admin/make_formation.py`)
* spontaneous casting for other games or spellbook types (in iwd2 it works only for cleric spells, not even domain):
  - create a table like `sponcast.2da` (iwd2) with the target replacement spells
  - put its name in the SPONCAST column of `unhardcoded/*/clsskills.2da` for whichever class you want
* more racial enemies in iwd2
  * just extend `unhardcoded/iwd2/haterace.2da` (IDS column is from [race.ids](http://gemrb.org/iesdp/files/ids/iwd2/race.htm))
  * add new strings for name and description as necessary (column 1 and 3)
* resting movies in games that don't have them or have only one (bg1)
  * get appropriate videos
  * create/edit `restmov.2da` in a similar shape that bg2 already has, referencing the videos
  
### Medium

  - a new race
      - add all the required text strings (`races.2da`)
      - decide which avatars will be (re)used and calculate the
        animation ids
      - decide which-if-any bonuses the race will grant (original 2das +
        `dsrace.2da`)
  - subraces in bg2
      - write a new guiscript with a borrowed window pack from the kit
        selection
      - add subrace boni/mali
  - new multi/dual class choices
      - update a bunch of tables in the gemrb and game overrides
        (`classes.2da` and clskills.2da being the most important)
          - the MULTI column can be computed with this formula:
            `1<<(ID1-1) | 1<<(ID2-1) | 1<<(ID3-1)` (where the ids are
            the singleclass values in the ID column)
      - add missing tables (eg. clabxxxx.2da) and strings
      - maybe there'll be a need to update some game scripts
      - currently you'd still have to **share the usability flags** with
        some other combo
      - multiclasses are tiny bit easier, since you can skip a few
        tables
  - x-in-y games (like bg2 in iwd2)
      - no mixing with pst, due to large differences in control ids and
        strings
      - swap the guiscript folders and possibly some of the files in the
        gemrb override
      - swap / update `gemrb.ini`
  - character name generator
      - the only reason this is under medium and not easy is the fact
        that you have to create a long list of possible names or words
        and combination rules
  - Limit the number of attacks based on the Weapon's Speed Factor. A
    combat round is split into 10 segments. When a weapon has a SF of 7,
    supposedly you need a time of 7/10 of a round in order to swing it
    because it is heavy. How is it possible to swing it 4 times in that
    time ? I would love to limit the APR based on the weapon's SF. That
    way, you need a weapon with a SF \<= 5 in order to have 2 APR, a SF
    \<= 3 to have 3APR, etc.
      - check balance, warrior APR bonus and spell effect interference

### Hard

  - making infravision useful - decrease the visual and other ranges in
    the dark
      - this one would require engine and possibly ingame script changes
  - make all multiclass combinations possible (except for barbarians, of
    course)
      - this would mostly be about automating the multiclass addition
        mentioned in the previous section

## Modding on Mac

Since the extra game data, including the GemRB override directory, is
inside the app bundle, when you need to modify an override file you will
need to right click the application and select “Show Package Contents”
and navigate to `Contents/Resources/override`.

## Notes to modders

Since WeiDU 247 you don't have to treat GemRB any differently than the rest of the games.
Once GemRB is ran on an installed game, it will leave a `gemrb_path.txt` file in the top
game directory (alongside keymap.ini) with the path to engine files. WeiDU will then
automatically use that for extra search paths. You can also check for this file manually
if you need to do any GemRB-only operations.

For the curious, here is a table of the common paths involved. If you find a reason to
mod something in gemrb/override, do let us know.

|                   | files present ingame | moddable?                   | search order |
| ----------------- | -------------------- | --------------------------- | ------------ |
| game/override     | yes                  | weidu                       | 2            |
| gemrb/override    | yes                  | manual* / weidu+ModPath | 1            |
| gemrb/unhardcoded | no                   | weidu                       | 3            |

\* *requires write access to where gemrb is installed*
