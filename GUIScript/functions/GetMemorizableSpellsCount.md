---
title: GetMemorizableSpellsCount
module: GemRB
---

**Prototype:** GemRB.GetMemorizableSpellsCount (PartyID, SpellType, Level[, Bonus])

**Description:** Returns number of memorizable spells of given type and 
level in a player character's spellbook.

**Parameters:**
  * PartyID   - the PC's position in the party
  * SpellType - 0 - priest, 1 - wizard, 2 - innate
  * Level     - the memorized spell's level
  * Bonus     - whether querying the (wisdom) modified or the base value

**Return value:** numeric, -1 if the query is invalid (no spellcaster, bad spelltype, too high level).

**See also:** [SetMemorizableSpellsCount](SetMemorizableSpellsCount.md)

