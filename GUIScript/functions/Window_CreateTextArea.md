---
title: Window_CreateTextArea
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.CreateTextArea (WindowIndex, ControlID, x, y, w, h, font, alignment)

**Metaclass Prototype:** CreateTextArea (ControlID, x, y, w, h, font, alignment)

**Description:** Creates and adds a new TextArea to a Window. Used 
in PST MapNote editor. The maximum length of the edit field is 500 characters.

**Parameters:**
  * WindowIndex - the value returned from LoadWindow
  * ControlID   - the new control will be available via this controlID
  * x,y,w,h     - X position, Y position, Width and Height of the control
  * font        - font BAM ResRef
  * alignment   - text alignment

**Return value:** N/A

**See also:** [Window_CreateLabel](Window_CreateLabel.md), [Window_CreateMapControl](Window_CreateMapControl.md), [Window_CreateWorldMapControl](Window_CreateWorldMapControl.md), [Window_CreateButton](Window_CreateButton.md), [Window_CreateTextEdit](Window_CreateTextEdit.md)
