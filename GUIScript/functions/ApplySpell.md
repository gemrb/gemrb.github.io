---
title: ApplySpell
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.ApplySpell (globalID, resref[, casterID])

**Description:** Applies a spell on the actor. 
This function can be used to add abilities that are stored as spells 
(eg. innates).

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * resref   - spell resource reference
  * casterID - global id of the desired caster

**Return value:** N/A

**See also:** [SpellCast](SpellCast.md), [ApplyEffect](ApplyEffect.md), [CountEffects](CountEffects.md)

