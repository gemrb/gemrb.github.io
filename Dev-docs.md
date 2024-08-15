---
title: Developer documentation
toc: true
---

This is the starting page for most of our technical documentation. Some extra
nuggets can be found in the `gemrb/docs/` subdir, but they're old and very
specific.

Quick link: [GUIScript documentation](GUIScript/Index.md)

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

The file also contains general compilation instructions, but here's the gist:
1. **Windows**:
Follow the [MSVC](MSVC-build.md) or the [MSYS2/MinGW](MSYS2-build.md) guide.
They include instructions for installing the dependencies.
2. **macOS**:
There's an xcode project file included. You can also try generating it with
cmake.
3. Open source platforms
```
mkdir build
cd build
cmake .. -DCMAKE_BUILD_TYPE=Debug
make -j3
```

**Note:** GemRB can run from the build dir, so there's no need to install it by
running `make install`.


## Project infrastructure

The [organisation](https://github.com/gemrb) currently has these repositories:
- gemrb - the main project
- gemrb.github.io — this very website
- iesh - IE python shell
- gemrb-assets - for demo data source files, misc project art and more

The engine sees by far the most action, but if you're interested in something
different, all the projects are open to contribution.

GitHub hosts the code, the issue trackers and this page.
[Sourceforge](http://sourceforge.net/projects/gemrb/) hosts the original
project page, mailing lists and download center. We're also registered on [Open 
HUB](https://www.openhub.net/p/gemrb?p=GemRB) for some assorted stats.

Check the main [README](https://github.com/gemrb/gemrb/blob/master/README.md)
file to see our a header with build bot status, some
static code analyzers and more.


## The engine

We have a separate page dedicated to the [Engine overview](Engine-overview.md),
discussing the overall architecture and file layout.

Read about our [support for non-ASCII characters](Text-encodings.md).


### Technical start up details

When you run GemRB, here is what happens:

1. The core initialises, loads all the plugins and preloads some data.
2. The main game loop is started.
3. Main.py in the main GUIScript directory is ran. If unset, GameType
is autodetected through Autodetect.py files.
4. More core functionality and asset loading occurs.
5. The main loop starts.
6. Start.py's OnLoad method in the game's GUIScript directory is ran:
     - LoadGame(None) will set up a new game by loading the default GAM
       file and linked resources.
     - Party members can be created with CreatePlayer().
     - ...
     - EnterGame() to start the GameControl and enter the map.
7. MessageWindow.py is run.
8. Game is up and drawing.
9. ...
10. QuitGame() and Quit() to terminate.

Other guiscripts are run on demand, but mostly by direct calls from the
guiscript side. Read the GUIScript [introduction](GUIScript/Index.md) to
learn more or access the [function index](GUIScript/Functions.md) directly.


## Workflow

Check out [CONTRIBUTING]({{ site.contribute }}) for tips on where to start,
what to work on, tools, useful links and more.

Besides those tools, check our ["Cheats"](Cheats.md) page for a handful of useful
hotkeys and instructions for using our inbuilt python console.

Open issues with gists or draft pull requests if you want a structured discussion
of your changes before they are ready for uptake. Otherwise just submit the PR.


### Save game compatibility

... is something we strive for. The originals are often annoyingly specific
in how they want the file and fields to look, so it can be a hard problem
to address. 

The general approach is to load a save from the original, resave
it in GemRB and then try loading it again. If it works, great, if not, check
the difference between the two files. Reduce it step by step (manually or
through code changes) until the save works. `iediff` from
[iesh](https://github.com/gemrb/iesh) (or paired with `ielister`) can be
tremendously helpful in comparing the two binary files.

Another way is using a debugger, described with an actual example from #659:
1. You resave the game in GemRB, and load it with the original running in a
debugger like [x64dbg](https://x64dbg.com).
[Crash course tutorial](https://www.youtube.com/watch?v=75gBFiFtAb8) on what
this is about.
2. You hit the crash point and start to look around for anything familiar:
dictionary_githzerai_hjacknir is displayed somewhere around there, sounds
like PST stuff (Githzerai).
3. Load the GAM file into a raw editor like HxD. Cool, the string appears
-> looks like it's about variables, IESDP tells you more. Look at the
other one, no match. No wait, hjacknir is there but the whole thing has a
space in it's name.
4. You fix the GemRB save either manually or by a tool like NearInfinity.
5. You start the modified GAM file with PST: Cool, loading is proceeding
way more than before, so that's it for sure.
6. You browse the source code of GAMImporter for gut feelings, look for
the section of variable writing, find a suspicious function called
strnspccpy, look it up and see in the code: It really cuts away what the
Black Isle guys deliberately left in the code, by accident I assume.
7. If there are still crashes, go to 1.


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


## Exploring the games

As far as game resources go, the main complementary documentation is on the
[IESDP](https://gibberlings3.github.io/iesdp/) - The Infinity Engine Structures
Description Project. It represents the accumulated knowledge of IE internals and
in a sense, GemRB could be considered a reference implementation. Sometimes it is
also helpful to look at the sources of other tools like
[NearInfinity](https://github.com/NearInfinityBrowser/NearInfinity).

Our [iesh](https://github.com/gemrb/iesh) is not polished and in need of porting
to python3, but also exceptionally
useful when trying to figure out if anything uses fields or bits previously
thought unused or not working. Or if you need to do any processing. Basically
for anything that is much faster when automated, especially since most IE tools
have poor search capabilities. It can be used interactively, but also comes with
several scripted examples.

Direct reverse engineering is also possible and is the reason for much of the
understanding of the way the originals worked. There are several projects using
DLL injection to do minor fixes and extensions (ToBex, EEex, something for iwd2) —
they sometimes contain useful info.

While most games preserved a [debug console](Cheats.md) that can be helpful,
Planescape: Torment's was too buggy and was disabled for release. See the linked
page for a mod to remedy that.

## Maximizing performance

This is something particularly interesting to porters to platforms with
comparatively weak hardware. Some tricks to lower memory usage, I/O and/or
CPU use: change [the settings](Manpage.md) `Logging=0`, `AudioDriver=None`, 
`CapFPS=30`, `GCDebug=1536`. If OpenGL(ES) is available, building with that enabled
will of course help avoid software rendering.

### Investigating performance bottlenecks

Besides the usual tools GemRB supports using [tracy](https://github.com/wolfpld/tracy)
for low cost (appropriate for slow devices) profiling. A few annotations have been
added to critical or interesting sections already, but refer to the upstream docs for
details.


## Cocoa Application Wrapper

Apple platforms (Mac OS X & iOS) are built with a special wrapper. This
wrapper enables the application to interface with OS specific features
easily without having to alter the GemRB core. The meat of the wrapper
is simply an NSApplication Delegate object that can be dynamically
extended using categories loaded from the various GemRB plugins. The
application delegate has an Objective-C++ interface to the GemRB core so
it is possible to map system specific features to trigger action inside
the core or get core status.

Currently the wrapper doesn't do much, it does allow GemRB to be built as
a proper application bundle instead of a command line executable and it
overrides application quit (on Mac) to allow GemRB to handle a quit
event in its own way (currently GemRB simply quits, but it should have a
popup warning about losing progress etc).

The iOS version of the wrapper runs a configuration utility prior to
running gemrb ([Download sample
configuration](http://dl.dropbox.com/u/13866402/GemRB-ipad.cfg)). It
also attaches an accessory view to the keyboard for toggling modifier
keys.

Apple specific features that could be implemented with the wrapper:

  - Using NSUserDefaults to dynamically set engine options at runtime
  - GUI interface for editing the config (iOS prefpane or simple
    preference interface for Mac) 
  - a quick launch GUI to prompt for game type on launch.
  - setup special environments (ex. Python for iOS)


## Git Bisect
 
Git is a tool to track changes in files and especially useful for collaboration.
You have a file and someone changes a line; you can go back, a year later, and
check who added this line, and if they wrote why, mentioned test cases or any
other useful info.

It also enables bisection, a quick search to find with what change a problem
started occuring. Something was working 2 weeks ago, but isn't now? You feed git
this info, and it will automatically present you with the least amount of
necessary checks (changes to verify) to find the exact commit that broke it.
Check out [Tower's explanation](https://www.git-tower.com/learn/git/faq/git-bisect/)
for a visualization of the process.

### Bisecting
 
`git bisect` is the subcommand used to nail down the commit that broke the
thing you're testing. 

To start a bisection:
- `git bisect start` 
- Assuming the current revision has the problem, enter `git bisect bad`

Now we need to find a state when things were working fine. Since you probably
have to guess, let's try 50 changes before now with `git checkout HEAD~50`.
Rebuild as usual, eg. on linux:
```sh
cd build
make -j2
```
If it's bad, run git checkout again and repeat until you find a good version.
Once you have it: `git bisect good`.
 
Now the main cycle starts. Git will suggest a new commit to test, estimate
the number of steps and repeat the bisection until it finds the commit that
introduced the problem.
- Rebuild as usual
- It works? `git bisect good`
- It doesn't? `git bisect bad`
- You cannot test it because of some other error, for example it doesn't
build at all? `git bisect skip`

A couple of runs later, you will be presented with the "first bad commit",
which you should report (or use yourself).

To end the bisect, enter `git bisect reset`. This will bring you back to
where you were before in git history. 


## Using rr for hard to reproduce bugs
In case you want to use [rr](https://rr-project.org/) to get help tracking down a hard
to reproduce bug, make sure to build without OpenGL, since it doesn't support it.

## Using GemRB libraries in external projects
**Note: this is an experimental feature. No API or ABI compatibility guarantees exist.**

Here's a few examples with a BG2 install:
```cpp
#include <iostream>
#include <chrono>
#include <thread>
#include "Interface.h"
#include "PluginMgr.h"
#include "SaveGameMgr.h"
#include "Map.h"
#include "MapMgr.h"
#include "TileMap.h"
#include "Scriptable/InfoPoint.h"
//#include "Logging/Loggers/Stdio.h"

using namespace GemRB;
using namespace std::chrono_literals;

int main(int argc, char** argv) {
	// basic setup steps - a library caller would construct CoreSettings manually
	CoreSettings cfg = LoadFromArgs(argc, argv);
	// if you wanted to use our logging functionality
	//ToggleLogging(cfg.Logging);
	//AddLogWriter(createStdioLogWriter());
	Interface gemrb(std::move(cfg)); // same as core later

	// inspect an item
	const Item* itm = gamedata->GetItem("sw1h31");
	const ITMExtHeader* hdr = itm->GetExtHeader(0);
	String name = core->GetString(itm->ItemNameIdentified);
	//Log(DEBUG, "Testing", "Item's identified name is: {}", fmt::WideToChar{name});
	std::cout << "Item's identified name is: " << MBStringFromString(name) << std::endl;
	std::cout << "Item's first header's effect count is: " << hdr->features.size() << std::endl;

	// inspect an item's description image
	Holder<Sprite2D> im = gamedata->GetAnySprite(itm->DescriptionIcon, -1, 0);
	Region frame = im->Frame;
	std::cout << "Item's description image frame height is: " << frame.h << std::endl;

	// playing a sound
	auto audio = core->GetAudioDrv();
	auto handle = audio->Play("AMB_D21D", SFXChannel::GUI);
	while (handle && handle->Playing()) std::this_thread::sleep_for(25ms);

	// grab the text of the first infopoint on the map
	// we have to set up a game first
	auto gamStream = gamedata->GetResourceStream("baldur", IE_GAM_CLASS_ID);
	auto gamMgr = GetImporter<SaveGameMgr>(IE_GAM_CLASS_ID, gamStream);
	Game* game = gamMgr->LoadGame(new Game(), 0);
	core->SetGame(game);
	ResRef mapRef {"ar0020"};
	const Map* map = game->GetMap(mapRef, false); // if you want to inspect the live map
	// DataStream* ds = gamedata->GetResourceStream(mapRef, IE_ARE_CLASS_ID);
	// auto mM = GetImporter<MapMgr>(IE_ARE_CLASS_ID, ds);
	// Map* map = mM->GetMap(mapRef, true); // if you just want the base data
	const InfoPoint* ip = map->GetTileMap()->GetInfoPoint(2);
	std::cout << "Infopoint's click text is: " << int(ip->StrRef) << std::endl;

	// cleanup to prevent a delay and crash on exit
	delete game;
	core->SetGame(nullptr);
	VideoDriver.reset();
	return 0;
}
```

Let's say it's in a file called `libgemrb.test.cpp`. The way to build it is to start in the source repo:
```
cd build
g++ -I ../gemrb/includes/ -I ../gemrb/core/ -I . -L gemrb/core/ -L gemrb/plugins/ -DFMT_HEADER_ONLY -DFMT_EXCEPTIONS=0 \
  -Wl,-rpath,$PWD/gemrb/core -o libgemrb.test ../libgemrb.test.cpp gemrb/core/libgemrb_core.so
```

One would then run it with eg. `./libgemrb.test -c bg2.cfg`. The config has to be set up properly (you can play the game),
`UseAsLibrary=1` needs to be added to it and `GameType` has to be set manually, not left at `auto`.
