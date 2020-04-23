---
title: LeaveParty
module: GemRB
---

**Prototype:** GemRB.LeaveParty (globalID [, Dialog])

**Description:** Removes the character from the party and initiates dialog 
if demanded.

**Parameters:**
  * globalID - party ID or global ID of the actor to use
  * Dialog:
    * if set to 1, initiate the dialog.
    * if set to 2, execute 'SetLeavePartyDialogFile' and initiate dialog.

**Return value:** N/A

**See also:** [GetPartySize](GetPartySize.md)

