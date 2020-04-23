---
title: Window_CreateWorldMapControl
module: _GemRB
---

**Prototype:** GemRB.CreateWorldMapControl (WindowIndex, ControlID, x, y, w, h, direction[, font, recolor])

**Metaclass Prototype:** CreateWorldMapControl (ControlID, x, y, w, h, direction[, font, recolor])

**Description:** This command creates a special WorldMapControl, which is 
currently unavailable via .chu files. If WindowIndex and ControlID (not 
ControlIndex!) point to a valid control, it will replace that control with 
the WorldMapControl using the original control's dimensions (x,y,w,h are 
ignored).

**Parameters:** 
  * WindowIndex - the value returned from LoadWindow
  * ControlID   - the new control will be available via this controlID
  * x,y,w,h     - X position, Y position, Width and Height of the control
  * direction   - travel direction (-1 to ignore)
  * font        - font used to display names of map locations
  * recolor     - recolor map icons (bg1)

**Return value:** N/A

**Example:**
 
       Window = GemRB.LoadWindow (0)
       Window.CreateWorldMapControl (4, 0, 62, 640, 418, Travel, 'floattxt')
       WorldMapControl = Window.GetControl (4)

**See also:** [WorldMap_GetDestinationArea](WorldMap_GetDestinationArea.md), [CreateMovement](CreateMovement.md)
