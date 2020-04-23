---
title: WorldMap_AdjustScrolling
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.AdjustScrolling (WindowIndex, ControlIndex, x, y)

**Metaclass Prototype:** AdjustScrolling (x, y)

**Description:** Sets the scrolling offset of a WorldMapControl.

**Parameters:** 
  * WindowIndex - the windows's reference
  * ControlIndex - the control's reference
  * x, y - scrolling offset values

**Return value:** N/A

**Example:**
    # northeast
    Button = GemRB.GetControl (Window, 9)
    Button.SetEvent (IE_GUI_BUTTON_ON_PRESS, 'MapNE')
...

**def MapNE():**
    WorldMapControl.AdjustScrolling (10, -10)
    return
The above lines set up a button event. When the button is pressed the worldmap will be shifted in the northeastern direction.

**See also:** [[guiscript:Window_CreateWorldMapControl]
