---
title: GetSpell
module: GemRB
---

**Prototype:** GemRB.GetSpell (ResRef[, silent])

**Description:** Returns dictionary with the specified spell's data. If silent 
is set, nothing will be printed to the console.

**Parameters:**
  * ResRef - the resource reference of the spell.
  * silent - turn off verbose output.

**Return value:** dictionary
  * 'SpellName'       - strref of unidentified name.
  * 'SpellDesc'       - strref of unidentified description.
  * 'SpellbookIcon'   - the spell's icon (.bam resref)
  * 'SpellExclusion'  - the excluded schools and alignments
  * 'SpellDivine'     - this field tells divine magics apart
  * 'SpellSchool'     - the spell's school (primary type)
  * 'SpellType'       - the type of text that appears on spell dispelling
  * 'SpellLevel'      - the spell's level
  * 'Completion'      - the spell's completion sound
  * 'SpellTargetType' - the spell's target type
  * 'SpellSecondary'  - the spell's secondary type
  * 'HeaderFlags'     - the spell's header flags
  * 'NonHostile'      - is the spell considered hostile?
  * 'SpellResRef'     - the spell's resource reference
  * 'SpellLocation'   - the spell's header ability location

**See also:** [GetItem](GetItem.md), [Button_SetSpellIcon](Button_SetSpellIcon.md), spell_structure(IESDP)

