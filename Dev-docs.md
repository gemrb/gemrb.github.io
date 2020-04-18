---
title: Developer documentation
---

This is the starting page for most of our technical documentation. Some extra
nuggets can be found in the gemrb/docs/ subdir, but it's old and very specific.


## Getting the code
Download the [git version of GemRB](https://github.com/gemrb/gemrb), via
the **Clone or download** button, the git command-line tool or your IDE.

**However**, if you plan to submit a pull request, log in to GitHub, visit
the linked GitHub page and first **fork the repository** before cloning the
code. Once you push your changes to your fork, you can easily create a pull
request through the web interface.

## Setting up a development environment

GemRB tries to not reinvent the wheel, so it uses several libraries as
dependencies. Before attempting to build, be sure to install them (with all
their header/devel packages if they exist and for the same architecture, eg.
x86-64 or ARM)! The up to date list can be found in the
[INSTALL](https://github.com/gemrb/gemrb/blob/master/INSTALL) file.

The file also contains general compilation instructions, but here's the gist.
1. Windows
Follow the [MSVC]() or the [MSYS2]() guide. https://github.com/gemrb/gemrb/issues/611
2. macOS
There's an xcode project file included. You can also try generating it with
cmake.
3. Open source platforms
```
mkdir build
cd build
cmake .. [some options] # or cmake-gui ..
make -j3
```

**Note:** GemRB can run from the build dir, so there's no need to install it by
running the `install` target.

## Project infrastructure
The [organisation](https://github.com/gemrb) currently has these repositories:
- gemrb - the main project
- gemrb.github.io — this very website
- iesh - IE python shell

The engine sees by far the most action, but if you're interested in something
different, all the projects are open to contribution.

GitHub hosts the code, the issue trackers and this page.
[Sourceforge](http://sourceforge.net/projects/gemrb/) hosts the original
project page and download center. We're also registered on [Open 
HUB](https://www.openhub.net/p/gemrb?p=GemRB) for some assorted stats.

Check the main [README](https://github.com/gemrb/gemrb/blob/master/README.md)
file to see our a header with build bot status (Travis, AppVeyor), some
static code analyzers and more.

## The engine
  - [Engine Overview](Engine-overview.md)
startup details

## Workflow
see contributing

debugging tips - tools, ie tools ... ["Cheats"](Cheats.md) console + hotkeys
bots and tests
for dev docs: https://github.com/gemrb/gemrb/issues/659#issuecomment-611816962 debugging loading problems
iesh + other tools 

## Exploring the games
As far as game resources go, the main complementary documentation is on the
[IESDP](https://gibberlings3.github.io/iesdp/) - The Infinity Engine Structures
Description Project. It represents the accumulated knowledge of IE internals and
in a sense, GemRB could be considered a reference implementation. Sometimes it is
also helpful to look at the sources of other tools like
[NearInfinity](https://github.com/NearInfinityBrowser/NearInfinity).

Our [iesh](https://github.com/gemrb/iesh) is not polished, but is exceptionally
useful when trying to figure out if anything uses fields or bits previously
thought unused or not working. Or if you need to do any processing. Basically
for anything that is much faster when automated, especially since most IE tools
have poor search capabilities.

## The minimal dataset

GemRB comes with a minimal dataset, that can be used to check if the core
core functionality still works. It just fires up the engine and as soon as it
loads the Start script, it exits. That is the expected behaviour. No window
is opened.

If you installed GemRBb, try the included fhs.cfg:

    gemrb -c /usr/share/gemrb/minimal/fhs.cfg

But, you can just run the sample config from the build directory as-is:

    gemrb/gemrb -c ../gemrb/GemRB.cfg.noinstall.sample

This is what our build bots use as a trivial sanity check.

# TODO

converter:
https://pandoc.org/try/?text=&from=dokuwiki&to=gfm

  * [cocoa](http://www.gemrb.org/wiki/doku.php?id=cocoa)
  - Check the [man page](Manpage.md) for all the configuration
    options and commandline parameters
  - [Support for non-ASCII characters](Text-encodings.md)

### GUIScript documentation

  - [Introduction](GUIScript/Index.md)
  - [Function index](GUIScript/Functions.md)





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


