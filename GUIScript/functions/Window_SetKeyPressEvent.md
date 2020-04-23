---
title: Window_SetKeyPressEvent
module: _GemRB
layout: gs-function
---

**Prototype:** _GemRB.Window_SetKeyPressEvent (callback)

**Description:** Sets a callback function to handle key press event on window scopes. 

**Parameters:**
  * callback - Python function that accepts (windowIndex, key, mod) arguments and returns
	* 					 1 indicating successful key press consumption or 0 otherwise. 

**Return value:** N/A

**Example:**
    Window.SetKeyPressEvent (KeyPressCallback)
    return

**See also:** [QuitGame](QuitGame.md)

