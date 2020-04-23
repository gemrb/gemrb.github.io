---
title: Control_SubstituteForControl
module: _GemRB
---

**Prototype:** GemRB.SubstituteForControl (WindowIndex, ControlIndex, TWindowIndex, TControlIndex)

**Metaclass Prototype:** SubstituteForControl (TControl)

**Description:** Substitute a control with another control (even of 
different type), keeping its ControlID, size and scrollbar.

**Parameters:**
  * WindowIndex - the value returned from LoadWindow for the substitute control
  * ControlID - the substitute control's controlID
  * TWindowIndex - the value returned from LoadWindow for the target control
  * TControlID - the old control's controlID
  * TControl - target control object

**Return value:** The new ControlID
