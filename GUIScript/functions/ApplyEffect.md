---
title: ApplyEffect
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.ApplyEffect (globalID, opcode, param1, param2[, resref, resref2, resref3, source, timing])

**Description:** Creates a basic effect and applies it on the actor marked 
by PartyID. 
This function cam be used to add stats that are stored in effect blocks.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * opcode   - the effect opcode (for values see effects.ids)
  * param1   - parameter 1 for the opcode
  * param2   - parameter 2 for the opcode
  * resref   - optional resource reference to set in effect
  * resref2  - (optional) resource reference to set in the effect
  * resref3  - (optional) resource reference to set in the effect
  * resref4  - (optional) resource reference to set in the effect
  * source   - (optional) source to set in the effect
  * timing   - (optional) timing mode to set in the effect

**Return value:** N/A

**Example:**
    for i in range(ProfCount-8):
        StatID = GemRB.GetTableValue (TmpTable, i+8, 0)
        Value = GemRB.GetVar ('Prof '+str(i))
        if Value:
            GemRB.ApplyEffect (MyChar, 'Proficiency', Value, StatID)

The above example sets the weapon proficiencies in a bg2's CharGen9.py script.

**See also:** [SpellCast](SpellCast.md), [SetPlayerStat](SetPlayerStat.md), [GetPlayerStat](GetPlayerStat.md), [CountEffects](CountEffects.md)
