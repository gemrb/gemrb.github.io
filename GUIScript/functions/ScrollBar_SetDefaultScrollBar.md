---
title: ScrollBar_SetDefaultScrollBar
module: _GemRB
---

**Prototype:** GemRB.SetDefaultScrollBar (WindowIndex, ControlIndex)

**Metaclass Prototype:** SetDefaultScrollBar ()

**Description:** Sets a ScrollBar as default on a window. If any control 
receives mousewheel events, it will be relayed to this ScrollBar, unless 
there is another attached to the control.

**Parameters:**
  * WindowIndex, ControlIndex - the ScrollBar control's reference

**Return value:** N/A

**See also:** [Control_AttachScrollBar](Control_AttachScrollBar.md)
