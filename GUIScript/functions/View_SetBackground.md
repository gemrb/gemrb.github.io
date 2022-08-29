---
title: View_SetBackground
module: _GemRB
---

**Prototype:** View_SetBackground (GView, ResRef|Color|None)

**Metaclass Prototype:** SetBackground (ResRef|Color|None)

**Description:** Set the background image or color for the View.

**Parameters:**
  * GView - the control's reference
  * ResRef - name of the image to use
  * Color - a dict with colors to use for a plain fill
  * None - if the None object is passed, the background is cleared

**Examples:**

    StartWindow.SetBackground ('STARTOLD')
    consoleOut.SetBackground ({'r' : 0, 'g' : 0, 'b' : 0, 'a' : 128})
    NoteLabel.SetBackground (None)

**Return value:** N/A
