---
title: GetSlotItem
module: GemRB
---

**Prototype:** GemRB.GetSlotItem (PartyID, slot[, translated])

**Description:** Returns dictionary with the specified actor's inventory 
slot data. Or the dragged item if globalID is 0. If translated is nonzero, 
the slot will not be looked up again.

**Parameters:**
  * PartyID   - the PC's position in the party
  * slot      - the item's inventory slot
  * translated - look up the slot again (useful for quickweapons)

**Return value:** dictionary
  * 'ItemResRef' - The name of the item (.itm resref)
  * 'Usages0' - The primary charges of the item (or the item's stack amount if the item is stackable).
  * 'Usages1' - The secondary charges of the item.
  * 'Usages2' - The tertiary charges of the item.
  * 'Flags'   - Item flags:
    * IE_INV_ITEM_IDENTIFIED = 1,   The item is identified.
    * IE_INV_ITEM_UNSTEALABLE = 2,  The item is unstealable.
    * IE_INV_ITEM_STOLEN = 4,       The item is stolen.
    * IE_INV_ITEM_UNDROPPABLE =8,   The item is undroppable.
    * IE_INV_ITEM_ACQUIRED = 0x10,  The item was recently moved.
    * IE_INV_ITEM_DESTRUCTIBLE = 0x20,  The item is removable (sellable or destructible).
    * IE_INV_ITEM_EQUIPPED = 0x40,  The item is currently equipped.
    * IE_INV_ITEM_STACKED = 0x80,   The item is a stacked item.
  * 'Header'  - Item's extended header assigned to the inventory slot (the
  ability to use). Only applicable to quickslots.
  * 'Slot'  - The same as the slot parameter.
  * 'LauncherSlot' - The slot of the launcher, if any, 0 otherwise.

**See also:** [GetItem](GetItem.md), [Button_SetItemIcon](Button_SetItemIcon.md), [ChangeItemFlag](ChangeItemFlag.md)
