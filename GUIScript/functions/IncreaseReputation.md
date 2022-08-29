---
title: IncreaseReputation
module: GemRB
---

**Prototype:** GemRB.IncreaseReputation (Donation)

**Description:** Increases party's reputation based on Donation. (see reputatio.2da)

**Parameters:**
  * donation - gold spent to increase reputation. You have to change the
  party's gold separately.

**Return value:** Nonzero if the reputation has been increased. The amount
of increase is multiplied by ten.

**See also:** [GameGetReputation](GameGetReputation.md), [GameGetPartyGold](GameGetPartyGold.md), [GameSetPartyGold](GameSetPartyGold.md)
