---
title: WorldMap_GetDestinationArea
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.GetDestinationArea (WindowIndex, ControlID[, RndEncounter])

**Metaclass Prototype:** GetDestinationArea ([RndEncounter])

**Description:** Returns a dictionary of the selected area by the worldmap 
control. If the route is blocked, then Distance will return a negative 
value and Destination/Entrance won't be set. Random encounters could be 
optionally evaluated. If the random encounter flag is set, the random 
encounters will be evaluated too.

**Parameters:**
  * WindowIndex, ControlIndex - designate a worldmap control
  * RndEncounter - check for random encounters?

**Return value:** Dictionary
  * Target      - The target area selected by the player
  * Distance    - The traveling distance, if it is negative, the way is blocked
  * Destination - The area resource reference where the player arrives (if there was a random encounter, it differs from Target)
  * Entrance    - The area entrance in the Destination area, it could be empty, in this casethe player should appear in middle of the area

**See also:** [Window_CreateWorldMapControl](Window_CreateWorldMapControl.md), [CreateMovement](CreateMovement.md), [accessing_gui_controls](accessing_gui_controls.md)
