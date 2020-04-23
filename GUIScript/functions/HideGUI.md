---
title: HideGUI
module: GemRB
---

**Prototype:** GemRB.HideGUI ()

**Description:**
Hides the game GUI (all windows except the GameControl window). It is also used
 before a major change is made on a GUI window to avoid flickering. After the
 changes, an UnhideGUI() command should be issued too.

A list of reserved names (variables) and what they hold:
  * MessageWindow - contains a TextArea for ingame messages/dialogue
  * OptionsWindow - a series of buttons for Inventory/Spellbook/Journal,etc
  * PortraitWindow - a series of portrait buttons
  * ActionsWindow - a series of buttons to Attack/Talk, etc.
  * TopWindow - unused (might be removed later)
  * OtherWindow - this window usually covers the GameControl, it is used to display    maps, inventory, journal, etc.
  * FloatWindow - special window which floats on top of the GameControl

All these windows are associated with a position variable too, these are
 MessagePosition, OptionsPosition, etc.
The position value tells the engine the window's relative position to the
 GameControl GUI. The engine doesn't make any distinction between these
 windows based on their reference name. The differences come from the
position value:
  * -1 - no position (floats over GameControl)
  * 0  - left
  * 1  - bottom
  * 2  - right
  * 3  - top
  * 4  - bottom (cumulative)

**Parameters:** N/A

**Return value:** 1 on success

**See also:** [UnhideGUI](UnhideGUI.md), [Window_Invalidate](Window_Invalidate.md), [Window_SetVisible](Window_SetVisible.md)

