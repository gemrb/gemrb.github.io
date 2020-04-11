# TODO

converter:
https://pandoc.org/try/?text=&from=dokuwiki&to=gfm

  * [cocoa](http://www.gemrb.org/wiki/doku.php?id=cocoa)

WIP

Some general documentation can be found in the docs/ subdir. 
debugging tips - ctrl-m + other hotkeys, tools, ie tools ...

for dev docs: https://github.com/gemrb/gemrb/issues/659#issuecomment-611816962 debugging loading problems
iesh + org/repo structure



### GemRB man page

  - Check the [man page](/docs/manpage) for all the configuration
    options and commandline parameters

### Engine documentation

  - [Engine Overview](/engine/start)
  - [Support for non-ASCII characters](/engine/encodings)
  - See [IESDP](http://gibberlings3.net/iesdp/) for a nearly complete
    and up to date documentation of the Infinity Engine.

### GUIScript documentation

  - [Introduction](/guiscript/start)
  - [Function index](/guiscript/index)




## The minimal dataset

Since 0.6.1 GemRB comes with a minimal dataset, that can be used to
check if gemrb is configured correctly right out of the box.

If you installed gemrb, try the included fhs.cfg:

    gemrb -c /usr/share/gemrb/minimal/fhs.cfg

If you don't want to install, you can just run the sample config from
the build directory as-is:

    gemrb/gemrb -c ../gemrb/GemRB.cfg.noinstall.sample

It will exit as soon as it loads the Start script. That is the expected
behaviour.



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

------

## Technical GemRB start up details

When you run GemRB, here is what happens:

1.  The core initialises, loads all the plugins and preloads some data
2.  The main game loop is started
3.  Start.py in the game's guiscript directory is run
      - LoadGame(None) will set up a new game by loading the default GAM
        file and linked resources
      - Party members can be created with CreatePlayer()
      - EnterGame()
      - ...
4.  MessageWindow.py is run
5.  Game is up and drawing
6.  QuitGame() and Quit() to terminate

Other guiscripts are run on demand, but mostly by direct calls from the
guiscript side.


## Useful links

  - Project pages:
    [Sourceforge](http://sourceforge.net/projects/gemrb/), [Open
    HUB](https://www.openhub.net/p/gemrb?p=GemRB)
  - [IESDP](https://gibberlings3.github.io/iesdp/) - The Infinity Engine Structures Description Project
