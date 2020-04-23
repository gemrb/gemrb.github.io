---
title: LearnSpell
module: GemRB
---

**Prototype:** GemRB.LearnSpell (PartyID, SpellResRef[, Flags, BookType, Level])

**Description:** Tries to learn the specified spell. Flags control xp 
granting, stat checks and feedback.

**Parameters:**
  * PartyID     - the PC's position in the party
  * SpellResRef - the spell's Resource Reference
  * Flags       - bitmap with the following bits (default is 0):
    * 1 - Give XP for learning (Level * 100)
    * 2 - Display message
    * 4 - Check for insufficient stats
    * 8 - Also memorize it
  * BookType - override which spellbook to use
  * Level - override at which level to learn it

**Return value:** integer, 0 on success, nonzero on failure (LSR_*).

**See also:** [MemorizeSpell](MemorizeSpell.md), [RemoveSpell](RemoveSpell.md)

