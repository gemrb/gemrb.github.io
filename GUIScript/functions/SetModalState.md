---
title: SetModalState
module: GemRB
---

**Prototype:** GemRB.SetModalState (globalID, Value[, spell])

**Description:** Sets an actor's modal state. The modal states are listed 
in ie_modal.py. If 'spell' is not given, it will set a default spell 
resource associated with the state.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * Value - new modal state
  * Spell - the spell resource associated with the state

**Return value:** N/A

**Examples:**
 
    GemRB.SetModalState (pc, MS_TURNUNDEAD)
The above example makes the player start the turn undead action.

**See also:** [SetPlayerStat](SetPlayerStat.md), [SetPlayerName](SetPlayerName.md)

