---
title: Control_SetTooltip
module: _GemRB
---

**Prototype:** GemRB.SetTooltip (GView, String|Strref[, Function])

**Metaclass Prototype:** SetTooltip (String|Strref[, Function])

**Description:** Sets view's tooltip. Any view may have a tooltip.

The tooltip's visual properties must be set in the gemrb.ini file:
  * TooltipFont - Font used to display tooltips
  * TooltipBack - Sprite displayed behind the tooltip text, if any
  * TooltipMargin - Space between tooltip text and sides of TooltipBack (x2)

**Parameters:**
  * GView - the view's reference
  * String - an arbitrary string
  * Strref - a string index from the dialog.tlk table.
  * Function - (optional) function key to prepend

**Return value:** N/A

**See also:** [Control_SetText](Control_SetText.md)
