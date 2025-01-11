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
| **Binaries** | [<i class="fab fa-windows"></i> Windows]({{ page.sf }}/{{ site.version }}/gemrb-win32-v{{ site.version }}.zip),<br>[<i class="fab fa-linux"></i> Linux]({{ page.sf }}/{{ site.version }}/gemrb-linux-v{{ site.version }}.AppImage),<br>[<i class="fab fa-apple"></i> macOS x86]({{ page.sf }}/{{ site.version }}/gemrb-macos-v{{ site.version }}.tar.bz2),<br>[<i class="fab fa-apple"></i> macOS ARM64]({{ page.sf }}/{{ site.version }}/gemrb-macos-arm64-v{{ site.version }}.zip) ([Mac Source Ports alternative](https://www.macsourceports.com/sourceport/gemrb)) | [Build bots](https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/) |
| Source | [Tarball]({{ page.sf }}/{{ site.version }}/gemrb-{{ site.version }}-sources.tar.gz) | See [dev docs](Dev-docs.html#getting-the-code) |
| Version | {{ site.version }} | {{ site.version }}-git with build number |

The Android and iOS builds are [currently unmaintained](https://github.com/gemrb/gemrb/issues/529).


# Getting the games

You will need one of the original Infinity Engine games or **the free
[BG II demo](https://duckduckgo.com/?q=bg2+demo).** If you're not using Windows, here are
[some ideas](Installing-games.md) on how to complete the install. GemRB comes with its own demo, but it is short.

Due to low interest, GemRB does [not support the EE versions](https://github.com/gemrb/gemrb/issues/164)
of the games yet. Experimental support for bg2ee is present, but it is not ready for prime time yet.

After you have the games, you can also install [any mods](Modding.md). They should work out of the box, but
any that modify the EXE files could lack the functionality those hacks achieved. Installing the
[fixpacks](Common-problems.md#game-bugs) is highly recommended.


# Install

The downloads do not come with installers, so **just unpack them in a game folder** and run GemRB.
MacOS is the only exception with its bundle. On Windows make sure you have the [Visual Studio 2017 Redistributable](https://aka.ms/vs/15/release/VC_redist.x86.exe), as GemRB will fail to start without two of its DLLs.

If you downloaded the sources instead, follow the [compilation instructions](Dev-docs.md##setting-up-a-development-environment).
GemRB can even run from the build dir without installing.


# Configure GemRB

Consider changing settings only after running GemRB for the first time. In this case you can
skip this whole section.
{: .notice--warning}

GemRB uses a settings file primarily to know where to look for the game data when not
running from within a game folder or when the path is not passed to it. The other reason you
might want to edit it is to change other settings like resolution, input tweaks or debugging toggles.

Edit the shipped **`GemRB.cfg`**: the only thing that always needs to be changed (unless you installed
GemRB in a game folder) is the **path to the game's data files** (`GamePath`). It is crucial you get
this right to be able to use the configuration.

If you are curious, read the detailed explanation of all the [configuration options](Manpage.md).
The configuration filename is arbitrary, but check the note in the *Options* section.

You can create a config file with only the keys that you want to change. For example, you can set just the `Width` and `Height` resolution options if the game and engine data is found some other way (eg. in Linux AppImage packages).
{: .notice--warning}

# Run GemRB

Run it as any other program. :)
{: .notice--warning}

You will know GemRB is set up correctly once you can see the main game
screen. If that doesn't happen, check the end of the log for errors and fix the
configuration file as needed. Usually the game path is set wrong.

Run the `gemrb` binary, optionally specifying the desired configuration: `gemrb.exe -c torment.cfg`
or game path: `gemrb.exe /games/gog/iwd2`.

If you named the configuration file `GemRB.cfg` and put it in the same folder as the binary,
that file will be used automatically and you don't need to specify anything — you can **just
click on the program**.

If you're using a touch screen, read this page for the [gesture information](Touch-input.md).

## How to run the GemRB demo?

The quickest way, without any configuration, is to **just run GemRB** without any parameters. It will run the demo if it can't
find any other game data. So make sure you haven't unpacked it in a game dir and voilà!
