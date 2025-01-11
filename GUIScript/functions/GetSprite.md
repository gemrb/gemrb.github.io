---
title: GetSprite
module: GemRB
---

**Prototype:** GemRB.GetSprite (resref[, grad, cycle, frame])

**Description:** Return a Sprite2D for a given resref. If 
the supplied color gradient value is the default -1, then no palette change, 
if it is >=0, then it changes the 4-16 palette entries of the Sprite palette. Since it 
uses 12 colors palette, it has issues in PST.

**Parameters:**
  * resref - the name of the BAM animation (a .bam resref)
  * grad - the gradient number, (-1 is no gradient)
  * cycle, frame - the cycle and frame index of the picture in the bam

**Return value:** N/A
