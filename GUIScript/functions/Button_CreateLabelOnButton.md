---
title: Button_CreateLabelOnButton
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.CreateLabelOnButton (WindowIndex, ControlIndex, NewID, font, align)

**Metaclass Prototype:** CreateLabelOnButton (NewID, font, align)

**Description:** Creates and adds a new Label to a Window, based on the 
dimensions of an existing button. If the NewID is the same as the old 
button ID, the old button will be converted to this Label (the old button 
will be removed). 

**Parameters:**
  * WindowIndex     - the value returned from LoadWindow
  * ButtonControlID - the button control to be copied/converted
  * NewID           - the new control will be available via this controlID
  * font            - a .bam resref which must be listed in fonts.2da too
  * align           - label text alignment

**Return value:** N/A

**See also:** [Window_CreateButton](Window_CreateButton.md), [Window_CreateLabel](Window_CreateLabel.md)
