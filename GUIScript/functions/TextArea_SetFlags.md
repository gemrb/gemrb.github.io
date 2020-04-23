---
title: TextArea_SetFlags
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetTextAreaFlags (WindowIndex, ControlIndex, Flags, Operation)

**Metaclass Prototype:** SetFlags (Flags, Operation)

**Description:** Sets the Flags of a TextArea.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * Flags - various bits altering the behaviour of the control
    * IE_GUI_TEXTAREA_AUTOSCROLL   - 0x05000001
    * IE_GUI_TEXTAREA_SMOOTHSCROLL - 0x05000002 slowly scroll contents. If it is out of text, it will call the TEXTAREA_OUT_OF_TEXT callback.
    * IE_GUI_TEXTAREA_HISTORY      - 0x05000004 drop some of the scrolled out text.
  * Operation - bit operation to perform, default is OP_SET.

**Return value:** N/A

**Example:**
    TextAreaControl = SoundWindow.GetControl (45)
    TextAreaControl.SetFlags (IE_GUI_TEXTAREA_HISTORY, OP_OR)
    TextAreaControl.SetVarAssoc ('Sound', 0)
    RowCount = TextAreaControl.GetCharSounds ()
The above code will set up the TextArea as a ListBox control, by reading the names of available character soundsets into the TextArea and setting it up as selectable. When the user clicks on row, the 'Sound' variable will be assigned a row number.

**See also:** [RewindTA](RewindTA.md), [SetTAHistory](SetTAHistory.md), [GetCharSounds](GetCharSounds.md), [GetCharacters](GetCharacters.md), [Control_QueryText](Control_QueryText.md), [accessing_gui_controls](accessing_gui_controls.md), [bit_operation](bit_operation.md)
