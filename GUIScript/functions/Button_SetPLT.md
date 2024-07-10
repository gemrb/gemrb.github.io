---
title: Button_SetPLT
module: _GemRB
---

**Metaclass Prototype:** SetPLT (PLTResRef, col1, col2, col3, col4, col5, col6, col7, col8[, type])

**Description:** Sets the Picture of a Button Control from a PLT file. 
Sets up the palette based on the eight given gradient colors.

**Parameters:**
  * PLTResRef - the name of the picture (a .plt resref)
  * col1-8 - color gradients
  * type - the byte to use from the gradients:
    * 0 Body (robe or armour)
    * 1 Weapon
    * 2 Shield
    * 3 Helmet

**Return value:** N/A

**See also:** [Button_SetBAM](Button_SetBAM.md)
