---
title: FillPlayerInfo
module: GemRB
---

**Prototype:** GemRB.FillPlayerInfo (globalID[, Portrait1, Portrait2, clear=0])

**Description:** Fills basic character info that is not stored in stats. 
This command will generate an AnimationID for the character based on the 
avprefix.2da table, the character must have the stats referenced in the 
avprefix structure already set. It will also set the player's portraits if 
given. It will set the actor's area/position according to the 'PlayMode' 
variable and the Slot value (using the startpos.2da table). This command 
must be called once after a character was created and before EnterGame().

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * Portrait1 - medium (or large) portrait
  * Portrait2 - small portrait
  * clear - clear all the quickslot/spell/item fields?

avprefix.2da is a gemrb specific table. Its first row contains the base animationID used for the actor. Its optional additional rows contain other table resrefs which refine the animationID by different player stats. The first row of these tables contain the stat which affects the animationID. The other rows assign cumulative values to the animationID. 

**For example:**
avprefix.2da
        RESOURCE
0       0x6000
1       avprefr
2       avprefg
3       avprefc

avprefr.2da
                RACE
TYPE            201
HUMAN           0
ELF             1
HALF_ELF        1
GNOME           4
HALFLING        3
DWARF           2
HALFORC         5

Based on the avatar's stat (201 == race) the animationID (0x6000) will be increased by the given values. For example an elf's animationID will be 0x6001. The animationID will be further modified by gender and class.

**Return value:** N/A

**Examples:**

    GemRB.FillPlayerInfo (MyChar, PortraitName + 'M', PortraitName + 'S')

**See also:** [LoadGame](LoadGame.md), [CreatePlayer](CreatePlayer.md), [SetPlayerStat](SetPlayerStat.md), [EnterGame](EnterGame.md)

