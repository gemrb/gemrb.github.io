---
title: ModifyEffect
module: GemRB
---

**Prototype:** GemRB.ModifyEffects (PartyID, opcode, x, y)

**Description:** Changes/sets the target coordinates of the specified effect. 
This command is used for the farsight spell.

**Parameters:**
  * PartyID - the player character's index in the party
  * opcode  - the effect opcode (for values see effects.ids)
  * x       - target x coordinate
  * y       - target y coordinate

**Return value:** N/A

**See also:** [ApplyEffect](ApplyEffect.md), [CountEffects](CountEffects.md)

