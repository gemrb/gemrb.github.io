---
title: GameGetSelectedPCSingle
module: GemRB
---

**Prototype:** GemRB.GameGetSelectedPCSingle (flag)

**Description:** If flag is 0 or omitted, then returns currently active pc 
in non-walk environment (i.e. in shops, inventory, ...).  If flag is set to 
non-zero, then returns the currently speaking PC. 
If there is no such PC, then returns 0.

**Parameters:**
  * flag - 0/1

**Return value:** PartyID (1-10)

**See also:** [GameSelectPC](GameSelectPC.md), [GameSelectPCSingle](GameSelectPCSingle.md)
