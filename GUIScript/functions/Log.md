---
title: Log
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.Log (log_level, owner, message)

**Description:** Log a message to GemRB's logging system.

**Parameters:**
  * log_level - integer log level (from GUIDefines.py)
    * LOG_NONE = -1
    * LOG_FATAL = 0
    * LOG_ERROR = 1
    * LOG_WARNING = 2
    * LOG_MESSAGE = 3
    * LOG_COMBAT = 4
    * LOG_DEBUG = 5
  * owner - name of the context or owner of the message
  * message - string to log

**Return value:** N/A
