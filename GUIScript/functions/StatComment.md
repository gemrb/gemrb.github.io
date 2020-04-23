---
title: StatComment
module: GemRB
---

**Prototype:** GemRB.StatComment (Strref, X, Y)

**Description:**
Replaces %%d's with the values of X and Y in a string referenced by strref.

PST uses %%d values in place of tokens, thus it requires a special command. 
In other engines use GetString after setting the needed tokens with 
SetToken (if you need to set them at all).

**Parameters:**
  * Strref - a string reference from the dialog.tlk table.
  * X, Y   - two numerical values to be replaced in place of %%d's.

**Return value:** A string with resolved %%d's.

**Example:**

def IntPress():
      global Int, StatTable, TextArea
      TextArea.SetText (18488)
      intComment = StatTable.GetValue (Int, 1)
      TextArea.Append (GemRB.StatComment (intComment, 0, 0))

The above example comes directly from our PST script, it will display the 
description of the intelligence stat (strref==18488), adding a comment 
based on the current Int variable. StatTable (a 2da table) contains the 
comment strref values associated with an intelligence value.

**See also:** [GetString](GetString.md), [SetToken](SetToken.md),
[Table_GetValue](Table_GetValue.md), [Control_SetText](Control_SetText.md),[LoadTable](LoadTable.md),
[TextArea_Append](TextArea_Append.md)

