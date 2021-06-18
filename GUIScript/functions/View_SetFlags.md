---
title: View_SetFlags
module: _GemRB
---

**Prototype:** View_SetFlags (GView, Flags[, Operation])

**Metaclass Prototype:** SetFlags (Flags[, Operation])

**Description:** Sets the general flags of a View.

**Parameters:**
  * GView - the control's reference
  * Flags - the bits to enable
  * Operation - the bit operation to use, defaults to OP_SET

**Examples:**

    Button.SetFlags (IE_GUI_BUTTON_ALIGN_RIGHT | IE_GUI_BUTTON_ALIGN_BOTTOM, OP_OR)
    Window.SetFlags (WF_ALPHA_CHANNEL, OP_NAND)

**Return value:** boolean marking success or failure
