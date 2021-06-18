---
title: CreateView
module: GemRB
---

**Prototype:** GemRB.CreateWindow (ControlID, Type, FrameRect[, OtherArgs])

**Description:** Creates a new empty view and returns it.

**Parameters:** 
  * ControlID - the window's ID
  * Type - the View's type
  * FrameRect - a dict with the View's frame (origin and size)
  * OtherArgs - further arguments depending on the View type

**Example:**

    view = CreateView (control, IE_GUI_SCROLLBAR, frame, CreateScrollbarARGs(bam))

**See also:** [RemoveView](RemoveView.md), [AddSubview](AddSubview.md), [GetFrame](GetFrame.md)

**Return value:** GView
