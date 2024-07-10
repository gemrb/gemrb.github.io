---
title: Control_SetVarAssoc
module: _GemRB
---

**Metaclass Prototype:** SetVarAssoc (VariableName, LongValue)

**Description:** It associates a variable name and an optionally bounded 
value with a control. 
The control uses this associated value differently, depending on the 
control. See more about this in 'data_exchange'.

**Parameters:**
  * Variablename - string, a Global Dictionary Name associated with the control
  * LongValue - numeric, a value associated with the control
  * min - numeric, minimum range value (optional)
  * max - numeric, maximum range value (optional)

**Return value:** N/A

**Special:** If the 'DialogChoose' variable was set to -1 or 0 during a dialog session, it will terminate (-1) or pick the first available option (0) from the dialog automatically. (0 is used for 'continue', -1 is used for 'end dialogue').

**See also:** [Button_SetFlags](Button_SetFlags.md), [SetVar](SetVar.md), [GetVar](GetVar.md)
