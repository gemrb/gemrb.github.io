---
title: Button_SetActionIcon
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetActionIcon (Window, Button, Dict, ActionIndex[, Function])

**Metaclass Prototype:** SetActionIcon (ActionIndex[, Function])

**Description:** Sets up an action button based on the guibtact table. 
The ActionIndex should be less than 34. This action will set the button's 
image, the tooltip and the push button event handler.

**Parameters:**
  * WindowIndex, ControlIndex - the button's reference
  * ActionIndex - the row number in the guibtact.2da file
  * Function - function key to assign

**Return value:** N/A

**See also:** [Button_SetSpellIcon](Button_SetSpellIcon.md), [Button_SetItemIcon](Button_SetItemIcon.md), [Window_SetupControls](Window_SetupControls.md)
