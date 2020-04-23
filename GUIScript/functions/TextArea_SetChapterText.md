---
title: TextArea_SetChapterText
module: _GemRB
---

**Prototype:** GemRB.SetChapterText (Win, Ctrl, Text)

**Metaclass Prototype:** SetChapterText (Text)

**Description:**
Sets up a TextArea for scrolling the chapter text from below the TextArea 
to beyond the top.

**Parameters:** 
  * Win - window id
  * Ctrl - textarea id
  * Text - The text to set in the TA

**Example:**

    TextArea = ChapterWindow.GetControl (5)
    TextArea.SetChapterText (text)

**Return value:** N/A

**See also:**
