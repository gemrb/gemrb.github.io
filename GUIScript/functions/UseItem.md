---
title: UseItem
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.UseItem (globalID, Slot, header[,forcetarget])

**Description:** Makes the actor try to use an item. 
If slot is non-negative, then header is the header of the item in the 'slot'. 
If slot is -1, then header is the index of the item functionality in the use item list. 
If slot is -2, then header is the quickslot index. 
This handles targeting and executes the appropriate scripting command.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * Slot     - item's inventory slot
  * header   - item index from the SetupEquipmentIcons list, an item may have multiple entries, because of multiple features
  * forcetarget - overrides Target number if set

**Return value:** N/A

**See also:** [CanUseItemType](CanUseItemType.md), [SpellCast](SpellCast.md), [Window_SetupEquipmentIcons](Window_SetupEquipmentIcons.md)

