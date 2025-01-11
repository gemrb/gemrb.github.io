---
title: GameControlSetScreenFlags
module: GemRB
---

**Prototype:** GemRB.GameControlSetScreenFlags (Mode, Operation)

**Description:** Sets screen flags, like cutscene mode, disable mouse, etc. 
Don't confuse it with the saved screen flags set by GameSetScreenFlags.

**Parameters:**
  * Mode:
    * 0 - center on actor (one time)
    * 1 - center on actor (always)
    * 2 - cutscene mode (rather use ai scripts for this)
  * Operation - bit operation to use

**Return value:** boolean denoting success

**See also:** [GameSetScreenFlags](GameSetScreenFlags.md)
