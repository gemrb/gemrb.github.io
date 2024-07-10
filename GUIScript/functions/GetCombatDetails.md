---
title: GetCombatDetails
module: GemRB
---

**Prototype:** GemRB.GetCombatDetails (pc, leftorright)

**Description:** Returns the current THAC0 and other data relating to the 
equipped weapon.

**Parameters:** 
  * pc - position in the party
  * leftorright - left or right hand weapon (main or offhand)

**Return value:** dict: 'ToHit', 'Flags', 'DamageBonus', 'Speed', 
'CriticalBonus', 'Style', 'Proficiency', 'Range', 'Enchantment', 'Slot', 
'APR', 'CriticalMultiplier', 'CriticalRange', 'ProfDmgBon', 'HitHeaderNumDice', 
'HitHeaderDiceSides', 'HitHeaderDiceBonus', 'LauncherDmgBon', 'WeaponStrBonus', 
'AC' (dict), 'ToHitStats' (dict), 'DamageOpcodes' (dict)

**See also:** [IsDualWielding](IsDualWielding.md)
