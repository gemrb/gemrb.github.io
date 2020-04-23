---
title: Table_GetColumnCount
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.GetTableColumnCount (TableIndex[, Row])

**Metaclass Prototype:** GetColumnCount ([Row])

**Description:** Returns the column count of the specified row in a 2DA Table.

**Parameters:**
  * TableIndex - returned by a previous LoadTable command.
  * Row        - the row of the table, if omitted, defaults to 0

**Return value:** numeric

**See also:** [LoadTable](LoadTable.md), [Table_GetRowCount](Table_GetRowCount.md)
