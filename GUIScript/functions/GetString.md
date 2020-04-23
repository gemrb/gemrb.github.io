---
title: GetString
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetString (Strref[, Flags])

**Description:** Returns string for given strref. Usually, you don't need to 
resolve a string before use, as you can use SetText with a strref parameter. 
This command lets you alter the string. For example, if you want to add a 
level value without a token, you'll need this.

**Parameters:** 
  * Strref - a string reference from the dialog.tlk table
  * Flags - a bitfield:
    * 1   - display strrefs on
    * 2   - play attached sound
    * 4   - speech (stop previous sound)
    * 256 - strref off (overrides cfg)

**Return value:** A string with resolved tokens. To resolve %d's, you must
either use StatComment or do it manually.

**Example:**
   Level = GemRB.GetPlayerStat (pc, IE_LEVEL) # 1 at character generation
   Label.SetText (GemRB.GetString(12137) + str(Level)) 
The above example will display 'Level: 1' in the addressed label.

**See also:** [StatComment](StatComment.md), [Control_SetText](Control_SetText.md)

