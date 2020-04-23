---
title: GetPlayerStat
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetPlayerStat(globalID, StatID[, Base])

**Description:** Queries a stat of the player character. The stats are 
listed in ie_stats.py. For IWD2 skills, it takes all bonuses into account.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * StatID - stat index
  * Base - if set to 1, the function will return the base instead of the modified (current) value

**Return value:** numeric

**See also:** [SetPlayerStat](SetPlayerStat.md), [GetPlayerName](GetPlayerName.md), [GetPlayerStates](GetPlayerStates.md)
