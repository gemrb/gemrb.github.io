---
title: PrepareSpontaneousCast
module: GemRB
---

**Prototype:** GemRB.PrepareSpontaneousCast (globalID, spellIndex, type, level, spellResRef)

**Description:** Depletes the memorised spell and replaces it with another 
(in memory). WARNING: useful only immediately before casting.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * spellIndex - current spell's index
  * type - spell's booktype
  * level - spell's level
  * spellResRef - replacement spell's resource reference

**Return value:** new spell's spellinfo index
