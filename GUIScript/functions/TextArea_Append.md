---
title: TextArea_Append
module: _GemRB
---

**Prototype:** GemRB.TextAreaAppend (WindowIndex, ControlIndex, String|Strref [, Row[, Flag]])

**Metaclass Prototype:** Append (String|Strref [, Row[, Flag]])

**Description:** Appends the Text to the TextArea Control in the Window. 
If row is specificed, it can also append text to existing rows.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * String - literal text, it could have embedded colour codes
  * Strref - a string index from the dialog.tlk table.
  * Row - the row of text to add the text to, if omitted, the text will be added (in a new row) after the last row.
  * Flag - the flags for QueryText (if strref resolution is used)
    * 1 - strrefs displayed (even if not enabled by default)
    * 2 - sound (plays the associated sound)
    * 4 - speech (works only with if sound was set)
    * 256 - strrefs not displayed (even if allowed by default)

**Return value:** Index of the row appended or changed

**See also:** [TextArea_Clear](TextArea_Clear.md), [Control_SetText](Control_SetText.md), [Control_QueryText](Control_QueryText.md)
