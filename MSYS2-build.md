---
title: MSYS2 (MinGW) compilation guide
toc: true
---

## Install MSYS2

MSYS2 provides a simple command line solution that can be used to set up all the required
tools and libraries to build and run GemRB from source.
[**Download and install it**](https://www.msys2.org/). More detailed instructions are
available [here](https://www.msys2.org/wiki/MSYS2-installation/).

It uses pacman, which is the package management tool used by Arch Linux. It will require
approximately 2.5GB of space to install everything, but the download size is actually
much smaller.


## Install build tools

If you closed it, open up the MSYS2 shell again.

This command will install the required collection of tools for compilation. *Tip*: you
can copy it to the clipboard and press *Shift+Insert* to run it in the terminal.

```
pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-cmake mingw-w64-x86_64-extra-cmake-modules git make
```


## Install dependencies

All the dependencies GemRB requires can also be installed from within MSYS2. 

First the required dependencies:
```
pacman -S mingw-w64-x86_64-python2 mingw-w64-x86_64-SDL2
```
Zlib has already been installed during the initial MSYS2 setup.

*Note*: If you have python 2.7 installed on your system already, CMake should find it
and you don't need to install it here.

Then come the optional dependencies:
```
pacman -S mingw-w64-x86_64-openal mingw-w64-x86_64-SDL2_mixer mingw-w64-x86_64-libogg mingw-w64-x86_64-libvorbis
pacman -S mingw-w64-x86_64-libpng mingw-w64-x86_64-freetype
```
Iconv should already be present just like Zlib. 

We also use libvlc for videos in mac versions of a game, but that's both very
rare and requires further tweeking to get `mingw-w64-x86_64-vlc` (a 2GB install)
recognized.


## Get GemRB sources and build them

Grab your **fork's** Git URL or use the main repository one as in this example
([see note](https://gemrb.github.io/Dev-docs.html#getting-the-code)). The
following commands will do everything else:

```
git clone https://github.com/gemrb/gemrb.git gemrb
mkdir gemrb/build
# start building
cd gemrb/build
cmake -G "MSYS Makefiles" -DCMAKE_BUILD_TYPE=Debug ..
make
```


## Configure and run the game

Follow the common [instructions](https://gemrb.github.io/Install.html#configure-gemrb).

Then change to the gemrb directory inside the build directory and run GemRB:
```
cd gemrb
./gemrb.exe
```

It is possible to use multiple game configuration files to support running different
games at the same time. For example, make a copy of `GemRB.cfg` to `Torment.cfg`
and run the game with the command`./gemrb.exe -c Torment.cfg`.

You can try making a symbolic link to the exe as well. The name of the file is also
the name of the configuration file that will be sought. Eg. `./myiwd2.exe` will
search for `./myiwd2.cfg`.


## Configure Windows search paths

On Windows 10, you can simply type `env` in the start menu search box to get to
the relevant control panel to do this. On other versions you can usually get to
system properties by right clicking `My Computer`.

### Running from outside the shell

If you want to be able run the game from outside of the MSYS2 terminal, you will
need to add the MinGW dll file location to the Windows `PATH` environment variable
or it will not be able to find them. 

The MSYS2 installer avoids doing this by default to avoid causing potential
conflicts on a user's system, but unless you already have another MinGW or Cygwin
setup installed, it should not cause any issues, and is easily reversible if it
does.

Add `C:\msys64\mingw64\bin` if you installed it in the default location, while
the following screenshot used a different path:
![setting PATH](/assets/img/win-envvars.jpg)

At this stage, you should be able to run the game from Windows Explorer
by just clicking on `gemrb.exe`.

### Setting the python path

If you are going to use the python package that comes with MSYS2, you will also
need to set the `PYTHONPATH` variable to `C:\msys64\mingw64\lib\python2.7`.
Adapt the path if you installed MSYS2 somewhere else.

