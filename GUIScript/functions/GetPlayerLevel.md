---
title: GetPlayerLevel
module: GemRB
---

**Prototype:** GemRB.GetPlayerLevel (globalID, class)

**Description:** Returns the actor's level in the specified class. Takes
dual-classing into account (inactive duals).

**Parameters:**
  * globalID - the PC's position in the party (1 based)
  * class - which level to query, see ie_stats.py

**Return value:** number
