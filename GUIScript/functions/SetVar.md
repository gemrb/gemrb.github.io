---
title: SetVar
module: GemRB
---

**Prototype:** GemRB.SetVar (VariableName, Value)

**Description:** Set a Variable of the Global Dictionary. This is an 
independent dictionary from the gamescript. It contains configuration 
variables, and provides a flexible interface between guiscript and the 
engine core. There are some reserved names that are referenced from the 
core, these are described in different places:
  * variable  : described in
  * PlayMode  - LoadGame
  * *Window   - HideGUI
  * *Position - HideGUI
  * Progress  - data_exchange

**Parameters:**
  * VariableName - the name of the variable (shorter than 32!)
  * Value        - numeric, the new value

**Return value:** N/A

**Examples:**

    GemRB.SetVar('ActionsWindow', ActionsWindow)
    GemRB.SetVar('OptionsWindow', OptionsWindow)
    GemRB.SetVar('MessageWindow', MessageWindow)
    GemRB.SetVar('ActionsPosition', 4) #BottomAdded
    GemRB.SetVar('OptionsPosition', 0) #Left
    GemRB.SetVar('MessagePosition', 4) #BottomAdded
The above lines set up some windows of the main game screen.

**See also:** [Control_SetVarAssoc](Control_SetVarAssoc.md), [SetToken](SetToken.md), [LoadGame](LoadGame.md), [HideGUI](HideGUI.md), [data_exchange](data_exchange.md)
