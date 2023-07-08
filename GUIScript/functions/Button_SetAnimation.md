---
title: Button_SetAnimation
module: _GemRB
---

**Prototype:** GemRB.SetAnimation (WindowIndex, ControlIndex, BAMResRef[, Cycle, Blend, Cols])

**Metaclass Prototype:** SetAnimation (BAMResRef[, Cycle, Blend])

**Description:**  Sets the animation of a Control (usually a Button) from 
a BAM file. Optionally an animation cycle could be set too.

**Parameters:** 
  * WindowIndex - the window control id
  * ControlID - the id of the target control
  * BAMResRef - resref of the animation
  * Cycle - (optional) number of the cycle to use
  * Blend - (optional) set the blend mode, default is BLENDED 
  * Cols - (optional) a list of Colors to apply as the palette

**Return value:** N/A
