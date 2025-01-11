---
title: Button_SetActionIcon
module: _GemRB
---

**Metaclass Prototype:** SetActionIcon (Dict, ActionIndex[, Function])

**Description:** Sets up an action button based on the guibtact table. 
The ActionIndex should be less than 34. This action will set the button's 
image, the tooltip and the push button event handler.

**Parameters:**
  * Dict - the environment you want to have access to
  * ActionIndex - the row number in the guibtact.2da file
  * Function - function key to assign

**Return value:** N/A

**See also:** [Button_SetSpellIcon](Button_SetSpellIcon.md), [Button_SetItemIcon](Button_SetItemIcon.md)
