---
title: UnmemorizeSpell
module: GemRB
---

**Prototype:** GemRB.UnmemorizeSpell (PartyID, SpellType, Level, Index[, flags])

**Description:** Unmemorizes specified memorized spell. If flags are set, 
they will limit removal to a spell with specified depletion (and the same 
resref as the provided spell).

**Parameters:**
  * PartyID      - the PC's position in the party
  * SpellType    - 0 - priest, 1 - wizard, 2 - innate
  * Level        - the memorized spell's level
  * Index        - the memorized spell's index
  * flags        - optional, remove only an already depleted (1) or non-depleted (2) spell

**Return value:** boolean, 1 on success

**See also:** [MemorizeSpell](MemorizeSpell.md), [GetMemorizedSpellsCount](GetMemorizedSpellsCount.md), [GetMemorizedSpell](GetMemorizedSpell.md)
