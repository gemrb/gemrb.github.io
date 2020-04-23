---
title: GetKnownSpellsCount
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetKnownSpellsCount (PartyID, SpellType[, Level])

**Description:** Returns number of known spells of given type and level in 
a player character's spellbook. If Level isn't given, it will return the 
number of all spells of the given type.

**Parameters:**
  * PartyID   - the PC's position in the party
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the known spell's level

**Return value:** numeric

**See also:** [GetMemorizedSpellsCount](GetMemorizedSpellsCount.md), [GetKnownSpell](GetKnownSpell.md)

