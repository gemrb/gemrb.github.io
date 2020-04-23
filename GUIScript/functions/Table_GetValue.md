---
title: Table_GetValue
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.GetTableValue (TableIndex, RowIndex/RowString, ColIndex/ColString, Type)

**Metaclass Prototype:** GetValue (RowIndex/RowString, ColIndex/ColString[, Type])

**Description:** Returns a field of a 2DA Table. The row and column indices 
must be of same type (either string or numeric), the return value will be 
of the same type, unless Type is specified and different.

**Parameters:**
  * TableIndex - returned by a previous LoadTable command.
  * RowIndex, ColIndex - numeric row/column indices
  * RowString, ColString - the row/column names as written in the 2da file
  * Type - forces a specific return type (GUIDefines.py)
    * -1 - default
    * GTV_STR 0 - string
    * GTV_INT 1 - int
    * GTV_STAT 2 - stat symbol (translated to numeric - value of stat)
    * GTV_REF 3 - string reference (expanded to string)

**Return value:** numeric or string, based on the indices or type

**See also:** [GetSymbolValue](GetSymbolValue.md), [Table_FindValue](Table_FindValue.md), [LoadTable](LoadTable.md)
