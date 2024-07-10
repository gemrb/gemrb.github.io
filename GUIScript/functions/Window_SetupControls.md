---
title: Window_SetupControls
module: _GemRB
---

**Metaclass Prototype:** SetupControls (Dict, Slot[, Start, Bar])

**Description:** Sets up all 12 action buttons for a player character, 
based on preset preferences and the character's class.

**Parameters:**
  * Dict - the environment you want to have access to
  * Slot        - the player character's index in the party
  * Start       - action offset
  * Bar - a tuple with the action bar buttons to use

**Return value:** N/A

**See also:** [Button_SetActionIcon](Button_SetActionIcon.md), [SetDefaultActions](SetDefaultActions.md), [Window_SetupEquipmentIcons](Window_SetupEquipmentIcons.md)
