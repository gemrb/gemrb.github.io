---
title: SaveGame
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.SaveGame (savegame, description[, version])
**Prototype:** GemRB.SaveGame (position[, version])

**Description:** Saves the current game. If version is given, it will save 
to a specific SAV version.

**Parameters:**
  * position - the saved game's index; 0 and 1 are reserved
  * savegame - a save game python object (GetSaveGames)
  * description - the string that will also appear in the filename
  * version - an optional SAV version override

**Return value:** N/A

**Example:** 
  GemRB.SaveGame (10, 'After meeting Dhall')

**See also:** [LoadGame](LoadGame.md), [SaveCharacter](SaveCharacter.md)
