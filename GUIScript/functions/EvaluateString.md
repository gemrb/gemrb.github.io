---
title: EvaluateString
module: GemRB
---

**Prototype:** GemRB.EvaluateString (String[, quiet=False])

**Description:** Evaluates an ingame script trigger in the current area 
script context. It prints the result. The command is more useful from the 
ingame debug console than from scripts.

**Parameters:**
  * String - a gamescript trigger
  * quiet - set to True to skip printing the result

**Return value:** the trigger's return value

**Examples:**

GemRB.EvaluateString('HPPercentLT(Player1, 20)', True)

**See also:** [ExecuteString](ExecuteString.md)

