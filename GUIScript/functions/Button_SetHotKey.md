---
title: Button_SetHotKey
module: _GemRB
---

**Prototype:** _GemRB.Button_SetHotKey(char or keymaping[, modifiers=0, global=False])

**Description:** Binds a keyboard key to trigger the control event when its window is focused.
If global is set, the hot key works even if the window does not have focus.
If None is passed as the key, any existing hotkey binding is cleared.

**Parameters:**
 * char - key to bind
 * modifiers - bitfield denoting if modifier keys need to be pressed
   * GEM_MOD_SHIFT (1) - shift
   * GEM_MOD_CTRL (2) - control
   * GEM_MOD_ALT (4) - alt
 * global - boolean toggling focus requirement

**Return value:** N/A
