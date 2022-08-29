---
title: GetAbilityBonus
module: GemRB
---

**Prototype:** GemRB.GetAbilityBonus (stat, column, value[, ex])

**Description:** Returns ability based values from different .2da files.

**Parameters:**
  * stat   - a stat ID, like IE_STR
  * column - integer, the column index of the value in the .2da file:
    * **IE_STR:** 0 - To hit, 1 - Damage, 2 - Open doors, 3 - Weight allowance
    * **IE_INT:** 0 - learn spell, 1 - max spell level, 2 - max spell number on level
    * **IE_DEX:** 0 - reaction adjustment, 1 - missile,  2 - AC
    * **IE_CON:** 0 - normal hp, 1 - warrior hp, 2 - minimum hp roll, 3 - hp regen rate, 4 - fatigue
    * **IE_CHR:** 0 - reaction
    * **IE_LORE:** 0 - lore bonus (int+wis based)
    * **IE_REPUTATION:** 0 - reaction (chr+reputation based)
    * **IE_WIS:** 0 - percentile xp bonus
  * value - stat value to check with
  * ex - extra stat value to check with (used for extended strength)

**Return value:** -9999 if the parameters are illegal, otherwise the required bonus

**See also:** [SetPlayerStat](SetPlayerStat.md), [GetPlayerStat](GetPlayerStat.md), [Table_GetValue](Table_GetValue.md)
