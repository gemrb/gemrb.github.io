---
title: Roll
module: GemRB
---

**Prototype:** GemRB.Roll (Dice, Size, Add)

**Description:** Calls traditional dice roll calculation.

**Parameters:**
  * Dice - the number of the dice.
  * Size - the size of the die.
  * Add  - add this value directly to the sum

**Return value:** numeric

**Examples:** 

    dice = 3
    size = 5
    v = GemRB.Roll (dice, size, 3)

The above example generates a 3d5+3 number.
