---
title: SetupQuickSpell
module: GemRB
---

**Prototype:** GemRB.SetupQuickSpell (globalID, spellslot, spellindex, type)

**Description:** Set up a quick spell slot of a PC. It also returns the 
target type of the selected spell.

**Parameters:**
  * globalID - global ID of the actor to use
  * spellslot - quickspell slot to use
  * spellindex - spell to assign
  * type - spell(book) type (255 means any)

**Return value:** integer, target type constant

