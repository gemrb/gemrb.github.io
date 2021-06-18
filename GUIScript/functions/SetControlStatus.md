---
title: SetControlStatus
module: GemRB
---

**Prototype:** GemRB.SetControlStatus (WindowIndex, ControlIndex, State)

**Metaclass Prototype:** SetStatus (State)

**Description:** Sets the state of a Control. For buttons, this is the 
same as SetButtonState.
For other controls, this command will set the common value of the 
control, which has various uses.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * Button States:**
    * IE_GUI_BUTTON_ENABLED    = 0x00000000, default state
    * IE_GUI_BUTTON_UNPRESSED  = 0x00000000, same as above
    * IE_GUI_BUTTON_PRESSED    = 0x00000001, the button is pressed
    * IE_GUI_BUTTON_SELECTED   = 0x00000002, the button stuck in pressed state
    * IE_GUI_BUTTON_DISABLED   = 0x00000003, the button is disabled 
    * IE_GUI_BUTTON_LOCKED     = 0x00000004, the button is inactive (like DISABLED, but processes MouseOver events and draws UNPRESSED bitmap)
    * IE_GUI_BUTTON_FAKEDISABLED = 0x00000005, draws DISABLED bitmap, but it isn't disabled
    * IE_GUI_BUTTON_FAKEPRESSED = 0x00000006, draws PRESSED bitmap, but it isn't shifted
  * Map Control States (add 0x09000000 to these):
    * IE_GUI_MAP_NO_NOTES   =    0, no mapnotes visible
    * IE_GUI_MAP_VIEW_NOTES =    1, view notes (no setting)
    * IE_GUI_MAP_SET_NOTE   =    2, allow setting notes

**Return value:** N/A

**See also:** [Button_SetState](Button_SetState.md)
