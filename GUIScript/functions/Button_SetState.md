---
title: Button_SetState
module: _GemRB
---

**Metaclass Prototype:** SetState (State)

**Description:** Sets the state of a Button Control. Doesn't work if the button 
is a checkbox or a radio button though, their states are handled internally.

**Parameters:**
  * State - the new state of the button:
    * IE_GUI_BUTTON_ENABLED    = 0x00000000, default state
    * IE_GUI_BUTTON_UNPRESSED  = 0x00000000, same as above
    * IE_GUI_BUTTON_PRESSED    = 0x00000001, the button is pressed
    * IE_GUI_BUTTON_SELECTED   = 0x00000002, the button stuck in pressed state
    * IE_GUI_BUTTON_DISABLED   = 0x00000003, the button is disabled 
    * IE_GUI_BUTTON_LOCKED     = 0x00000004, the button is inactive (like DISABLED, but processes MouseOver events and draws UNPRESSED bitmap)
    * IE_GUI_BUTTON_FAKEDISABLED      = 0x00000005, draws DISABLED bitmap, but it isn't disabled
    * IE_GUI_BUTTON_FAKEPRESSED     = 0x00000006, draws PRESSED bitmap, but it isn't shifted

**Return value:** N/A

**See also:** [Button_SetFlags](Button_SetFlags.md)
