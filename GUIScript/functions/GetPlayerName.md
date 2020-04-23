---
title: GetPlayerName
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GetPlayerName (PartyID[, LongOrShort])

**Description:** Queries the player character's (script)name.

**Parameters:**
  * PartyID - the PC's position in the party (1 based)
  * LongOrShort - which name to query
    * -1: default name
    * 0: shortname
    * 1: longname
    * 2: scripting name

**Return value:** string

**See also:** [SetPlayerName](SetPlayerName.md), [GetPlayerStat](GetPlayerStat.md)
