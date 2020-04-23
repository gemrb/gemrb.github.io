---
title: CreateItem
module: GemRB
---

**Prototype:** GemRB.CreateItem (PartyID, ItemResRef, [SlotID, Charge0, Charge1, Charge2])

**Description:** Creates item in the inventory of the player character.

**Parameters:** 
  * PartyID    - the PC's position in the party
  * ItemResRef - the item's name (.itm resref)
  * SlotID     - Inventory Slot (-1 means any backpack slot)
  * Charge0-2  - the item's stack amount/charges

**Return value:** N/A
