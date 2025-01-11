---
title: GameSetScreenFlags
module: GemRB
---

**Prototype:** GemRB.GameSetScreenFlags (Bits, Operation)

**Description:** Sets the Display Flags of the main game screen (pane 
status, dialog textarea size).

**Parameters:**
  * Bits (partly game dependent due to different GUI layouts)
    * 0 - default, small message window size
    * 1 - enable party AI
    * 2 - medium message window size
    * 4 - large message window size (use with 2, as 6, GS_LARGEDIALOG)
    * 8 - in dialog mode
    * 16 - hide the whole GUI
    * 32 - hide left menu (options) window
    * 64 - hide portrait window
  * Operation - The usual bit operations

**Return value:** boolean denoting success
