---
title: LoadWindow
module: GemRB
---

**Prototype:** GemRB.LoadWindow (WindowID)

**Description:** Returns a Window. You must call LoadWindowPack before using 
this command. The window won't be displayed. If LoadWindowPack() set nonzero 
natural screen size with Width and Height parameters, the loaded window is 
then moved by (screen size - winpack size) / 2

**Parameters:** a window ID, see the .chu file specification

**Return value:** GWindow (index)

**See also:** [LoadWindowPack](LoadWindowPack.md), [Window_GetControl](Window_GetControl.md), [Window_SetVisible](Window_SetVisible.md), [Window_ShowModal](Window_ShowModal.md), [accessing_gui_controls](accessing_gui_controls.md)
