---
title: Control_SetActionInterval
module: _GemRB
---

**Prototype:** _GemRB.Control_SetActionInterval (GControl [,interval])

**Metaclass Prototype:** SetActionInterval ([interval])

**Description:** Sets the tick interval between repeating actions such as a held down mouse button

**Parameters:** 
* interval - the number of ticks between firing actions, default is Control::ActionRepeatDelay

**Return value:** N/A

**Examples:**

Button.SetActionInterval (50)
**See also:** [Control_SetEvent](Control_SetEvent.md)
