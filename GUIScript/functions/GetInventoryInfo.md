---
title: GetInventoryInfo
module: GemRB
---

**Prototype:** GemRB.GetInventoryInfo (globalID)

**Description:** Returns several details about current slots in the specified actor's inventory

**Parameters:**
  * globalID - the actor's global ID or the PC's position in the party

**Return value:** dictionary
  * 'FistSlot'
  * 'MagicSlot' - The magic slot if a magic weapon was spawned, None othewise.
  * 'WeaponSlot' - The first melee slot.
  * 'UsedSlot' - The equipped slot, the fist slot if nothing is equipped.
  * 'HasEquippedAbilities' - Whether any inventory item is granting a usable ability

**See also:** [GetSlotItem](GetSlotItem.md), [GetItem](GetItem.md)
