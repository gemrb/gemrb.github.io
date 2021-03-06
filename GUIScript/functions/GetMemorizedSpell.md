---
title: GetMemorizedSpell
module: GemRB
---

**Prototype:** GemRB.GetMemorizedSpell (PartyID, SpellType, Level, Index)

**Description:** Returns dict with specified memorized spell from PC's spellbook.

**Parameters:** 
  * PartyID   - the PC's position in the party
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the memorized spell's level
  * Index     - the memorized spell's index

**Return value:** dictionary
  * 'SpellResRef' - The name of the spell (.spl resref)
  * 'Flags'       - Is the spell castable, or already spent

**See also:** [GetMemorizedSpellsCount](GetMemorizedSpellsCount.md)

