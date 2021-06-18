---
title: View_SetEventProxy
module: _GemRB
---

**Prototype:** View_SetEventProxy (GView, ProxyView)

**Metaclass Prototype:** SetEventProxy (ProxyView)

**Description:** Set a proxy View that will receive events on behalf of the target View.

**Parameters:**
  * GView - the control's reference
  * ProxyView - another View

**Example:**

    RaceWindow.SetEventProxy (ScrollBarControl)

**Return value:** N/A
