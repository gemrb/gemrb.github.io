---
title:  "GemRB 0.2.5 released"
author: Jarda Benkovsky
---

Hi all,
we made another tasty release of GemRB. This time the linux binary hopefully works.

What's new?

New features:
- Save game
- Effects are now loaded
- Equipping effects in items
- Spawn points in areas
- Textscreen (scrolled text between chapters)

Improved features:
- GameScript is now much more reliable: Action override works, triggers fire once and then get cleared
- fully working Store screen
- fixed padding of message window rows (in dialogs)

Release note for linux binary:

This package is meant to be unpacked into /usr/local (or into /usr/local/stow/gemrb). 
Hopefully the libraries should load properly this time.

- don't forget to do ldconfig after installing the package
- edit the config file
