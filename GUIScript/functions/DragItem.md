---
title: DragItem
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.DragItem (PartyID, Slot, ResRef, [Count=0, Type])

**Description:** Start dragging specified item. If Count is given, it will 
try to split the item. If an  item is already dragged, it won't do 
anything. If Slot is negative, drag the actor's party portrait instead.

**Parameters:**
  * PartyID - the PC's position in the party
  * Slot    - actor index in game structure
  * ResRef  - item name (.itm resref)
  * Count   - stack size (0 means all)
  * Type    - if nonzero, drag from pile at actor's feet instead

**Return value:** N/A

**See also:** [DropDraggedItem](DropDraggedItem.md), [IsDraggingItem](IsDraggingItem.md)
