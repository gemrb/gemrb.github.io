---
title: GetVar
module: GemRB
---

**Prototype:** GemRB.GetVar (VariableName)

**Description:** Get a Variable value from the Global Dictionary. Controls 
could be set up to be associated with such a variable. Even multiple 
controls could affect the same variable.

**Parameters:**
  * VariableName - name of the variable (shorter than 32!)

**Return value:** numeric, 0 if the variable doesn't exist

**Examples:**

    selected = GemRB.GetVar ('SelectedMovie')

**See also:** [SetVar](SetVar.md), [Control_SetVarAssoc](Control_SetVarAssoc.md)

