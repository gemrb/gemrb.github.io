---
title: DropDraggedItem
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.DropDraggedItem (PartyID, Slot)

**Description:** Put currently dragged item to specified PC and slot. Stop 
dragging. Dropping the item in an invalid slot will result in 0. Partial 
success may happen if the item was dropped into a stack, but not all items 
were moved. The dragging status will be removed only after a complete 
success. Not all inventory slots may carry any type of item. The item could 
be dropped in an unspecified inventory slot, the ground, or an equippable 
slot fitting for the item.

**Parameters:**
  * PartyID - the actor's inparty index
  * Slot    - the Inventory Slot or special values:
    * -1 any equippable slot fitting for the item
    * -2 ground
    * -3 any empty inventory slot

**Return value:** integer, 0 (failure), 1 (partial success), 2 (success) or 3 (swapped item)

**See also:** [DragItem](DragItem.md), [IsDraggingItem](IsDraggingItem.md), [CanUseItemType](CanUseItemType.md)

