---
title: Button_SetAnimation
module: _GemRB
---

**Metaclass Prototype:** SetAnimation (Animation[, Cycle, Flags, Cols])

**Description:**  Sets the animation of a Button from
a BAM file with optional cycle or a list of Sprite2D objects and a duration.
Optionally Flags can be used to specify the animation flags.

**Parameters:** 
  * GButton - the button
  * Animation - resref of the animation, or a list of Sprite2D
  * Cycle - (optional) number of the cycle to use if using a BAM, otherwise the duration (in ms) required for the animation.
  * Flags - (optional) set the animation flags 
  * Cols - (optional) a list of Colors to apply as the palette

**Return value:** N/A
