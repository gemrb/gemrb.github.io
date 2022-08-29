---
title: CreatePlayer
module: GemRB
---

**Prototype:** CreatePlayer (CREResRef, Slot [,Import, VersionOverride])

**Description:** Adds an actor (PC) to the current game. It works only 
after a LoadGame() was executed, and should be used before an EnterGame(). 
It is also used to import a .chr file as a PC. A new character will need 
additional SetPlayerStat() and FillPlayerInfo() calls to be a working 
character. 
Note: if the slot is already filled, it will delete that pc instead!

**Parameters:**
  * CREResRef - name of the creature to use, usually 'charbase'
  * Slot      - The player character's position in the party
  * Import    - Set it to 1 if you want to import a .chr instead of creating a new character
  * VersionOverride - Force CRE version of new actor.

**Return value:** the new player's index in the game structure

**Examples:**

    MyChar = GemRB.GetVar ('Slot')
    GemRB.CreatePlayer ('charbase', MyChar)

The above example will create a new player character in the slot selected
by the Slot variable.

    MyChar = GemRB.GetVar ('Slot')
    ImportName = 'avenger'
    GemRB.CreatePlayer (ImportName, MyChar, 1)

The above example would import avenger.chr into the slot selected by the 
Slot Variable. If it exists in the Characters directory of the game.

**See also:** [LoadGame](LoadGame.md), [EnterGame](EnterGame.md), [QuitGame](QuitGame.md), [FillPlayerInfo](FillPlayerInfo.md), [SetPlayerStat](SetPlayerStat.md)
