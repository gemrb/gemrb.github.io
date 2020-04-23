---
title: Table_GetColumnIndex
module: _GemRB
---

**Prototype:** GemRB.GetTableColumnIndex (TableIndex, ColumnName)

**Metaclass Prototype:** GetColumnIndex (ColumnName)

**Description:** Returns the index of a column in a 2DA Table.

**Parameters:**
  * TableIndex - returned by a previous LoadTable command.
  * ColumnName - a column label

**Return value:** numeric, -1 if column doesn't exist

**See also:** [LoadTable](LoadTable.md), [Table_GetRowIndex](Table_GetRowIndex.md)
