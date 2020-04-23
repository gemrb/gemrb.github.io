---
title: GetPlayerScript
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetPlayerScript (globalID[, Index])

**Description:** Queries the player's script. If index is omitted, it will 
default to the class script slot (customisable by players).

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * Index - script index (see scrlev.ids)

**Return value:** the player's script (.bcs or .baf resref)

**See also:** [SetPlayerScript](SetPlayerScript.md)

