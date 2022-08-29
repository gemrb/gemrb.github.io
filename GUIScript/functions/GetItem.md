---
title: GetItem
module: GemRB
---

**Prototype:** GemRB.GetItem (ResRef[, PartyID])

**Description:** Returns dictionary with the specified item's data.

**Parameters:**
  * ResRef - the resource reference of the item

**Return value:** dictionary
  * 'ItemName'           - strref of unidentified name.
  * 'ItemNameIdentified' - strref of identified name.
  * 'ItemDesc'           - strref of unidentified description.
  * 'ItemDescIdentified' - strref of identified description.
  * 'ItemIcon'           - the item's icon (.bam resref)
  * 'DescIcon'           - the description icon
  * 'BrokenItem'         - the replacement item (used for items with broken sounds)
  * 'MaxStackAmount'     - maximum stackable amount
  * 'Dialog'             - item dialog (.dlg resref)
  * 'DialogName'         - the item dialog name
  * 'Price'              - the base item price
  * 'Type'               - the item type (see itemtype.2da)
  * 'AnimationType'      - the item animation ID
  * 'Exclusion'          - the exclusion bit (used by eg. magic armor and rings of protection).
  * 'LoreToID'           - the required lore to identify the item
  * 'MaxCharge'          - the maximum amount of charges
  * 'Tooltips'           - the item tooltips
  * 'Locations'          - the item extended header's ability locations
  * 'Spell'              - the spell's strref if the item is a copyable scroll
  * 'Function'           - returns special function
    * 0 - no special function
    * 1 - item is a copyable scroll (2nd header's 1st feature is 'Learn spell')
    * 2 - item is a drinkable potion 
    * 4 - item is a container
    * 8 - item has selectable abilities (headers)

**See also:** [GetSlotItem](GetSlotItem.md), [GetSpell](GetSpell.md), [Button_SetItemIcon](Button_SetItemIcon.md)
