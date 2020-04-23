---
title: TextArea_ListResources
module: _GemRB
---

**Prototype:** GemRB.ListResources (WindowIndex, ControlIndex, type [, flags])

**Metaclass Prototype:** ListResources (type [, flags])

**Description:** Lists the resources of 'type' as selectable options in the TextArea.

**Parameters:** 
  * WindowIndex, ControlIndex - control IDs
  * type - one of CHR_PORTRAITS, CHR_SOUNDS, CHR_EXPORTS or CHR_SCRIPTS
  * flags -    currently only used for CHR_PORTRAITS: 0 means the portraits with 'M' as the suffix, anything else 'S'

**Return value:** int - the number of options added to the TextArea
