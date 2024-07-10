---
title: TextArea_ListResources
module: _GemRB
---

**Metaclass Prototype:** ListResources (type [, flags])

**Description:** Lists the resources of 'type' as selectable options in the TextArea.

**Parameters:** 
  * type - one of CHR_PORTRAITS, CHR_SOUNDS, CHR_EXPORTS or CHR_SCRIPTS
  * flags:
    - for CHR_PORTRAITS chooses suffix: 0 'M', 1 'S', 2 'L'

**Return value:** list - the list of options added to the TextArea
