---
title: Button_SetBAM
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetButtonBAM (WindowIndex, ControlIndex, BAMResRef, CycleIndex, FrameIndex, col1)

**Metaclass Prototype:** SetBAM (BAMResRef, CycleIndex, FrameIndex[, col1])

**Description:** Sets the Picture of a Button Control from a BAM file. If 
the supplied color gradient value is the default -1, then no palette change, 
if it is >=0, then it changes the 4-16 palette entries of the bam. Since it 
uses 12 colors palette, it has issues in PST.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * BAMResRef - the name of the BAM animation (a .bam resref)
  * CycleIndex, FrameIndex - the cycle and frame index of the picture in the bam
  * col1 - the gradient number, (-1 no gradient)

**Return value:** N/A

**See also:** [Button_SetPLT](Button_SetPLT.md), [Button_SetPicture](Button_SetPicture.md), [Button_SetSprites](Button_SetSprites.md)
