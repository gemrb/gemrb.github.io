---
title: SetToken
module: GemRB
---

**Prototype:** GemRB.SetToken(VariableName, Value)

**Description:** Set/Create a token to be replaced in StrRefs. QueryText() 
will use the actual value of the token when it encounters '<token>' 
substrings in a retrieved dialog.tlk entry. Some tokens are hardcoded and 
you can't affect QueryText() by setting them. Usage of those tokens should 
be avoided. The hardcoded token list:
  * FIGHTERTYPE  - always resolves to strref #10174
  * RACE         - always resolves to the race of the last speaker
  * GABBER       - always resolves to the longname of the last speaker
  * SIRMAAM      - strref #27473/#27475 depending on last speaker's gender
  * GIRLBOY      - strref #27477/#27476 depending on last speaker's gender
  * BROTHERSISTER- strref #27478/#27479 ...
  * LADYLORD     - strref #27481/#27480 ...
  * MALEFEMALE   - strref #27483/#27482 ...
  * HESHE        - strref #27485/#27484 ...
  * HISHER       - strref #27487/#27486 ...
  * HIMHER       - strref #27487/#27488 ...
  * MANWOMAN     - strref #27490/#27489 ...
  * PRO_*        - same as above with protagonist

**Parameters:**
  *    VariableName - the name of the variable (shorter than 32!)
  *    Value        - string, the value of the token

**Example:**

    ClassTitle = CommonTables.Classes.GetValue (Class, 'CAP_REF', GTV_REF)
    GemRB.SetToken ('CLASS', ClassTitle)
    # force an update of the string by refetching it
    TA.SetText (GemRB.GetString (16480))

**Return value:** N/A

**See also:** [GetToken](GetToken.md), [Control_QueryText](Control_QueryText.md), [Control_SetText](Control_SetText.md)

