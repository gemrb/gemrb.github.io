---
title: Button_SetOverlay
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetButtonOverlay (WindowIndex, ControlIndex, Current, Max, r,g,b,a, r,g,b,a)

**Metaclass Prototype:** SetOverlay (ratio, r1,g1,b1,a1, r2,g2,b2,a2)

**Description:** Sets ratio (0-1.0) of height to which button picture will 
be overlaid in a different colour. The colour will fade from the first rgba 
values to the second.

**Parameters:** 
  * Window, Button - the control's reference
  * ClippingRatio  - a floating point value from the 0-1 interval
  * rgba1          - source colour
  * rgba2          - target colour

**Return value:** N/A

**See also:** [Button_SetPictureClipping](Button_SetPictureClipping.md)
