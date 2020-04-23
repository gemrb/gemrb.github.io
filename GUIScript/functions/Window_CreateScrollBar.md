---
title: Window_CreateScrollBar
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.CreateScrollBar (WindowIndex, ControlID, x, y, w, h, ResRef)

**Metaclass Prototype:** CreateScrollBar (ControlID, x, y, w, h, ResRef)

**Description:** Creates and adds a new ScrollBar to a Window.

**Parameters:**
  * WindowIndex - the window control
  * ControlID - the id of the new control
  * x, y - position
  * w - width
  * h - height
  * ResRef - the resref for the sprite set

**Return value:** ControlIndex

**See also:** [ScrollBar_SetDefaultScrollBar](ScrollBar_SetDefaultScrollBar.md), [Control_AttachScrollBar](Control_AttachScrollBar.md)
