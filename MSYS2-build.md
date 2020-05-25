---
title: MSYS2 (MinGW) compilation guide
toc: true
---

** WIP, placeholder copy of MSVC instructions **

## Install MSYS2 and update the package databases

MSYS2 provides a simple command line solution that can be used to set up all the required
tools and libraries to build and run GemRB from source.
[**Download and install it**](https://www.msys2.org/). More detailed instructions are
available [here](https://www.msys2.org/wiki/MSYS2-installation/).

It uses pacman, which is the package management tool used by Arch Linux. It will require
approximately 2.5GB of space to install everything, but the download size is actually
much smaller.

*Important*: If you want to run GemRB from outside the MSYS2 shell, don't skip the last
[section](#). It will guide you through the needed steps.


## Install build tools

If you closed it, open up the MSYS2 shell again.

This command will install the required collection of tools for compilation. *Tip*: you
can copy it to the clipboard and press *Shift+Insert* to run it in the terminal.

```
pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-gdb mingw-w64-x86_64-cmake mingw-w64-x86_64-extra-cmake-modules git
make
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

We also use libvlc, but it was untested whether mingw-w64-x86_64-vlc provides it.


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

If you want to run GemRB from within Visual Studio with several config files
to be able to test several games at once, add new launcher configurations that
specify a path to those config files, so the final invocation is eg. 
`gemrb.exe -c torment.cfg` or `gemrb.exe -c myiwd2.cfg`.
