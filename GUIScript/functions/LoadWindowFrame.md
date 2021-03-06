---
title: LoadWindowFrame
module: GemRB
---

**Prototype:** GemRB.LoadWindowFrame (MOSResRef_Left, MOSResRef_Right, MOSResRef_Top, MOSResRef_Bottom))

**Description:** Load the parts of window frame used to decorate windows 
on higher resolutions.

**Parameters:**
  * MOSResRef_Left, MOSResRef_Right,
  * MOSResRef_Top, MOSResRef_Bottom: names of MOS files with frame parts

**Return value:** N/A

**Example:**
 (from bg2's Start.py)
    # Find proper window border for higher resolutions
    screen_width = GemRB.GetSystemVariable (SV_WIDTH)
    screen_height = GemRB.GetSystemVariable (SV_HEIGHT)
    if screen_width == 800:
      GemRB.LoadWindowFrame ('STON08L', 'STON08R', 'STON08T', 'STON08B')
    elif screen_width == 1024:
      GemRB.LoadWindowFrame ('STON10L', 'STON10R', 'STON10T', 'STON10B')

    # Windows in this winpack were originally made and placed 
    # for 640x480 screen size
    GemRB.LoadWindowPack ('START', 640, 480)
    StartWindow = GemRB.LoadWindow (0)
    GemRB.SetWindowFrame (StartWindow)

**See also:** [Window_SetFrame](Window_SetFrame.md), [LoadWindowPack](LoadWindowPack.md)
