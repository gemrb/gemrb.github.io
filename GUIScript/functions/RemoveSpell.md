---
title: RemoveSpell
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.RemoveSpell (globalID, SpellType, Level, Index)
**Prototype:** GemRB.RemoveSpell (globalID, SpellResRef)

**Description:** Unlearns a specified known spell.

**Parameters:**
  * globalID  - party ID or global ID of the actor to use
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the known spell's level
  * Index     - the known spell's index
  * SpellResRef - spell resource reference to remove by

**Return value:** boolean, 1 on success

**See also:** [UnmemorizeSpell](UnmemorizeSpell.md), [GetKnownSpellsCount](GetKnownSpellsCount.md), [GetKnownSpell](GetKnownSpell.md), [LearnSpell](LearnSpell.md), [RemoveEffects](RemoveEffects.md)

