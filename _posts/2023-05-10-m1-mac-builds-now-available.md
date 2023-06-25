---
title: M1 mac builds now available
author: Jaka Kranjc
---

In the download section, [development downloads](Install.html), you can now also find builds
for the newer mac hardware not using x86 or PPC architectures. Release builds will be
available starting with the next release. All this is possible thanks to [Cirrus CI](https://cirrus-ci.org).

Do note that you currently **have to have SDL2 and SDL2_mixer installed** (eg. from brew).
Without the first GemRB will crash on start, without the second there will be no audio.
We bundle both, but something is going wrong and they don't get used when running.
Testers and developers who can improve the package creation are invited to contribute to
solving this mistery and improving the CMake-backed package generation.
