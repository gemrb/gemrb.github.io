---
title: GetStoreItem
module: GemRB
---

**Prototype:** GemRB.GetStoreItem (index[, righthand])

**Description:** Gets the item resref, price and other details of a store 
item referenced by the index. In case of PST stores the item's availability 
is also checked against the availability triggers.

**Parameters:**
  * index - the number of the item in the store list
  * righthand - set to non-zero to query the right-hand store (bag) instead

**Return value:** dictionary
  * 'ItemResRef' - the ResRef of the item
  * 'ItemName'   - the StrRef of the item's name (identified or not)
  * 'ItemDesc'   - the StrRef of the item's description (identified or not)
  * 'Price'      - the price of the item (subtract this from the party gold)
  * 'Amount'     - the amount of item in store (-1 means infinite)
  * 'Usages0'    - The primary charges of the item (or the item's stack amount if the item is stackable).
  * 'Usages1'    - The secondary charges of the item.
  * 'Usages2'    - The tertiary charges of the item.
  * 'Flags'      - Item flags.
  * 'Purchased'  - The count of purchased items of this type.

**See also:** [EnterStore](EnterStore.md), [GetStoreDrink](GetStoreDrink.md), [GetStoreCure](GetStoreCure.md), [GetStore](GetStore.md), [GetSlotItem](GetSlotItem.md)

