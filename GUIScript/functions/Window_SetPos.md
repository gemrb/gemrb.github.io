---
title: Window_SetPos
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetWindowPos (WindowIndex, X, Y, [Flags=WINDOW_TOPLEFT])

**Metaclass Prototype:** SetPos (X, Y, [Flags=WINDOW_TOPLEFT])

**Description:** Moves a Window.

**Parameters:** 
  * WindowIndex - the index returned by LoadWindow()
  * X,Y - placement of the window, see Flags below for meaning for each flag
  * Flags - bitmask of WINDOW_TOPLEFT (etc.), used to modify the meaning of X and Y.
    * TOPLEFT  : X, Y are coordinates of upper-left corner.
    * CENTER   : X, Y are coordinates of window's center.
    * ABSCENTER: window is placed at screen center, moved by X, Y.
    * RELATIVE : window is moved by X, Y.
    * SCALE    : window is moved by diff of screen size and X, Y, divided by 2.
    * BOUNDED  : the window is kept within screen boundaries.

**Note:** All flags except WINDOW_BOUNDED are mutually exclusive

**Return value:** N/A

**Example:**
    x, y = GemRB.GetVar ('MenuX'), GemRB.GetVar ('MenuY')
    GemRB.SetWindowPos (Window, x, y, WINDOW_CENTER | WINDOW_BOUNDED)

The above example is from the PST FloatMenuWindow script. It centers 
pie-menu window around the mouse cursor, but keeps it within screen.

**See also:** [Window_SetSize](Window_SetSize.md), [Control_SetPos](Control_SetPos.md)
