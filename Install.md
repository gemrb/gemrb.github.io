---
title: Install
---

# Download

The **latest sources and official builds** are always
available on our SourceForge **[project
page](http://sourceforge.net/projects/gemrb/files/)**.

buttons / grid:
- Latest release build (OS icons) -> https://sourceforge.net/projects/gemrb/files/ 
- Latest release source? (could also be above)
- Latest development build (OS icons?) -> https://sourceforge.net/projects/gemrb/files/Buildbot%20Binaries/
- Latest development source @ github (link to dev docs?)

The Android and iOS builds are currently unmaintained.

# Getting the Games

You will need one of the original Infinity Engine games or **the free
[BG II demo](https://duckduckgo.com/?q=bg2+demo).** If you're not using Windows, here are
[some ideas](Installing-games.md) on how to complete the install. GemRB comes with its own demo, but it is trivial.

Due to low interest, GemRB does [not support the EE versions](https://github.com/gemrb/gemrb/issues/164)
of the games, though there has always been considerable feature overlap.

After you have the games, you can also install [any mods](). They should work out of the box, but
any that modify the EXE files could lack the functionality those hacks achieved.

# Install

The downloads do not come with installers, so just unpack them and run GemRB. MacOS is the only exception with its bundle.

If you downloaded the sources instead, follow the [compilation instructions]().
GemRB can even run from the build dir without installing.

# TODO

converter:
https://pandoc.org/try/?text=&from=dokuwiki&to=gfm

 - Configure gemrb
 - How to run
   - Test run

Also?
  * [touch](http://www.gemrb.org/wiki/doku.php?id=input:touch) page
  * [manpage](http://www.gemrb.org/wiki/doku.php?id=docs:manpage) base for configuration page and/or autogenerate
  * [encodings](http://www.gemrb.org/wiki/doku.php?id=engine:encodings) page
  * [debug_keys](http://www.gemrb.org/wiki/doku.php?id=debug_keys) page, are any even different? IESDP lists them ... Link and display only differences

## Configuring gemrb

### Manually

1.  Copy one of the GemRB.cfg samples and rename it to
    \<game\_name\>.cfg . You can name configuration files arbitrarily,
    but this way makes the most sense if you'll be running multiple
    games.
2.  <span class="underline">**Edit GemRB.cfg. The only thing that always
    needs to be changed is the path to the game's data files (GamePath,
    very seldomly CDx). It is crucial you get this right.**</span> 

Setting the paths can be tricky, so carefully read the errors that gemrb
prints to the output before exiting. See [this
video](http://www.youtube.com/watch?v=32BZouraDPM) (linux) for a
*walktrough* on how to fix the encountered problems and set up the paths
properly.

## Test run

You will know gemrb is working perfectly once you can see the main game
screen. If that doesn't happen, check the console for errors and fix the
configuration file as needed. Usually some path is set wrong.

  - Run the "gemrb" binary (you can specify the desired configuration
    like this: gemrb -c torment.cfg)
  - You can also link the gemrb binary to \<game\_name\> and the start
    it with that link, so gemrb will automatically pick the right
    configuration file. That means there is no need to pass -c anymore
    (pst vs gemrb -c pst.cfg)

### The minimal dataset

Since 0.6.1 GemRB comes with a minimal dataset, that can be used to
check if gemrb is configured correctly right out of the box.

If you installed gemrb, try the included fhs.cfg:

    gemrb -c /usr/share/gemrb/minimal/fhs.cfg

If you don't want to install, you can just run the sample config from
the build directory as-is:

    gemrb/gemrb -c ../gemrb/GemRB.cfg.noinstall.sample

It will exit as soon as it loads the Start script. That is the expected
behaviour.


  
------
Move to dev docs:

  * [cocoa](http://www.gemrb.org/wiki/doku.php?id=cocoa)

## Main development repository

  - [GitHub Browser](https://github.com/gemrb/gemrb)
  - Anonymous access (read-only without forking): 

    git clone git://github.com/gemrb/gemrb.git

  - Developer access (full):

    git clone git@github.com:gemrb/gemrb.git

If you plan to submit a pull request, log in to GitHub, visit our page
there (first link), fork the repository and then clone your fork. Once
you push your changes to your fork, you can easily create a pull request
through the web interface.

------
## How relevant is this vs. INSTALL vs. pointing somewhere else?


[windows specific (mingw) instructions](http://www.gemrb.org/wiki/doku.php?id=install:windows) see https://github.com/gemrb/gemrb/issues/611

### Compile it yourself

#### Dependencies

Make sure you have SDL, python, zlib and a compiler installed (with all
their header/devel packages if they exist). You will also need either
cmake (recommended) or autotools (unmaintained).

Full list: [Python](http://www.python.org/),
[SDL](http://www.libsdl.org), [zlib](http://http://zlib.net/),
[OpenAL](http://http://connect.creativelabs.com/openal/default.aspx) or
SDL\_Mixer (if you want sound),
[libPNG](http://http://www.libpng.org/pub/png/libpng.html) (optional),
[Freetype](http://www.freetype.org/) (if you want TTF fonts),
[iconv](http://www.gnu.org/software/libiconv/) (if you want TTF fonts
while using non-unicode dialog.tlk)

When not using an IDE to build, make will be required. Also, on Windows
a Cygwin environment can be used instead of MSVC.

#### Getting the sources

First you'll need to get the source. Either in the form of a *release
tarball* or the *latest source* from GIT (preferred).

The advantage of the development tree is that you always have the most
updated version, with bugfixes and features added after release. Of
course, you may also get extra bugs, while the changes are being
polished.

This probably gets more complicated if you're on Windows because, but
you can try running the builds from
[here](http://buildbot.gemrb.org/binaries/GemRB-win32-latest.zip).

##### Source tarball

Download the source tarball from the [project
page](http://sourceforge.net/projects/gemrb/).

##### Latest tree from GIT

Create a (readonly) *checkout* of gemrb in the current dir with:

    git clone git://github.com/gemrb/gemrb.git

#### Compilation

If you have the tarball, extract it. The rest of the instructions are
the same as for building from Git. First move to the source directory
then run the following:

    mkdir build
    cd build
    cmake ..
    make -j2

By default, GemRB is installed into /usr/local ("fhs"). You can pass
-DLAYOUT with "home" or "opt" to change the general layout and -DPREFIX
to change the install path prefix. Pass -DCMAKE\_BUILD\_TYPE=Debug to
cmake if you want to create a debug build.

If you're using one of the available project files, just build as usual.

You can finally install GemRB (optional) by `make install`.
