---
title: Button_SetSprites
module: _GemRB
---

**Metaclass Prototype:** SetSprites (ResRef, Cycle, UnpressedFrame, PressedFrame, SelectedFrame, DisabledFrame)

**Description:** Sets the Button's images. You can disable the images by 
setting the IE_GUI_BUTTON_NO_IMAGE flag on the control.

**Parameters:**
  * ResRef - a .bam animation resource (.bam resref)
  * Cycle - the cycle of the .bam from which all frames of this button will come
  * UnpressedFrame - the frame which will be displayed by default
  * PressedFrame - the frame which will be displayed when the button is pressed 
  * SelectedFrame - this is for selected checkboxes
  * DisabledFrame - this is for inactivated buttons

**Return value:** N/A

**See also:** [Button_SetFlags](Button_SetFlags.md), [Button_SetBAM](Button_SetBAM.md), [Button_SetPicture](Button_SetPicture.md)
