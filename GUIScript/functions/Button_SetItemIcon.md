---
title: Button_SetItemIcon
module: _GemRB
---

**Metaclass Prototype:** SetItemIcon (ITMResRef[, Type, Tooltip, ITM2ResRef, BAM3ResRef]])

**Description:** Sets Item icon image on a Button control.

**Parameters:**
  * ITMResRef                 - the name of the item (.itm resref)
  * Type                      - the icon's type
    * 0 - Inventory Icon1
    * 1 - Inventory Icon2
    * 2 - Description Icon (for BG)
    * 3 - No Icon (empty slot)
    * 4 - Activation Icon1
    * 5 - Activation Icon2
    * 6 - Item ability icon for first extended header
    * 7 - Item ability icon for second extended header
    * 8 - etc.
  * Tooltip  - if set to 1, the tooltip for the item will also be set
  * ITM2ResRef - if set, a second item to display in the icon. ITM2 is drawn first. The tooltip of ITM is used. Only valid for Type 4 and 5
  * BAM3ResRef - if set, a third image will be stacked on top of the others

**Return value:** N/A

**See also:** [Button_SetSpellIcon](Button_SetSpellIcon.md), [Button_SetActionIcon](Button_SetActionIcon.md)
