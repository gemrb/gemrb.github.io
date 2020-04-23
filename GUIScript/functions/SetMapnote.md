---
title: SetMapnote
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.SetMapnote(X, Y, color, text)

**Description:** Adds or removes a mapnote to the current map (area).

**Parameters:**
  * X, Y - the position of the mapnote
  * color - the color index (0-7) of the note (in case of PST it is only 0 or 1)
  * text - string, the text of the note. If it's empty, the mapnote is removed.

**Return value:** N/A

**See also:** [Window_CreateMapControl](Window_CreateMapControl.md)

