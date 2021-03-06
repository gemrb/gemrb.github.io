---
title: GetPCStats
module: GemRB
---

**Prototype:** GemRB.GetPCStats (PartyID)

**Description:** Returns dictionary of PC's performance stats.

**Parameters:**
  * PartyID - the PC's position in the party (1 based)

**Return value:** A Python dictionary containing the following items
  * 'BestKilledName'   - strref of killed creature with biggest XP
  * 'BestKilledXP'     - XP value of this creature
  * 'JoinDate'         - date joined the team
  * 'KillsChapterXP'   - total XP from kills gathered in this chapter
  * 'KillsChapterCount'- total number of kills in this chapter
  * 'KillsTotalXP'     - total XP from kills
  * 'KillsTotalCount'  - total number of kills
  * 'FavouriteSpell'   - spell used the most of the time
  * 'FavouriteWeapon'  - weapon bringing the most kill XP

**See also:** [GetPlayerStat](GetPlayerStat.md)
