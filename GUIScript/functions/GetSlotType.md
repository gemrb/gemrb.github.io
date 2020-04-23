---
title: GetSlotType
module: GemRB
---

**Prototype:** GemRB.GetSlotType (idx[, PartyID])

**Description:** Returns dictionary of an itemslot type (slottype.2da).

**Parameters:**
  * idx - a row number of slottype.2da
  * PartyID - optional actor ID for a richer dictionary

**Return value:** dictionary
'Type'   - bitfield, The inventory slot's type.
'ID'     - the gui button's controlID which belongs to this slot.
'Tip'    - the tooltip resref for this slot.
'ResRef' - the background .bam of the slot.

**See also:** [Button_SetItemIcon](Button_SetItemIcon.md)

