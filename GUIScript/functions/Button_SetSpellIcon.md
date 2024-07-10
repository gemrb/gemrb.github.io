---
title: Button_SetSpellIcon
module: _GemRB
---

**Metaclass Prototype:** SetSpellIcon (SPLResRef[, Type, Tooltip, Function])

**Description:** Sets Spell icon image on a Button control. Type determines 
the icon type, if set to 1 it will use the Memorised Icon instead of the 
Spellbook Icon

**Parameters:**
  * SPLResRef - the name of the spell (.spl resref)
  * Type - 0 (default, use parchment background) or 1 (use stone background)
  * Tooltip - 0 (default); if 1, set the tooltip 'F<n> <spell_name>'
  * Function - F-key number to be used in the tooltip above

**Return value:** N/A

**See also:** [Button_SetItemIcon](Button_SetItemIcon.md)
