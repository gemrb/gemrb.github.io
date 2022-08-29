---
title: SaveCharacter
module: GemRB
---

**Prototype:** GemRB.SaveCharacter (PartyID, filename)

**Description:** Saves (exports) the designated partymember into the Characters 
directory of the game. This character is importable later by a special 
CreatePlayer call.

**Parameters:**
  * PartyID  - the saved character's position in the party
  * filename - the filename of the character

**Return value:** N/A

**Examples:** 

    pc = GemRB.GameGetSelectedPCSingle ()
    GemRB.SaveCharacter (pc, ExportFileName)

The above example exports the currently selected character.

**See also:** [CreatePlayer](CreatePlayer.md)
