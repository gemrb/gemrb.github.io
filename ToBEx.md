---
title: ToBEx compatibility
---

This page lists ToBEx features that are also available in GemRB. They
use the same bits and constants to stay compatible. **They work in all
games!**

  - several deharcoded tables and spells, including difficulty, avatars,
    walksounds, bardsong and other modal actions ...
      - gemrb has more than ToBEx, so just take a peek at
        gemrb/unhardcoded/
  - items:
      - can be explicitly marked as suitable for backstabbing or not
      - can have their critical-hit protection toggled
  - spells:
      - can target invisible bit
      - can cast while silenced bit
      - spell "concentration" checks (set `SimplifiedDisruption=1` in
        `gemrb.ini`)
  - greater choice in the "always backstab" stat (which restrictions to
    apply)
  - effects:
      - extra save flags:
          - bypass mirror image
          - ignore difficulty settings (damage scaling)
      - Cutscene2 effect is the same
      - SetStat improvements
  - not all stores recharge items (in the original, bags of holding
    could recharge wands)
  - character generation
      - scrollbars for unlimited kits and co.
  - triggers and actions
      - for LoseGame, see [mods](Modding.md), you just need to
        toggle a value
  - universal 4-weapon slots: this is implemented through numwslot.2da
    like in EEs

Only things explicitly mentioned in our commit logs are on the original
list. If you want to know about any other specific feature, best to ask on the forum.
