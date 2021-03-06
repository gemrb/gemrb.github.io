---
title: GetJournalEntry
module: GemRB
---

**Prototype:** GemRB.GetJournalEntry (chapter, index[, section])

**Description:** Returns dictionary representing journal entry with given 
chapter, section and index. Section will default to zero.

**Parameters:**
  * chapter - the chapter of the journal entry
  * index - the index of the entry in the given section/chapter
  * section - the section of the journal to use

**Return value:** dictionary with the following fields:
  * 'Text'     - strref of the journal entry
  * 'GameTime' - time of entry
  * 'Section'  - same as the input parameter
  * 'Chapter'  - same as the input parameter

**See also:** [GetJournalSize](GetJournalSize.md), [SetJournalEntry](SetJournalEntry.md)
