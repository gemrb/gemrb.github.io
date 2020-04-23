---
title: CanUseItemType
module: GemRB
---

**Prototype:** GemRB.CanUseItemType (slottype, itemname[, actor, equipped])

**Description:** Checks the itemtype vs. slottype, and also checks the 
usability flags vs. actor's stats (alignment, class, race, kit etc.)

**Parameters:**
  * slottype    - the slot to check (See ie_slots.py)
  * itemname    - the resource reference of the item
  * actor       - the actor's PartyID (if 0, skips actor checks)
  * equipped    - whether the item is equipped (if so, don't consider disabled items to be unusable)

**Return value:** boolean

**See also:** [DropDraggedItem](DropDraggedItem.md), [UseItem](UseItem.md)
