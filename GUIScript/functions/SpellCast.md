---
title: SpellCast
module: GemRB
---

**Prototype:** GemRB.SpellCast (PartyID, Type, Spell[, ResRef])

**Description:** Makes PartyID cast a spell of Type. This handles targeting 
and executes the appropriate scripting command.

**Parameters:**
  * PartyID - player character's index in the party
  * Type    - switch between casting modes:
    * spell(book) type bitfield (1-mage, 2-priest, 4-innate and iwd2 versions)
    * -1: don't cast, but reinit the GUI spell list
    * -2: cast from a quickspell slot
    * -3: cast directly, does not require the spell to be memorized
  * Spell   - spell's index in the memorised list
  * ResRef  - (optional) spell resref for type -3 casts

**Return value:** N/A

**See also:** [UseItem](UseItem.md)

