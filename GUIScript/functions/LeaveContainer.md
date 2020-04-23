---
title: LeaveContainer
module: GemRB
---

**Prototype:** GemRB.LeaveContainer ()

**Description:** Closes the current container by calling 'CloseContainerWindow' 
in the next update cycle. You cannot call 'CloseContainerWindow' directly, 
because the core system needs to know if the container subwindow is still 
open. This function will also remove empty ground piles.

**Return value:** N/A

**See also:** [GetContainer](GetContainer.md), [GetContainerItem](GetContainerItem.md), [LeaveStore](LeaveStore.md)
