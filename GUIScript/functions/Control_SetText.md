---
title: Control_SetText
module: _GemRB
---

**Prototype:** GemRB.SetText (WindowIndex, ControlIndex, String|Strref)

**Metaclass Prototype:** SetText (String|Strref)

**Description:** Sets the Text of a control in a Window. In case of 
strrefs, any tokens contained by the string will be resolved. (For 
example the substring '<CHARNAME>' will be replaced by the 'CHARNAME' 
token.) -1 is a special Strref, it will be resolved to the name/version 
of the running engine.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * String - an arbitrary string
  * Strref - a string index from the dialog.tlk table.

**Return value:** 0 on success, -1 otherwise

**See also:** [Control_QueryText](Control_QueryText.md), [DisplayString](DisplayString.md), [Window_GetControl](Window_GetControl.md)
