---
title: SetPlayerName
module: GemRB
---

**Prototype:** GemRB.SetPlayerName(Slot, Name[, LongOrShort])

**Description:** Sets the player name. Each actor has 2 names, this 
command can set either or both.

**Parameters:**
  * Slot - numeric, the character's slot
  * Name - string, the name
  * LongOrShort - 0 (both), 1 (short), 2 (long)

**Return value:** N/A

**Examples:**

    GemRB.SetPlayerName (MyChar, GemRB.GetToken('CHARNAME'), 0)

In the above example we set the player's name to a previously set Token (global string).

**See also:** [Control_QueryText](Control_QueryText.md), [GetToken](GetToken.md)
