---
title: GetSystemVariable
module: GemRB
---

**Prototype:** GemRB.GetSystemVariable (Index)

**Description:** Returns the named Interface attribute.

**Parameters:**
  * Index could have the following values:
    * SV_BPP = 0 - bpp (color resolution)
    * SV_WIDTH = 1 - screen width
    * SV_HEIGHT = 2 - screen height
    * SV_GAMEPATH = 3 - game path
    * SV_TOUCH = 4 - are we using touch input mode?
    * SV_SAVEPATH = 5 - path to the parent of save/mpsave/bpsave dir

**Return value:** This function returns -1 if the index is invalid.

**See also:** [GetGameString](GetGameString.md)

