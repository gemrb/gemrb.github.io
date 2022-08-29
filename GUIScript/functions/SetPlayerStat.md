---
title: SetPlayerStat
module: GemRB
---

**Prototype:** GemRB.SetPlayerStat (globalID, ID, Value[, PCF])

**Description:** Sets a player character's base stat. The stats are listed 
in ie_stats.py.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * ID - Stat index
  * Value - New stat value
  * PCF - Set to 0 if you don't want the stat's post-change function to be ran

**Return value:** N/A

**Examples:** 

    PickedColor = ColorTable.GetValue (ColorIndex, GemRB.GetVar('Selected'))
    GemRB.SetPlayerStat (pc, IE_MAJOR_COLOR, PickedColor)

The above example sets the player's color just picked via the color customisation dialog. ColorTable holds the available colors.

**See also:** [GetPlayerStat](GetPlayerStat.md), [SetPlayerName](SetPlayerName.md), [ApplyEffect](ApplyEffect.md)
