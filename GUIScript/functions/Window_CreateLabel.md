---
title: Window_CreateLabel
module: _GemRB
---

**Prototype:** GemRB.CreateLabel(WindowIndex, ControlID, x, y, w, h, font, text, align)

**Metaclass Prototype:** CreateLabel(ControlID, x, y, w, h, font, text, align)

**Description:** Creates and adds a new Label to a Window.

**Parameters:**
  * WindowIndex - the value returned from LoadWindow
  * ControlID   - the new control will be available via this controlID
  * x,y,w,h     - X position, Y position, Width and Height of the control
  * font        - a .bam resref which must be listed in fonts.2da too
  * text        - initial text of the label (must be string)
  * align       - label text alignment

**Return value:** N/A

**Example:**

    StartWindow.CreateLabel (0x0fff0000, 0,415,640,30, 'EXOFONT', '', 1)
    Label = StartWindow.GetControl (0x0fff0000)
    Label.SetText (GEMRB_VERSION)
The above lines add the GemRB version string to the PST main screen.

**See also:** [Window_CreateButton](Window_CreateButton.md), [Control_SetText](Control_SetText.md)
