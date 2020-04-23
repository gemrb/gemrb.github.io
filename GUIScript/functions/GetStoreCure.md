---
title: GetStoreCure
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetStoreCure (index)

**Description:** Gets the spell resref, price and description of a store 
cure referenced by the index.

**Parameters:**
  * index - the number of the cure in the store list

**Return value:** dictionary
  * 'CureResRef'  - the ResRef of the cure spell
  * 'Description' - the StrRef of the spell's description
  * 'Price'       - the price of the spell (subtract this from the party gold)

**See also:** [EnterStore](EnterStore.md), [GetStoreDrink](GetStoreDrink.md), [GetStore](GetStore.md)
