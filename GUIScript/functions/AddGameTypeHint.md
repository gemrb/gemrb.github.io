---
title: AddGameTypeHint
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.AddGameTypeHint (type, weight, flags=0)

**Description:** Asserts that GameType should be TYPE, with confidence WEIGHT. 
This is used by Autodetect.py scripts when GameType was set to 'auto'.

**Parameters:**
  * type - GameType (e.g. bg1, bg2, iwd, how, iwd2, pst and others)
  * weight - numeric, confidence that TYPE is correct. Standard games should use values <= 100, (eventual) new games based on the standard ones should use values above 100.
  * flags - numeric, not used now

**Return value:** N/A
