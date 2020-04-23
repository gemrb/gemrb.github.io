---
title: MemorizeSpell
module: GemRB
---

**Prototype:** GemRB.MemorizeSpell (PartyID, SpellType, Level, Index[, Enabled])

**Description:** Memorizes specified known spell. If Enabled is set, the 
spell will be ready for use.

**Parameters:**
  * PartyID   - the PC's position in the party
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the known spell's level
  * Index     - the known spell's index
  * Enabled   - defaults to 0, which means the spell is depleted

**Return value:** boolean, 1 on success.

**See also:** [GetKnownSpell](GetKnownSpell.md), [UnmemorizeSpell](UnmemorizeSpell.md)
