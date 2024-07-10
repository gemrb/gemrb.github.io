---
title: LoadWindow
module: GemRB
---

**Prototype:** GemRB.LoadWindow (WindowID[, windowPack, position])

**Description:** Returns a Window. You must call LoadWindowPack before using 
this command. The window won't be displayed. If LoadWindowPack() set nonzero 
natural screen size with Width and Height parameters, the loaded window is 
then moved by (screen size - winpack size) / 2

**Parameters:**
  * a window ID, see the .chu file specification
  * windowPack: which window pack (.chu) to take the window from (defaults to current)
  * position: where to place it on screen (defaults to WINDOW_CENTER, see GUIDefines.py)

**Return value:** GWindow

**See also:** [LoadWindowPack](LoadWindowPack.md), [Window_GetControl](Window_GetControl.md), [Window_ShowModal](Window_ShowModal.md)
