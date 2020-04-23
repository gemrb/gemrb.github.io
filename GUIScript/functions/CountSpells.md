---
title: CountSpells
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.CountSpells (PartyID, SpellName, SpellType, Flag)

**Description:** Returns number of memorized spells of given name and type 
in PC's spellbook. If flag is set then spent spells are also count.

**Parameters:**
  * PartyID   - the PC's position in the party
  * SpellName - spell to count
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Flag      - count depleted spells too?

**Return value:** integer

**See also:** [GetMemorizableSpellsCount](GetMemorizableSpellsCount.md)
