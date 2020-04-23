---
title: GetMemorizedSpellsCount
module: GemRB
---

**Prototype:** GemRB.GetMemorizedSpellsCount (globalID, SpellType, Level, Castable)

**Description:** Returns number of spells of given type and level in 
selected character's memory. If level is negative then it returns the 
number of distinct spells memorised.

**Parameters:**
  * globalID  - party ID or global ID of the actor to use
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the memorized spell's level
  * Castable  - ignore depleted spells?

**Return value:** numeric

**See also:** [GetMemorizedSpell](GetMemorizedSpell.md), [GetKnownSpellsCount](GetKnownSpellsCount.md)
