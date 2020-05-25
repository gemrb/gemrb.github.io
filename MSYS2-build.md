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

Important: If you want to run GemRB from outside the MSYS2 shell, don't skip the last
[section](#). It will guide you through the needed steps.


## Install build tools

If you closed it, open up the MSYS2 shell again.

This command will install the required collection of tools for compilation. Tip: you
can copy it to the clipboard and press *Shift+Insert* to run it in the terminal.

```
pacman -S mingw-w64-x86_64-gcc mingw-w64-x86_64-gdb mingw-w64-x86_64-cmake mingw-w64-x86_64-extra-cmake-modules git
make
```






The MSVC Community 2019 edition can be 
[downloaded for free](https://visualstudio.microsoft.com/vs/features/cplusplus/).

The Visual Studio installer presents you with a ton of options for various scenarios you
might use it for via the "Workloads" landing page. This is fine for general deployment,
but the full install weighs around 7 GB, so you may want to choose individual components
to minimise your download time.

When installing include also these individual options:
 * **C++**, version does not matter
 * **Python 2**, pick the 64-bit version
 * **Git**, the github support feature is optional
 * **CMake**
 * **Windows (10) SDK**, any version should do — if not, let us know


## Install dependencies — external SDKs
After you have installed Visual Studio, you will need to install the libraries that
GemRB depends upon to work.

The required external libraries are **SDL** and **Zlib**. You will want audio too,
so grab OpenAL and the other optional dependencies.
 
To download them, we use VCPKG, a package manager that is specifically made to support
building these libraries (among others) under Windows. 

Open a powershell terminal from within Visual Studio:
`Tools > Command line- > Developer powershell`

Then run the following commands. Hint: no need to type anything, copy and hit
"shift+ins".

Download and configure VCPKG with:
```
git clone https://github.com/Microsoft/vcpkg
cd vcpkg
.\bootstrap-vcpkg.bat
```

Then install the all the dependencies:
```
.\vcpkg install sdl2:x64-windows zlib:x64-windows
.\vcpkg install openal-soft:x64-windows sdl2-mixer:x64-windows libpng:x64-windows
.\vcpkg install libogg:x64-windows libvorbis:x64-windows freetype:x64-windows libiconv:x64-windows
```

And finally tell Visual Studio where to find the new files:
```
.\vcpkg integrate install
```

## Get GemRB sources and build them
Open Visual Studio again, pick `Clone or check out code` and point it to your **fork**
or the main repository ([see note](https://gemrb.github.io/Dev-docs.html#getting-the-code)):

    https://github.com/gemrb/gemrb.git 

Visual Studio will gladly import GemRB as a CMake based project. The landing page
will give you the option to open the built-in CMake settings GUI if you wish to
change any default settings.

When you are happy with the configuration, go to `Project->Generate cache for GemRB`.

To build GemRB go to `Build->Build all` or hit `F7`.

If you get any compiler errors instead of a working executable, then save the
contents of the build log and open an issue on the tracker.


## Configure and run the game

Follow the common [instructions](https://gemrb.github.io/Install.html#configure-gemrb).

If you want to run GemRB from within Visual Studio with several config files
to be able to test several games at once, add new launcher configurations that
specify a path to those config files, so the final invocation is eg. 
`gemrb.exe -c torment.cfg` or `gemrb.exe -c myiwd2.cfg`.
