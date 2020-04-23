---
title: GetToken
module: GemRB
---

**Prototype:** GemRB.GetToken (VariableName)

**Description:** Get a Variable value from the Token Dictionary. Tokens are 
string values, used both by the game scripts and the GUI scripts.

**Parameters:**
  * VariableName - name of the variable (shorter than 32!)

**Return value:** string, the value of the token

**Example:**

    TextArea.Append (GemRB.GetToken ('CHARNAME'))
The above example will add the protagonist's name to the TextArea (if the token was set correctly).

**See also:** [SetToken](SetToken.md), [Control_QueryText](Control_QueryText.md)

