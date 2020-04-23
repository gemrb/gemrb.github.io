---
title: Window_ShowModal
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.ShowModal (WindowIndex, [Shadow=MODAL_SHADOW_NONE])

**Metaclass Prototype:** ShowModal ([Shadow=MODAL_SHADOW_NONE])

**Description:** Show a Window on Screen setting the Modal Status. If 
Shadow is MODAL_SHADOW_GRAY, other windows are grayed. If Shadow is 
MODAL_SHADOW_BLACK, they are blacked out.

**Parameters:**
  * WindowIndex - the index returned by LoadWindow()
  * Shadow:
    * MODAL_SHADOW_NONE = 0
    * MODAL_SHADOW_GRAY = 1 (translucent)
    * MODAL_SHADOW_BLACK = 2

**Return value:** N/A

**See also:** [Window_SetVisible](Window_SetVisible.md)
