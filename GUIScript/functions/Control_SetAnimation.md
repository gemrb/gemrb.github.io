---
title: Control_SetAnimation
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetAnimation (WindowIndex, ControlIndex, BAMResRef[, Cycle, Blend])

**Metaclass Prototype:** SetAnimation (BAMResRef[, Cycle, Blend])

**Description:**  Sets the animation of a Control (usually a Button) from 
a BAM file. Optionally an animation cycle could be set too.

**Parameters:** 
  * WindowIndex - the window control id
  * ControlID - the id of the target control
  * BAMResRef - resref of the animation
  * Cycle - (optional) number of the cycle to use
  * Blend - (optional) toggle use of blending

**Return value:** N/A

**See also:** [Control_SetAnimationPalette](Control_SetAnimationPalette.md)
