---
title: View_AddSubview
module: _GemRB
---

**Prototype:** View_AddSubview (GView, subview [,siblingView=None, id=-1])

**Metaclass Prototype:** AddSubview (subview[, siblingView=None, id=-1])

**Description:** Adds a view to a new superview in front of siblingView (or the back if None), removing it from its previous superview (if any).

**Parameters:**
  * GView - the control's (superview's) reference
  * subview - View to add
  * siblingView - View to add
  * id - assign this numeric ID to the new view (useful if it's already taken)

**Examples:**

    RaceWindow.AddSubview (ScrollBarControl)

**Return value:** the new View
