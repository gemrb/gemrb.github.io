---
title: LoadTable
module: GemRB
---

**Prototype:** GemRB.LoadTable (2DAResRef[, ignore_error=0])

**Description:** Loads a 2DA Table. In case it was already loaded, it 
will return the table's existing reference (won't load it again).

**Parameters:** 
  * 2DAResRef    - the table's name (.2da resref)
  * ignore_error - boolean, if set, handle missing files gracefully

**Return value:** GTable

**See also:** [UnloadTable](UnloadTable.md), [LoadSymbol](LoadSymbol.md)
