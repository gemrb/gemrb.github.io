---
title:  "Windows builds are back, through AppVeyor"
author: Jaka Kranjc
---

EDIT: See short instructions here:

http://www.gemrb.org/wiki/doku.php?id=install:windows
---

After a few lost days of annoying fights throughout our stack, automatic windows builds are finally back!
:wavey: Now using AppVeyor, something similar to Travis, but with windows hosts*.
 
They'll all be here:
https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/Windows/AppVeyor/

Install python2 if you don't have it yet:
https://www.python.org/ftp/python/2.7.12/python-2.7.12.msi

It's untested, so please let me know if it works properly. It's a 32bit build using SDL1 and all our optional
dependencies except for vlc and vorbis — nothing you could notice.

From now on, they'll be generated after each push again. Commits and pull requests will be tested for msvc (13)
compatibility, but only on the master branch.


\* *(Luckily it doesn't need a configuration file in the repo, since it took 89 iterations to get right!)*
