---
title: View_SetFrame
module: _GemRB
---

**Prototype:** View_SetFrame (GView, frameRect)

**Metaclass Prototype:** SetFrame (frameRect)

**Description:** Set the View's frame to the specified region.

**Parameters:**
  * GView - the control's reference
  * frameRect - a dict with x, y, w, h keys denoting the frame origin and size

**Examples:**

    StartWindow.SetFrame ({ 'x': 0, 'y': 0, 'h': 300, 'w': 300 })

**See also:** [GetFrame](GetFrame.md)

**Return value:** N/A
