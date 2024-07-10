---
title: Table_FindValue
module: _GemRB
---

**Prototype:** GemRB.FindTableValue (TableIndex, ColumnIndex, Value[, StartRow])

**Metaclass Prototype:** FindValue (ColumnIndex, Value[, StartRow])

**Description:** Returns the first row index of a field value in a 2DA 
Table. If StartRow is omitted, the search starts from the beginning.

**Parameters:**
  * TableIndex - integer, returned by a previous LoadTable command.
  * Column - index or name of the column in which to look for value.
  * Value - value to find in the table
  * StartRow - integer, starting row (offset)

**Return value:** numeric, None if the value isn't to be found

**See also:** [LoadTable](LoadTable.md), [Table_GetValue](Table_GetValue.md)
