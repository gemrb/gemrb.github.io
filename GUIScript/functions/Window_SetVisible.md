---
title: Window_SetVisible
module: _GemRB
---

**Prototype:** GemRB.SetVisible (WindowIndex, Visible)

**Metaclass Prototype:** SetVisible (Visible)

**Description:** Sets the Visibility Flag of a Window.
Window index 0 is the game control window (GameWindow python object)

**Parameters:**
  * WindowIndex - the index returned by LoadWindow()
  * Visible:**
    * WINDOW_INVISIBLE - Window is invisible
    * WINDOW_VISIBLE - Window is visible
    * WINDOW_GRAYED - Window is shaded
    * WINDOW_FRONT - Window is drawn in the foreground

**Return value:** N/A

**See also:** [Window_ShowModal](Window_ShowModal.md), [Window_SetFrame](Window_SetFrame.md)
