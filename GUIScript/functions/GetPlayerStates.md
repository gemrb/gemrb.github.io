---
title: GetPlayerStates
module: GemRB
---

**Prototype:** GemRB.GetPlayerStates (PartyID)

**Description:** Returns the active spell states on the player. The state 
descriptions are in the statdesc.2da file which comes with the original 
games. The values in the character array equal to the corresponding cycle 
number in states.bam. To reference statdesc.2da, subtract 65 from the 
values.

**Parameters:**
  * PartyID - the character's position in the party

**Return value:** a string whose letters are greater or equal ascii 65. 
Using the states.bam font, they will be drawn as the status icons.

**See also:** [GetPlayerName](GetPlayerName.md), [GetPlayerStat](GetPlayerStat.md)

