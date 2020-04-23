---
title: Control_AttachScrollBar
module: _GemRB
---

**Prototype:** GemRB.AttachScrollBar (WindowIndex, ControlIndex, ScrollBarControlIndex)

**Metaclass Prototype:** AttachScrollBar (ScrollBarControlIndex)

**Description:** Attaches a ScrollBar to another control. If the control 
receives mousewheel events, it will be relayed to the ScrollBar. TextArea 
controls will also be synchronised with the scrollbar. If there is a 
single ScrollBar on the window, or the ScrollBar was set with 
SetDefaultScrollBar, this command is not needed.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * ScrollBarControlIndex - the scrollbar's index on the same window

**Return value:** N/A

**See also:** [ScrollBar_SetDefaultScrollBar](ScrollBar_SetDefaultScrollBar.md)
