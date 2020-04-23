---
title: EnterGame
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.EnterGame ()

**Description:** Starts new game and enters it. 
It destroys all existing windows, and creates a GameControl window as the 0th 
window (the GameControl object will be the games 0th control). 
You should already have loaded a game using LoadGame(), otherwise the engine 
may terminate. The game won't be entered until the execution of the current 
script ends, but a LoadGame() may precede EnterGame() in the same function
(SetNextScript too).

**Parameters:** N/A

**Return value:** N/A

**See also:** [QuitGame](QuitGame.md), [LoadGame](LoadGame.md), [SetNextScript](SetNextScript.md)
