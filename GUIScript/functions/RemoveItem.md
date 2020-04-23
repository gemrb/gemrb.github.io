---
title: RemoveItem
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.RemoveItem (PartyID, Slot[, Count])

**Description:** Removes and destroys an item in an actor's inventory. This 
works even if the item is cursed or indestructible. If an item has charges 
it decreases the charge count instead.

**Parameters:**
  * PartyID - the PC's position in the party
  * Slot    - The inventory slot index of the item
  * Count   - the number of items

**Return value:** boolean, 1 on success

**See also:** [CreateItem](CreateItem.md)
