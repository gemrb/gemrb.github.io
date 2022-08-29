---
title: GetView
module: GemRB
---

**Prototype:** GetView (GView[, ID])

**Metaclass Prototype:** /

**Description:** Lookup view from either a window or from an alias.
**Parameters:**
  * GView - the window's reference or a string with the alias
  * ID - look for a view with a specific numeric ID

**Examples:**

    GemRB.GetView ('ACTWIN')

**Return value:** View
