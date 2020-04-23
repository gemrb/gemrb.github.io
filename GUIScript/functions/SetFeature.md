---
title: SetFeature
module: GemRB
---

**Prototype:** GemRB.SetFeature (feature, value)

**Description:** Set GameType flag FEATURE to VALUE, either True or False.

**Parameters:**
  * FEATURE - GF_xxx constant defined in GUIDefines.py and globals.h
  * VALUE - value to set the feature to. Either True or False

**Return value:** N/A

**Examples:**

      GemRB.SetFeature(GF_ALL_STRINGS_TAGGED, True)

