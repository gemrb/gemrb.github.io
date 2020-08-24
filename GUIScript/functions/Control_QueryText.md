---
title: Control_QueryText
module: _GemRB
---

**Prototype:** GemRB.QueryText (WindowIndex, ControlIndex[, UseSystemEncoding])

**Metaclass Prototype:** QueryText (UseSystemEncoding=False)

**Description:** Returns the Text of a TextEdit/TextArea/Label control. 
In case of a TextArea, it will return the selected row, not the entire 
textarea.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * UseSystemEncoding - whether returned text should use OS encoding, False by default

**Return value:** string, may be empty

**Example:**

    Name = NameField.QueryText ()
    GemRB.SetToken ('CHARNAME', Name)
The above example retrieves the character's name typed into the TextEdit control and stores it in a Token (a string variable accessible to gamescripts, the engine core and to the guiscripts too).

    GemRB.SetToken ('VoiceSet', TextAreaControl.QueryText ())
The above example sets the VoiceSet token to the value of the selected string in a TextArea control. Later this voiceset could be stored in the character sheet.
If returned string will be used to e.g. as filename, string should be using system encoding, or file might be not found if it contains non-ASCII letters.
**Example**
    Filename = CharImportList.QueryText (True)
    GemRB.CreatePlayer (Filename, MyChar|0x8000, 1)

**See also:** [Control_SetText](Control_SetText.md), [SetToken](SetToken.md), [accessing_gui_controls](accessing_gui_controls.md)
