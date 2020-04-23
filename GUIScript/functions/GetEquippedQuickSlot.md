---
title: GetEquippedQuickSlot
module: GemRB
---

**Prototype:** GemRB.GetEquippedQuickSlot (PartyID[, NoTrans])

**Description:** Returns the quickweapon slot index or the inventory slot.

**Parameters:**
  * PartyID - the PC's position in the party (1 based)
  * NoTrans - which equipped slot to return?
    * 0 - return the inventory slot
    * 1 - return the quickweapon slot index

**Return value:** numeric

**See also:** [SetEquippedQuickSlot](SetEquippedQuickSlot.md), [GetEquippedAmmunition](GetEquippedAmmunition.md)

