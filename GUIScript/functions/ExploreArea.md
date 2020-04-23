---
title: ExploreArea
module: GemRB
---

**Prototype:** ExploreArea ([bitvalue=-1])

**Description:** Explores or unexplores the whole area. Basically fills the 
explored bitmap with the value given. If there was no value given, it will 
fill with -1 (all bit set).

**Parameters:**
  * bitvalue:
    * 0 - undo explore
    * -1 - explore
    * all other values give meaningless results

**Return value:** N/A

**See also:** [MoveToArea](MoveToArea.md), [RevealArea](RevealArea.md)
