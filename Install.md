---
title: Setting up GemRB and the games
toc: true
sf: https://sourceforge.net/projects/gemrb/files/Releases/
---

# Download

The **latest sources and official builds** are always
available on our SourceForge **[project
page](http://sourceforge.net/projects/gemrb/files/)**. Here is a handy table with shortcuts:

|  | Release downloads | Development downloads |
| --- | :---: | :---: |
| **Binaries** | [<i class="fab fa-windows"></i> Windows]({{ page.sf }}/{{ site.version }}/gemrb-win32-196c54e.zip),<br>[<i class="fab fa-linux"></i> Linux]({{ page.sf }}/{{ site.version }}/gemrb-linux-v{{ site.version }}.tar.bz2),<br>[<i class="fab fa-apple"></i> macOS]({{ page.sf }}/{{ site.version }}/gemrb-macos-v{{ site.version }}.tar.bz2) | [Build bots](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/) |
| Source | [Tarball]({{ page.sf }}/{{ site.version }}/gemrb-{{ site.version }}-sources.tar.gz) | See [dev docs](Dev-docs.html#getting-the-code) |
| Version | {{ site.version }} | {{ site.version }}-git with build number |

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

The downloads do not come with installers, so just unpack them and run GemRB. MacOS is the only exception with its bundle. On Windows make sure you have the [Visual Studio 2013 Redistributable](https://www.microsoft.com/en-us/download/details.aspx?id=40784) (2017 for development builds), as GemRB will fail to start without two of its DLLs.

If you downloaded the sources instead, follow the [compilation instructions](Dev-docs.md##setting-up-a-development-environment).
GemRB can even run from the build dir without installing.


# Configure GemRB

GemRB uses a settings file primarily to know where to look for the game data.

1.  Copy `GemRB.cfg.sample` to a new file named `GemRB.cfg` in the same folder.
2.  **Edit `GemRB.cfg`**:
  * The only thing that **always needs to be changed** is the **path to
    the game's data files** (`GamePath`, very seldomly `CDx`). **It is crucial you get this right.**
  * If you're running from a binary package, set `GemRBPath` to `.`.

If you are curious, read the detailed explanation of all the [configuration options](Manpage.md).
The configuration filename is arbitrary, but check the note in the last section.

*Setting the paths can be tricky, so carefully read any errors that gemrb
prints to the output or GemRB.log file before exiting. See [this old
video](http://www.youtube.com/watch?v=32BZouraDPM) for a walkthrough
on how to fix the encountered problems and set up the paths properly.*

## Windows

The default config file `GemRB.cfg.sample` is preconfigured as if you unpacked the archive into `C:\`.
If you haven't, edit it with a text editor, change `PluginsPath` to `.\plugins` and remove the hash
`#` in front of it.


# Run GemRB

You will know GemRB is set up correctly once you can see the main game
screen. If that doesn't happen, check the end of the log for errors and fix the
configuration file as needed. Usually the game path is set wrong, but also IWD2
doesn't work at the preset resolution (change to `800x600`).

Run the `gemrb` binary, specifying the desired configuration: `gemrb.exe -c torment.cfg`.
If you named the configuration file `GemRB.cfg` and put it in the same folder as the binary,
that file will be used automatically and you don't need to specify anything — you can **just
click on the program**.

If you're using a touch screen, read this page for the [gesture information](Touch-input.md).
