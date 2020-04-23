---
title: PlayMovie
module: GemRB
---

**Prototype:** GemRB.PlayMovie (MOVResRef[, flag=0])

**Description:** Plays the named movie. Sets the configuration variable 
MOVResRef to 1. If flag was set to 1 it won't play the movie if the 
configuration variable was already set (saved in game ini).

**Parameters:**
  * MOVResRef - a .mve/.bik (or vlc compatible) resource reference.
  * flag:
      * 0 - only play the movie if it has never been played before
      * 1 - always play

**Return value:**
  * 0 - movie played
  * -1 - error occurred
  * 1 - movie skipped

**See also:** [SetVar](SetVar.md), [GetVar](GetVar.md)

