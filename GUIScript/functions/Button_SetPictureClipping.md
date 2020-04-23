---
title: Button_SetPictureClipping
module: _GemRB
---

**Prototype:** GemRB.SetButtonPictureClipping (Window, Button, ClippingRatio)

**Metaclass Prototype:** SetPictureClipping (ClippingRatio)

**Description:** Sets percent (0-1.0) of width to which button picture 
will be clipped. This clipping cannot be used simultaneously with 
SetButtonOverlay().

**Parameters:** 
  * Window, Button - the control's reference
  * ClippingRatio  - a floating point value from the 0-1 interval

**Return value:** N/A

**See also:** [Button_SetPicture](Button_SetPicture.md), [Button_SetOverlay](Button_SetOverlay.md)
