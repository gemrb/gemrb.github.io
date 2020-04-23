---
title: LoadWindowPack
module: GemRB
---

**Prototype:** GemRB.LoadWindowPack (CHUIResRef[, Width=0, Height=0])

**Description:** Loads a WindowPack into the Window Manager Module. 
Only one windowpack may be open at a time, but once a window was selected 
by LoadWindow, you can get a new windowpack.

**Parameters:** 
  * CHUIResRef: the name of the GUI set (.CHU resref)
  * Width, Height: if nonzero, they set the natural screen size for which 
      the windows in the winpack are positioned. LoadWindow() uses this 
      information to automatically reposition loaded windows.

**Return value:** N/A

**Example:**

      LoadWindowPack ('START', 640, 480)

**See also:** [LoadWindow](LoadWindow.md), [LoadWindowFrame](LoadWindowFrame.md)

