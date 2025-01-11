---
title: GetEffects
module: GemRB
---

**Prototype:** GemRB.GetEffects (globalID, opcode)

**Description:** Returns a list of effects on the target matching opcode. Used for the contingency window.

**Parameters:**
  * globalID - the player character's index in the party
  * opcode  - the effect opcode (for values see effects.ids)

**Return value:** tuple of dicts with these keys derived from the effect:
  * Param1: first parameter
  * Param2: second parameter
  * Resource1
  * Resource2
  * Resource3
  * Spell1Icon: icon of the first resource if it is a spell
  * Spell2Icon: icon of the second resource if it is a spell
  * Spell3Icon: icon of the third resource if it is a spell

**See also:** [ApplyEffect](ApplyEffect.md), [CountEffects](CountEffects.md), [ModifyEffect](ModifyEffect.md)

