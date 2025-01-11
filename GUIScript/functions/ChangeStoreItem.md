---
title: ChangeStoreItem
module: GemRB
---

**Prototype:** GemRB.ChangeStoreItem (PartyID, slot, action)

**Description:** Performs a buy, sell, identify or steal action. It has the 
same bit values as IsValidStoreItem. It can also toggle the selection of an item.
If a right-hand store is currently loaded, it will be acted upon instead of
the PC's inventory.

**Parameters:**
  * PartyID - the PC's position in the party
  * slot    - the item's inventory or store slot
  * action  - bitfield
    * 1 - buy
    * 2 - sell
    * 4 - identify
    * 8 - steal
    * Add 0x20000 for selection (in case of buy/sell only)

**Return value:**
  * 0 - failure
  * 2 - success

**See also:** [EnterStore](EnterStore.md), [GetSlotItem](GetSlotItem.md), [GetStoreItem](GetStoreItem.md), [IsValidStoreItem](IsValidStoreItem.md)

