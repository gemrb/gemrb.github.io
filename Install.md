---
title: Setting up GemRB and the games
toc: true
---

# Download

The **latest sources and official builds** are always
available on our SourceForge **[project
page](http://sourceforge.net/projects/gemrb/files/)**. Here is a handy table with shortcuts:

|  | Release downloads | Development downloads |
| --- | :---: | :---: |
| **Binaries** | [<i class="fab fa-windows"></i> Windows](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/Windows/AppVeyor/gemrb-win32-196c54e.zip/download),<br>[<i class="fab fa-linux"></i> Linux](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/Linux/gemrb-2019-11-24v0.8.6.tar.bz2/download),<br>[<i class="fab fa-apple"></i> macOS](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/Apple/OSX/gemrb-2019-11-24v0.8.6.tar.bz2/download) | [Build bots](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/) |
| Source | [Tarball](https://sourceforge.net/projects/gemrb/files/GemRB%20Sources/GemRB%200.8.6%20Sources/gemrb-0.8.6.tar.gz/download) | See [dev docs](Dev-docs.html#getting-the-code) |
| Version | 0.8.6 | 0.8.6-git with build number |

The Android and iOS builds are [currently unmaintained](https://github.com/gemrb/gemrb/issues/529).

# Getting the games

You will need one of the original Infinity Engine games or **the free
[BG II demo](https://duckduckgo.com/?q=bg2+demo).** If you're not using Windows, here are
[some ideas](Installing-games.md) on how to complete the install. GemRB comes with its own demo, but it is trivial.

Due to low interest, GemRB does [not support the EE versions](https://github.com/gemrb/gemrb/issues/164)
of the games, though there has always been considerable feature overlap.

After you have the games, you can also install [any mods](Modding.md). They should work out of the box, but
any that modify the EXE files could lack the functionality those hacks achieved. Installing the
[fixpacks](Common-problems.md#game-bugs) is highly recommended.

# Install

The downloads do not come with installers, so just unpack them and run GemRB. MacOS is the only exception with its bundle.

If you downloaded the sources instead, follow the [compilation instructions](Dev-docs.md##setting-up-a-development-environment).
GemRB can even run from the build dir without installing.

TODO: include anything relevant from the [Pre-build git binaries](http://www.gemrb.org/wiki/doku.php?id=install:windows) section.

# Configure GemRB

GemRB uses a settings file primarily to know where to look for the game data.

1.  Copy one of the GemRB.cfg samples and rename as you want. We'll refer to it as GemRB.cfg from here on.
2.  **Edit GemRB.cfg. The only thing that always
    needs to be changed is the path to the game's data files (GamePath,
    very seldomly CDx). It is crucial you get this right.**

If you are curious, read the detailed explanation of all the [configuration options](Manpage.md).

*Setting the paths can be tricky, so carefully read any errors that gemrb
prints to the output or GemRB.log file before exiting. See [this old
video](http://www.youtube.com/watch?v=32BZouraDPM) for a
walktrough on how to fix the encountered problems and set up the paths
properly.*

# Run GemRB

You will know GemRB is set up correctly once you can see the main game
screen. If that doesn't happen, check the end of the log for errors and fix the
configuration file as needed. Usually the game path is set wrong.

Run the "gemrb" binary, specifying the desired configuration: `gemrb.exe -c torment.cfg`.
If you name the config "GemRB.cfg" and put it in the same folder as the binary, it will use
that configuration file automatically and you don't need to specify anything.

If you're using a touch screen, read this page for the [gesture information](Touch-input.md).
