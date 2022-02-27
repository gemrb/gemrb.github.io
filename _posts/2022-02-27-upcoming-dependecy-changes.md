---
title: Upcoming dependency changes
author: Jaka Kranjc
---

With 0.9.0 GemRB received Python 3 support alongside Python 2. Since the latter has been in end-of-life
mode for a while and to improve our handling of localized strings two important changes have been made.

**Starting with 0.9.1, Python 3 will be the only supported version and iconv will no longer be an
optional dependency**.

Both are ubiquitous, so we don't expect much trouble, except perhaps in some exotic platforms (eg. PS
Vita has no working Python 3 port yet). Iconv is provided as part of libc on many platforms, but BSD
and GNU also have separate libiconv implementations that are widely reusable.

Please reach out if your platform of choice requires special care.
