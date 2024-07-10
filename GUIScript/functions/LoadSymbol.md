---
title: LoadSymbol
module: GemRB
---

**Prototype:** GemRB.LoadSymbol (IDSResRef)

**Description:** Loads a IDS Symbol List. In case it was already loaded, 
it will return the list's existing reference (won't load it again).

**Parameters:**
  * IDSResRef - the symbol list's name (.ids resref)

**Return value:** GSymbol object, None if loading failed

**See also:** [UnloadSymbol](UnloadSymbol.md)

