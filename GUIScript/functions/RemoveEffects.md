---
title: RemoveEffects
module: GemRB
---

**Prototype:** GemRB.RemoveEffects (globalID, SpellResRef)

**Description:** Removes all effects created by the spell/item named SpellResRef. 
This is useful for removing class abilities (CLAB/HLA AP_* entries).

**Parameters:**
  * globalID  - party ID or global ID of the actor to use
  * SpellResRef - a spell or item resource reference (source of effects)

**Return value:** N/A

**See also:** [RemoveSpell](RemoveSpell.md), [RemoveItem](RemoveItem.md)

