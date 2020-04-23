---
title: CheckFeatCondition
module: GemRB
---

**Prototype:** GemRB.CheckFeatCondition (partyslot, a_stat, a_value, b_stat, b_value, c_stat, c_value, d_stat, d_value[, a_op, b_op, c_op, d_op])

**Description:** Checks if a party character is eligible for a feat. The 
formula is: (stat[a]~a or stat[b]~b) and (stat[c]~c or stat[d]~d). Where ~ 
is a relational operator. If the operators are omitted, the default 
operator is >=.

**Parameters:**
  * partyslot - the characters position in the party
  * a_stat ... d_stat - stat IDs
  * a_value ... d_value - stat value limits
  * a_op ... d_op - operator to use for comparing x_stat to x_value

**Return value:** bool

**See also:** [GetPlayerStat](GetPlayerStat.md), [SetPlayerStat](SetPlayerStat.md)

