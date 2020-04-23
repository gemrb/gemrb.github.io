---
title: GameControlSetTargetMode
module: GemRB
---

**Prototype:** GemRB.GameControlSetTargetMode (Mode[, Types])

**Description:** Sets the targeting mode of the main game screen control 
(attack, cast spell, ...) and type of target (ally, enemy and/or neutral; 
all by default). Changes the cursor.

**Parameters:**
  *    Mode
    * 0 TARGET_MODE_NONE
    * 1 TARGET_MODE_TALK
    * 2 TARGET_MODE_ATTACK (also for bashing)
    * 4 TARGET_MODE_CAST
    * 8 TARGET_MODE_DEFEND
    * 16 TARGET_MODE_PICK
  * (target) Types - bitfield:
    * GA_SELECT (selectable actor)
    * GA_NO_DEAD
    * GA_POINT - any point could be selected (area effect)
    * GA_NO_HIDDEN
    * GA_NO_ALLY
    * GA_NO_ENEMY
    * GA_NO_NEUTRAL

**Return value:** N/A

**See also:** [GameControlSetScreenFlags](GameControlSetScreenFlags.md), [GameControlGetTargetMode](GameControlGetTargetMode.md)

