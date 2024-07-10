---
title: GameGetSelectedPCSingle
module: GemRB
---

**Prototype:** GemRB.GameGetSelectedPCSingle ([flag=0])

**Description:** If flag is 0 or omitted, then returns currently active pc 
in non-walk environment (i.e. in shops, inventory, ...).  If flag is set to 
non-zero, then returns the currently speaking PC. 

**Parameters:**
  * flag - 0/1

**Return value:** PartyID (1-10) or 0 if there is no such PC

**See also:** [GameSelectPC](GameSelectPC.md), [GameSelectPCSingle](GameSelectPCSingle.md)
