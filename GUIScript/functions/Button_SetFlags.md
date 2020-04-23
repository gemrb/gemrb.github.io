---
title: Button_SetFlags
module: _GemRB
---

**Prototype:** GemRB.SetButtonFlags (WindowIndex, ControlIndex, Flags, Operation)

**Metaclass Prototype:** SetFlags (Flags, Operation)

**Description:** Sets the Display Flags of a Button. 

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * Flags - various bits altering the behaviour of the control
    * IE_GUI_BUTTON_NO_IMAGE   = 0x00000001, no button image set by SetButtonSprites
    * IE_GUI_BUTTON_PICTURE    = 0x00000002, has picture set by other SetButton* commands
    * IE_GUI_BUTTON_SOUND      = 0x00000004, clicking the button has a sound
    * IE_GUI_BUTTON_CAPS       = 0x00000008, uppercase the button label
    * IE_GUI_BUTTON_CHECKBOX   = 0x00000010, it is a checkbox
    * IE_GUI_BUTTON_RADIOBUTTON= 0x00000020, it is a radio button
    * IE_GUI_BUTTON_DEFAULT    = 0x00000040, it is the default button
    * IE_GUI_BUTTON_DRAGGABLE  = 0x00000080, the image of the button is draggable?
  * Operation - bit operation to perform on the current button flags

**Return value:** N/A

**Examples:**

    GemRB.SetButtonFlags (window, button, IE_GUI_BUTTON_CHECKBOX, OP_OR)
This command will make the button behave like a checkbox.

    Button.SetFlags (IE_GUI_BUTTON_NO_IMAGE, OP_NAND)
This command will re-enable the images of the button (making it visible).

**See also:** [Button_SetSprites](Button_SetSprites.md), [Button_SetPicture](Button_SetPicture.md), [Button_SetBAM](Button_SetBAM.md), [bit_operation](bit_operation.md)
