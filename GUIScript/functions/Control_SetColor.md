---
title: Control_SetColor
module: _GemRB
---

**Metaclass Prototype:** SetColor (Color[, Index])

**Description:** Set the control's desired text color as a rgb dict.
Specifics depend on control type:
  * text area: set the text color corresponding to the index, which is from GUIDefines:
    * TA_COLOR_NORMAL: text color
    * TA_COLOR_INITIALS: color of the artful initial
    * TA_COLOR_BACKGROUND: text background color
    * TA_COLOR_OPTIONS: color of pick-one selection options
    * TA_COLOR_HOVER: color of options on hover
    * TA_COLOR_SELECTED: color of the selected option
  * button: set the text color (same as passing TA_COLOR_NORMAL)
    * TA_COLOR_BACKGROUND: text background color (only for fonts that have background enabled in fonts.2da)
  * label: set the text color and enable color mode (black background by default)

**Parameters:**
  * Color - Python dictionary of r,g,b,a color values
  * Index - the COLOR_TYPE

**Return value:** N/A
