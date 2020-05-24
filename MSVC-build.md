---
title: Microsoft Visual Studio compilation guide
toc: true
---

## Install MSVC, windows runtime libraries and tools
The MSVC Community 2019 edition can be 
[downloaded for free](https://visualstudio.microsoft.com/vs/features/cplusplus/).

The Visual Studio installer presents you with a ton of options for various scenarios you
might use it for via the ‘Workloads’ landing page.This is fine for general deployment,
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

Then run the following commands. Hint: no need to type anything, copy and hit “shift+ins”.

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

## Clone the GemRB repository 
After solving the previous steps, open Visual Studio again, it should start automatically with several options, pick ‘Clone or check out code’ and point it to your fork or

https://github.com/gemrb/gemrb.git (see note: https://gemrb.github.io/Dev-docs.html#getting-the-code)

VS will gladly import GemRB as a CMake based project. The landing page will give you the option to open the built in CMake settings GUI if you wish to change any settings from the default.

 When you are happy with the configuration, go to Project->Generate cache for GemRB

Go to Build->Build all or hit F7 to try to build gemrb.

You will more than likely see some compiler warnings. In most cases they shouldn’t be anything to worry about. The regular tool for building GemRB is GCC, and MSVC has its own criteria of things to pick on.

If you get compiler errors on the other hand, in other words, you don’t get a working executable, then save the contents of the log and reach out for support


## Configure and run the game

Configure “GamePath=”  in GemRB.cfg to the directory containing your game files

Refer to this page for instructions setting up the game:

https://gemrb.github.io/Install.html#configure-gemrb
