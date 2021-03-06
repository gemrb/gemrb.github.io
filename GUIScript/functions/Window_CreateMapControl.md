---
title: Window_CreateMapControl
module: _GemRB
---

**Prototype:** GemRB.CreateMapControl (WindowIndex, ControlID, x, y, w, h, [LabelID, FlagResRef[, Flag2ResRef]])

**Metaclass Prototype:** CreateMapControl (ControlID, x, y, w, h, [LabelID, FlagResRef [, Flag2ResRef]]

**Description:**    Creates and adds a new Area Map Control to a Window. If 
WindowIndex and ControlID (not ControlIndex!) point to a valid control, it 
will replace that control with the MapControl using the original control's 
dimensions (x,y,w,h are ignored). It is possible to associate a variable 
with the MapControl, in this case, the associated variable will enable or 
disable mapnotes (you must supply a LabelID and the resources for the pins).

**Parameters:**
  * WindowIndex - the value returned from LoadWindow
  * ControlID   - the new control will be available via this controlID
  * x,y,w,h     - X position, Y position, Width and Height of the control
  * LabelID     - associated control ID to display mapnotes, it must be a label
  * FlagResRef  - Resource Reference for the pins, if no Flag2ResRef is given, this should be a .bam resref. If there is a second resref, then both must be .bmp.
  * Flag2ResRef - the readonly mapnotes are marked by this .bam (red pin)

**Return value:** N/A

**See also:** [Control_SetVarAssoc](Control_SetVarAssoc.md), [SetMapnote](SetMapnote.md)
