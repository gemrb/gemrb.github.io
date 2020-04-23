---
title: SetPlayerScript
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.SetPlayerScript (globalID, ScriptName[, Index])

**Description:** Sets the player character's script. Normally only the class 
script is customisable via the GUI (used if Index is omitted).

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * ScriptName - the script resource
  * Index      - the script index (see scrlev.ids)

**Return value:** N/A

**See also:** [GetPlayerScript](GetPlayerScript.md)
