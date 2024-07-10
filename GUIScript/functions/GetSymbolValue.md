---
title: GetSymbolValue
module: GemRB
---

**Prototype:** GemRB.GetSymbolValue (GSymbol, StringVal|IntVal)

**Metaclass Prototype:** GetValue (StringVal|IntVal)

**Description:** Returns a field of a IDS Symbol Table.

**Parameters:**
  * GSymbol - returned by a previous LoadSymbol command
  * StringVal - name of the symbol to resolve (first column of .ids file)
  * IntVal - value of the symbol to find (second column of .ids file)

**Return value:**
  * numeric, if the symbol's name was given (the value of the symbol)
  * string, if the value of the symbol was given (the symbol's name)

**Examples:**

    align = GemRB.GetPlayerStat (pc, IE_ALIGNMENT)
    ss = GemRB.LoadSymbol ('ALIGN')
    sym = GemRB.GetSymbolValue (ss, align)

The above example will find the symbolic name of the player's alignment.

**See also:** [LoadSymbol](LoadSymbol.md), [Table_GetValue](Table_GetValue.md)
