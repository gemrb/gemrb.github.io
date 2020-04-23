---
title: GameSelectPC
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.GameSelectPC (PartyID, Selected[, Flags = SELECT_NORMAL])

**Description:** Selects or deselects a PC. Note: some things use a 
different PC selection mechanism (dialogs and stores are not unified yet).

**Parameters:**
  * PartyID - the PC's position in the party, 0 means ALL
  * Selected - boolean
  * Flags - bitflags
    * SELECT_REPLACE - if set deselect all other actors
    * SELECT_QUIET - do not run SelectionHandler (no GUI feedback)

**Return value:** N/A

**Example:**
def SelectAllOnPress ():
  GemRB.GameSelectPC (0, 1)
  return
The above function is associated to the 'select all' button of the GUI screen.

**See also:** [GameIsPCSelected](GameIsPCSelected.md), [GameSelectPCSingle](GameSelectPCSingle.md), [GameGetSelectedPCSingle](GameGetSelectedPCSingle.md), [GameGetFirstSelectedPC](GameGetFirstSelectedPC.md)
