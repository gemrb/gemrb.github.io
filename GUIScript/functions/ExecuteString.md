---
title: ExecuteString
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.ExecuteString (String[, Slot])

**Description:** Executes an in-game script action in the current area 
script context. This means that LOCALS will be treated as the current 
area's variable. If a number was given, it will execute the action in the 
numbered actor's context.

**Parameters:**
  * String - a gamescript action
  * Slot   - a player slot or global ID

**Return value:** N/A

**Example:**
  GemRB.ExecuteString('ActionOverride([PC], Attack(NearestEnemyOf(Myself)) )')
The above example will force a player (most likely Player1) to attack an enemy, issuing the command as it would come from the current area's script. The current gametype must support the scripting action.


  GemRB.ExecuteString('Attack(NearestEnemyOf(Myself))', 2)
The above example will force Player2 to attack an enemy, as the example will run in that actor's script context.

**See also:** [EvaluateString](EvaluateString.md), gamescripts

