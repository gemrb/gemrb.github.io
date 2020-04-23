---
title: LoadGame
module: GemRB
---

**Prototype:** GemRB.LoadGame (index[, version])

**Description:**
Loads a saved game. This must be done before party creation. 
You must set the variable called PlayMode before loading a game (see SetVar). 
The game won't be loaded before the current GUIScript function returns!

**Parameters:**
  * index - the saved game's index, -1 means new game.
  * version - optional version to override some buggy default savegame versions
  * PlayMode (variable) - 0 (single player), 1 (tutorial), 2 (multi player)

**Return value:** N/A

**Example:**

      GemRB.SetVar ('PlayMode', 0)
      GemRB.LoadGame (-1, 22)

**See also:** [EnterGame](EnterGame.md), [CreatePlayer](CreatePlayer.md), [SetVar](SetVar.md), [SaveGame](SaveGame.md)

