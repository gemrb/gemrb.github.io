---
title: WorldMap_SetTextColor
module: _GemRB
---

**Prototype:** GemRB.SetWorldMapTextColor (WindowIndex, ControlIndex, which, red, green, blue)

**Metaclass Prototype:** SetTextColor (which, red, green, blue)

**Description:** Sets the label colors of a WorldMap Control. 'which' 
selects the color affected.

**Parameters:**
  * WindowIndex - the window control id
  * ControlID - the id of the target control
  * which - selects the color affected:
    * IE_GUI_WMAP_COLOR_BACKGROUND
    * IE_GUI_WMAP_COLOR_NORMAL - main text color
    * IE_GUI_WMAP_COLOR_SELECTED - color of hovered on text
    * IE_GUI_WMAP_COLOR_NOTVISITED - color of unvisited entries
  * red - red value
  * green - green value
  * blue - blue value

**Return value:** N/A
