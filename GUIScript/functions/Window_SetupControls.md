---
title: Window_SetupControls
module: _GemRB
---

**Prototype:** GemRB.SetupControls (WindowIndex, dict, slot[, Start])

**Metaclass Prototype:** SetupControls (Slot[, Start])

**Description:** Sets up all 12 action buttons for a player character, 
based on preset preferences and the character's class.

**Parameters:**
  * WindowIndex - the buttons' window index
  * Slot        - the player character's index in the party
  * Start       - action offset

**Return value:** N/A

**See also:** [Button_SetActionIcon](Button_SetActionIcon.md), [SetDefaultActions](SetDefaultActions.md), [Window_SetupEquipmentIcons](Window_SetupEquipmentIcons.md)
