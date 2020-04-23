---
title: GetSlots
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetSlots (PartyID, SlotType[, Flag])

**Description:** Returns the tuple of slots of a PC matching the SlotType 
criteria.

**Parameters:**
  * PartyID - a PC
  * SlotType - bitfield, the inventory slot's type (32768 means inventory)
  * Flag (defaults to 1)
    * <0 - returns empty slots
    * 0  - returns all slots.
    * >0 - returns filled slots

**Return value:** tuple

**See also:** [GetSlotType](GetSlotType.md)

