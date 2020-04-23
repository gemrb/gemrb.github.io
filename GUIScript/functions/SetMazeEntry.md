---
title: SetMazeEntry
module: GemRB
---

**Prototype:** GemRB.SetMazeEntry (entry, type, value)

**Description:** Sets a field in a maze entry. The entry index shouldn't 
exceed the maximum possible maze size (64).

**Parameters:** 
  * entry - index of entry to change
  * type - what sort of entry should it be?
    * ME_ACCESSED, ME_WALLS, ME_TRAP, ME_SPECIAL
  * value - what to set (meaning depends on type)

**Return value:** N/A

