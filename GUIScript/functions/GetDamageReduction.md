---
title: GetDamageReduction
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetDamageReduction (globalID, enchantment[, missile])

**Description:** returns the actor's damage reduction for the specified 
enchantment level and type. Used in iwd2. Can be cancelled by high 
weapon enchantment.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * enchantment - enchantment level (usually 0-5)
  * missile - look at missile reduction, not melee

**Return value:** integer, the amount of resisted damage

**See also:** [GetCombatDetails](GetCombatDetails.md)

