---
title: SetTimedEvent
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.SetTimedEvent (FunctionName, rounds)

**Description:** Sets a timed event to be called by the Game object. If 
there is no game loaded, this command is ignored. If the game is unloaded, 
the event won't be called.

**Parameters:** 
  * FunctionName - a python function object
  * rounds       - the delay with which the function should be called

**Return value:** N/A

**See also:** [Control_SetEvent](Control_SetEvent.md)

