---
title: Window_CreateTextEdit
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.CreateTextEdit (WindowIndex, ControlID, x, y, w, h, font, text)

**Metaclass Prototype:** CreateTextEdit (ControlID, x, y, w, h, font, text)

**Description:** Creates and adds a new TextEdit field to a Window. Used 
in PST MapNote editor. The maximum length of the edit field is 500 characters.

**Parameters:**
  * WindowIndex - the value returned from LoadWindow
  * ControlID   - the new control will be available via this controlID
  * x,y,w,h     - X position, Y position, Width and Height of the control
  * font        - font BAM ResRef
  * text        - initial text

**Return value:** N/A

**See also:** [Window_CreateLabel](Window_CreateLabel.md), [Window_CreateMapControl](Window_CreateMapControl.md), [Window_CreateWorldMapControl](Window_CreateWorldMapControl.md), [Window_CreateButton](Window_CreateButton.md)
