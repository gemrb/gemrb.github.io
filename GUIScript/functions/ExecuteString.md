---
title: ExecuteString
module: GemRB
---

**Prototype:** GemRB.ExecuteString (String[, Slot])

**Description:** Executes an in-game script action. If a valid Slot (greater than 0) 
is specified, the actor in that Slot is used as the script context. Slot numbers 
[1-1000] are treated as portrait indices, while Slot numbers greater than 1000 are 
treated as global actor IDs. If no Slot is specified, the scriptable object (actor, 
container, door, etc.) currently under the cursor (if available) becomes the script 
context. If no valid object exists under the cursor, the current area script is used 
as the script context instead.

The script context determines which scriptable executes the action and its 
associated behavior. For example, LOCALS used by the action will be those of the 
object acting as the script context.

**Parameters:**
  * String - a gamescript action
  * Slot   - a player slot or global ID

**Return value:** N/A

**Examples:**

    GemRB.ExecuteString('ActionOverride([PC], Attack(NearestEnemyOf(Myself)) )')

The above example will force a player (most likely Player1) to attack an enemy, issuing the command as it would come from the current area's script. The current gametype must support the scripting action.


    GemRB.ExecuteString('Attack(NearestEnemyOf(Myself))', 2)

The above example will force Player2 to attack an enemy, as the example will run in that actor's script context.

**See also:** [EvaluateString](EvaluateString.md), gamescripts

