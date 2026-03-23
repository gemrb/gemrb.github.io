---
title: Button_SetPLT
module: _GemRB
---

**Metaclass Prototype:** SetPLT (PLTResRef, ColorDict[, type])

**Description:** Sets the Picture of a Button Control from a PLT file. 
Sets up the palette based on the colors contained in ColorDict, where 
the key is the stat coresponding to the color.

**Parameters:**
  * PLTResRef - the name of the picture (a .plt resref)
  * ColorDict - dictionary of up to 8 color stats mapped to indices in the global palette
  * type - the byte to use from the gradients:
    * 0 Body (robe or armour)
    * 1 Weapon
    * 2 Shield
    * 3 Helmet

**Example:**

    import PaperDoll
    pc = GemRB.GameGetSelectedPCSingle ()
    stats = PaperDoll.ColorStatsFromPC (pc)
    Button.SetPLT (PaperDoll.GetActorPaperDoll (pc), stats)

**Return value:** N/A

**See also:** [Button_SetPicture](Button_SetPicture.md)
