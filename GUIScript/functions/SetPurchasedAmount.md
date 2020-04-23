---
title: SetPurchasedAmount
module: GemRB
---

**Prototype:** GemRB.SetPurchasedAmount (Index, Amount[, type])

**Description:** Sets the amount of purchased items of a type. If it is 0, 
then the item will be deselected from the purchase list. This function 
works only with an active store.

**Parameters:**
  * Index  - the store item's index
  * Amount - a numeric value not less than 0
  * type - set to non-zero to affect right-hand store (bag)

**Return value:** N/A

**See also:** [EnterStore](EnterStore.md), [LeaveStore](LeaveStore.md), [SetPurchasedAmount](SetPurchasedAmount.md)

