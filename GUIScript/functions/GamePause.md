---
title: GamePause
module: GemRB
---

**Prototype:** GemRB.GamePause (pause, quiet)

**Description:** Pauses or unpauses the current game or toggle whatever was 
set. This affects all ingame events, including: scripts, animations, 
movement. It doesn't affect the GUI.

**Parameters:**
  * pause  - int,
    * 0 = continue
    * 1 = pause
    * 2 = toggle pause
    * 3 = query state
  * quiet  - int bitfield,
    * 1 - no feedback
    * 2 - forced pause

**Return value:** the resulting paused state
