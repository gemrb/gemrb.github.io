---
title: SetTimer
module: GemRB
---

**Prototype:** GemRB.SetTimer (callback, interval[, repeats])

**Description:** Set callback to be called repeatedly at given interval. 
This is useful for things like running a twisted reactor.

**Parameters:**
  * callback - python function to run
  * interval - time interval in ticks
  * repeats - the number of times to repeat the action before expiring the timer

**Return value:** N/A
