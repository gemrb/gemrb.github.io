---
title: GetContainerItem
module: GemRB
---

**Prototype:** GemRB.GetContainerItem (PartyID, index)

**Description:** Returns the container item referenced by the index. If 
PartyID is 0 then the container was opened manually and should be the 
current container. If PartyID is not 0 then the container is autoselected 
and should be at the feet of the player.

**Parameters:**
  * PartyID - the PC's position in the party
  * index   - the item's index in the container

**Return value:** dictionary
  * 'ItemResRef' - the ResRef of the item
  * 'ItemName'   - the StrRef of the item's name (identified or not)
  * 'ItemDesc'   - the StrRef of the item's description (identified or not)
  * 'Usages0'    - The primary charges of the item (or the item's stack amount if the item is stackable).
  * 'Usages1'    - The secondary charges of the item.
  * 'Usages2'    - The tertiary charges of the item.
  * 'Flags'      - Item flags.

**See also:** [GetContainer](GetContainer.md), [GameGetFirstSelectedPC](GameGetFirstSelectedPC.md), [GetStoreItem](GetStoreItem.md)

