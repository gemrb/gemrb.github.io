---
title: Control_SetAction
module: _GemRB
---

**Metaclass Prototype:** SetAction (PythonFunction, EventType[, Button, Mod, Count])

**Description:** Ties an event of a control to a python function

**Parameters:** 
  * PythonFunction - a callback for when the event occurs.
  * EventType - the event type to bind to.
  * Button - the button of the EventType.
  * Mod - the modifier keys (flags).
  * Count - the repeat count of the event.

**Return value:** N/A

**Examples:**

    Bar.OnEndReached (EndLoadScreen)
    ...
    def EndLoadScreen ():
      Skull = LoadScreen.GetControl (1)
      Skull.SetPicture ('GSKULON')

The above example changes the image on the loadscreen when the progressbar reaches the end.

  Button.SetAction (Buttons.YesButton, IE_GUI_MOUSE_PRESS, 1, 0, 1)
The above example sets up the 'YesButton' function from the Buttons module to be called when the button is pressed with the left mouse button one time.

**See also:** [Window_GetControl](Window_GetControl.md), [Control_SetVarAssoc](Control_SetVarAssoc.md), [SetTimedEvent](SetTimedEvent.md)
