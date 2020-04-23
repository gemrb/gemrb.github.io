---
title: CheckSpecialSpell
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.CheckSpecialSpell (globalID, SpellResRef)

**Description:** Checks if an actor's spell is considered special (splspec.2da).

**Parameters:**
  * globalID - global ID of the actor to use
  * SpellResRef - spell resource to check

**Return value:** bitfield
  * 0 for normal ones
  * SP_IDENTIFY - any spell that cannot be cast from the menu
  * SP_SILENCE  - any spell that can be cast in silence
  * SP_SURGE    - any spell that cannot be cast during a wild surge
  * SP_REST     - any spell that is cast upon rest if memorized
