---
title: ValidTarget
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.ValidTarget (PartyID, flags)

**Description:** Checks if an actor is valid for various purposes, like 
being visible, selectable, dead, etc.

**Parameters:** 
  * PartyID - party ID or global ID of the actor to check
  * flags   - bits to check against (see GameControlSetTargetMode)

**See also:** [GameControlSetTargetMode](GameControlSetTargetMode.md)

**Return value:** boolean
