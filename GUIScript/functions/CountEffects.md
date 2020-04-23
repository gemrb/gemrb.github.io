---
title: CountEffects
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.CountEffects (globalID, opcode, param1, param2[, resref])

**Description:** Counts how many matching effects are applied on the actor. 
If a parameter is set to -1, it will be ignored.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * opcode   - the effect opcode (for values see effects.ids)
  * param1   - parameter 1 for the opcode
  * param2   - parameter 2 for the opcode
  * resref   - optional resource reference to match the effect

**Return value:** N/A

**Example:**
    res = GemRB.CountEffect (MyChar, 'HLA', -1, -1, AbilityName)

The above example returns how many HLA effects were applied on the character.

**See also:** [ApplyEffect](ApplyEffect.md)
