---
title: GetStore
module: GemRB
---

**Prototype:** GemRB.GetStore ([righthand])

**Description:** Gets the basic header information of the current store and 
returns it in a dictionary.

**Parameters:**
  * righthand - set to non-zero to query the right-hand store (bag) instead

**Return value:** dictionary
  * 'StoreType'       - numeric (see IESDP)
  * 'StoreName'       - the StrRef of the store name
  * 'StoreDrinkCount' - the count of drinks served (tavern)
  * 'StoreCureCount'  - the count of cures served (temple)
  * 'StoreItemCount'  - the count of items sold, in case of PST the availability trigger is also checked
  * 'StoreCapacity'   - the capacity of the store
  * 'StoreOwner   '   - the ID of the owner of the store
  * 'StoreRoomPrices' - a four elements tuple, negative if the room type is unavailable
  * 'StoreButtons'    - a four elements tuple, possible actions
  * 'StoreFlags'      - the store flags if you ever need them, StoreButtons is a digested information, but you might have something else in mind based on these
  * 'TavernRumour'    - ResRef of tavern rumour dialog
  * 'TempleRumour'    - ResRef of temple rumour dialog
  * 'IDPrice'    - price for identification
  * 'Lore'    - lore requirement
  * 'Depreciation'    - price depreciation
  * 'SellMarkup'    - markup for selling
  * 'BuyMarkup'    - markup for buying
  * 'StealFailure'    - chance to succeed at stealing

**See also:** [EnterStore](EnterStore.md), [GetStoreCure](GetStoreCure.md), [GetStoreDrink](GetStoreDrink.md), [GetRumour](GetRumour.md)

