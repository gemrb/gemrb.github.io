---
title: SetupQuickSlot
module: GemRB
---

**Prototype:** GemRB.SetupQuickSlot (globalID, quickSlotID, actionID)

**Description:** Changes the action assigned to the specified action bar button.
It only changes it for the specified creature, so it does not use the class 
default any more. This is only used in iwd2.

**Parameters:**
  * globalID - the PC's position in the party (1 based) or global ID
  * quickSlotID - the quickslot (button) to set up (0-11) or -1 to revert all to class defaults
  * actionID - the actionbar action id to assign to this quickslot

**Return value:** N/A

**See also:** [SetupQuickItemSlot](SetupQuickItemSlot.md), [SetEquippedQuickSlot](SetEquippedQuickSlot.md)

