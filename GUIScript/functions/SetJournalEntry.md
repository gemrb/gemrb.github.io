---
title: SetJournalEntry
module: GemRB
---

**Prototype:** GemRB.SetJournalEntry (strref[, section, chapter])

**Description:** Sets a journal journal entry with given chapter and section. 
If section was not given, then it will delete the entry. Chapter is 
optional, if it is omitted, then the current chapter will be used. If 
strref is -1, then it will delete the whole journal.

**Parameters:**
  * strref - strref of the journal entry
  * section - the section of the journal (only if the journal has sections)
  * chapter - the chapter of the journal entry

**Return value:** N/A

**See also:** [GetJournalEntry](GetJournalEntry.md)

