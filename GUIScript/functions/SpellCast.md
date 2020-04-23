---
title: SpellCast
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.SpellCast (PartyID, Type, Spell)

**Description:** Makes PartyID cast a spell of Type. This handles targeting 
and executes the appropriate scripting command. If type is -1, then the 
castable spell list will be deleted and no spell will be cast.

**Parameters:**
  * PartyID - player character's index in the party
  * Type    - spell type bitfield (1-mage, 2-priest, 4-innate)
  * Spell   - spell's index in the memorised list

**Return value:** N/A

**See also:** [UseItem](UseItem.md)

