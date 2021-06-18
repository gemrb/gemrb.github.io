---
title: GetPlayerPortrait
module: GemRB
---

**Prototype:** GemRB.GetPlayerPortrait (Slot[, SmallOrLarge])

**Description:** Queries the player's portrait. To set the portrait of a 
new character you must use FillPlayerInfo().

**Parameters:**
  * Slot         - the PC's position in the party
  * SmallOrLarge - boolean, specify 1 if you want to get the large portrait

**Return value:** dict
  * Sprite - the player's portrait (image)
  * ResRef - the portrait's name (image resref)

**See also:** [FillPlayerInfo](FillPlayerInfo.md)

