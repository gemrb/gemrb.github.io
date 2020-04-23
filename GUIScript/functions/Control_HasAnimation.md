---
title: Control_HasAnimation
module: _GemRB
---

**Prototype:** GemRB.HasAnimation (WindowIndex, ControlIndex, BAMResRef[, Cycle])

**Metaclass Prototype:** HasAnimation (BAMResRef[, Cycle])

**Description:** Checks whether a Control (usually a Button) has a given animation set.

**Parameters:** 
  * WindowIndex, ControlIndex - control IDs
  * BAMResRef - animation file to search for
  * Cycle - require a certain bam cycle to be used

**Return value:** integer, 0 if false
