---
title: ChangeContainerItem
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.ChangeContainerItem (PartyID, slot, action)

**Description:** Moves an item from PC's inventory into a container or vice 
versa. If PartyID is 0 then PC is the first selected PC and container is 
the current container. If PartyID is not 0 then the container is the pile 
at the feet of that PC.

**Parameters:**
  * PartyID - the PC's position in the party
  * slot    - the item's inventory or container slot
  * action
    * 0 - put item of PC into container
    * 1 - get item from container and put it in PC's inventory

**Return value:** N/A

**See also:** [GetContainer](GetContainer.md), [GetSlotItem](GetSlotItem.md)

