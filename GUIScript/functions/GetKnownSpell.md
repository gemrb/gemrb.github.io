---
title: GetKnownSpell
module: GemRB
---

**Prototype:** GemRB.GetKnownSpell (PartyID, SpellType, Level, Index)

**Description:** Returns dictionary with specified known spell from PC's spellbook.

**Parameters:**
  * PartyID   - the PC's position in the party
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the memorized spell's level
  * Index     - the memorized spell's index

**Return value:** dictionary
  * 'SpellResRef' - The name of the spell (.spl resref)

**See also:** [GetMemorizedSpell](GetMemorizedSpell.md)

