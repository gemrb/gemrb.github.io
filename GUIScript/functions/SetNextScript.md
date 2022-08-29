---
title: SetNextScript
module: GemRB
---

**Prototype:** GemRB.SetNextScript (scriptname)

**Description:** Instructs the GUIScript engine to load the script when 
this script has terminated.

**Parameters:**
  * scriptname - name of the python script to be executed. May not exceed 60 characters.

**Return value:** N/A

**Examples:**

    GemRB.SetNextScript ('CharGen')
    return

**See also:** [QuitGame](QuitGame.md)

