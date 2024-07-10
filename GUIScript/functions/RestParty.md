---
title: RestParty
module: GemRB
---

**Prototype:** GemRB.RestParty (flags, movie, hp)

**Description:** Makes the party rest. It is possible to check various 
things that may forbid resting (hostile creatures, area flags, party 
scattered). It is possible to play a movie or dream too.

**Parameters:**
  * flags - which checks to run?
  * movie - a number, see restmov.2da
  * hp    - hit points healed, 0 means full healing

**Return value:** dict
  * Error: True if resting was prevented by one of the checks
  * ErrorMsg: a strref with a reason for the error
  * Cutscene: True if a cutscene needs to run

