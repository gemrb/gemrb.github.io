---
title: ChangeItemFlag
module: GemRB
---

**Prototype:** GemRB.ChangeItemFlag (PartyID, slot, flags, mode)

**Description:** Changes the flags of an inventory slot. For example, 
identifies an item.

**Parameters:**
  * PartyID - the PC's position in the party (1 based)
  * slot    - inventory slot
  * flags   - a bitfield, same as the GetSlotItem flags
    * IE_INV_ITEM_IDENTIFIED    = 0x01 - the item is identified
    * IE_INV_ITEM_UNSTEALABLE   = 0x02 - the item is unstealable
    * IE_INV_ITEM_STOLEN        = 0x04 - the item is marked as stolen
    * IE_INV_ITEM_UNDROPPABLE   = 0x08 - the item is undroppable (dragitem fails)
    * IE_INV_ITEM_ACQUIRED      = 0x10 - the item was recently acquired
    * IE_INV_ITEM_DESTRUCTIBLE  = 0x20 - the item is removable
    * IE_INV_ITEM_EQUIPPED      = 0x40 - the item is equipped
    * IE_INV_ITEM_STACKED       = 0x80 - the item is a stacked item
  * mode    - binary operation type

**Return value:** Returns 0 if the item was not found, 1 otherwise.

**See also:** [GetSlotItem](GetSlotItem.md)
