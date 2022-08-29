---
title: View_SetResizeFlags
module: _GemRB
---

**Prototype:** View_SetResizeFlags (GView, Flags[, Operation])

**Metaclass Prototype:** SetResizeFlags (Flags[, Operation])

**Description:** Sets the resize flags of a View.

**Parameters:**
  * GView - the control's reference
  * Flags - the bits to enable
  * Operation - the bit operation to use, defaults to SET

**Examples:**

    TextArea.SetResizeFlags (IE_GUI_VIEW_RESIZE_ALL, OR)

**Return value:** boolean marking success or failure
