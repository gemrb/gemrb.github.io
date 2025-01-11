---
title: View_AddAlias
module: _GemRB
---

**Prototype:** View_AddAlias (GView, AliasGroup[, AliasID, Overwrite])

**Metaclass Prototype:** AddAlias (AliasGroup[, AliasID, Overwrite])

**Description:** Adds an additional entry to the Scripting engine under
AliasGroup with AliasID and binds it to the view, optionally
overwriting an existing entry.

**Parameters:**
  * GView - the control's reference
  * AliasGroup - View group
  * AliasID - force to this alias numeric ID
  * Overwrite - overwrite any existing alias

**Examples:**

    PortraitWindow.AddAlias ('HIDE_CUT', 3)

**Return value:** N/A
