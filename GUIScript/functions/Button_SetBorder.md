---
title: Button_SetBorder
module: _GemRB
---

**Prototype:** GemRB.SetButtonBorder (GButton, BorderIndex, Color, [enabled=0, filled=0, Rect=None])

**Metaclass Prototype:** SetBorder (BorderIndex, Color, [enabled=0, filled=0, Rect=None])

**Description:** Sets border/frame/overlay parameters for a button. This 
command can be used for drawing a border around a button, or to overlay 
it with a tint (like with unusable or unidentified item's icons).

**Parameters:** 
  * GButton - the control's reference
  * BorderIndex - 0, 1 or 2
  * RGBA - red,green,blue,opacity components of the border colour
  * enabled - 1 means enable it immediately
  * filled - 1 means draw it filled (overlays)
  * Rect - the border rectangle (the button frame if None)

**Return value:** N/A

**Examples:**

    GemRB.SetButtonBorder (Icon, 0, color,    0, 1, rect)
Not known spells are drawn darkened (the whole button will be overlaid).

**See also:** [Button_EnableBorder](Button_EnableBorder.md)
