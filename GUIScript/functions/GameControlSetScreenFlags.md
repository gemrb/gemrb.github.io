---
title: GameControlSetScreenFlags
module: GemRB
---

**Prototype:** GemRB.GameControlSetScreenFlags (Mode, Operation)

**Description:** Sets screen flags, like cutscene mode, disable mouse, etc. 
Don't confuse it with the saved screen flags set by GameSetScreenFlags.

**Parameters:**
  * Mode - bitfield:
    * 1 - disable mouse
    * 2 - center on actor (one time)
    * 4 - center on actor (always)
    * 8 - enable gui
    * 16 - lock scroll
    * 32 - cutscene (no action queueing)
  * Operation - bit operation to use

**Return value:** boolean denoting success

**See also:** [GameSetScreenFlags](GameSetScreenFlags.md)
