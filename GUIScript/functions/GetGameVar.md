---
title: GetGameVar
module: GemRB
---

**Prototype:** GemRB.GetGameVar (VariableName)

**Description:** Get a Variable value from the Game Global Dictionary. This 
is what gamescripts know as GLOBAL variables. 

**Parameters:**
  * VariableName - name of the variable

**Return value:**

**Examples:**

    Chapter = GemRB.GetGameVar ('chapter')

**See also:** [GetVar](GetVar.md), [GetToken](GetToken.md), [CheckVar](CheckVar.md)
