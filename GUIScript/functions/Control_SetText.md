---
title: Control_SetText
module: _GemRB
---

**Metaclass Prototype:** SetText (String|Strref)

**Description:** Sets the Text of a control in a Window. In case of 
strrefs, any tokens contained by the string will be resolved. (For 
example the substring '<CHARNAME>' will be replaced by the 'CHARNAME' 
token.) -1 is a special Strref, it will be resolved to the name/version 
of the running engine.

**Parameters:**
  * String - an arbitrary string
  * Strref - a string index from the dialog.tlk table.

**Return value:** N/A

**See also:** [Control_QueryText](Control_QueryText.md), [DisplayString](DisplayString.md), [Window_GetControl](Window_GetControl.md)
