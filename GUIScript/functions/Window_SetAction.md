---
title: Window_SetAction
module: _GemRB
---

**Metaclass Prototype:** SetAction (PythonFunction, EventType)

**Description:** Ties an event of a control to a python function

**Parameters:** 
  * PythonFunction - a callback for when the event occurs.
  * EventType - the event type to bind to.

**Return value:** N/A

**Examples:**

    Bar.SetAction (OnWindowClose, ACTION_WINDOW_CLOSED)
    ...
    def OnWindowClose (Window):
      ...

**See also:** [Control_SetAction](Control_SetAction.md)
