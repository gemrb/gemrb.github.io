---
title: Microsoft Visual Studio compilation guide
toc: true
---

## Install MSVC, windows runtime libraries and tools
The MSVC Community 2019 edition can be 
[downloaded for free](https://visualstudio.microsoft.com/vs/features/cplusplus/).

The Visual Studio installer presents you with a ton of options for various scenarios you
might use it for via the "Workloads" landing page. This is fine for general deployment,
but the full install weighs around 7 GB, so you may want to choose individual components
to minimise your download time.

When installing include also these individual options:
 * **C++**, version does not matter
 * **Git**, the github support feature is optional
 * **CMake**
 * **Windows (10) SDK**, any version should do — if not, let us know

The installer does ship Python, but not its debug build, so it's better to use the one
provided by vcpkg. It will be installed in the following section.

## Dependencies — external SDKs
You will need several libraries that GemRB depends upon to work.

The required external libraries are **SDL** and **Zlib**. The other dependencies are optional,   
for example the audio library OpenAL.
 
To download them, we use [VCPKG](https://vcpkg.io/en/getting-started.html), a package manager that is specifically made to support building these libraries (among others) under Windows. 

Open a powershell terminal from within Visual Studio:
`Tools > Command line- > Developer powershell`

Then run the following commands. Hint: no need to type anything, copy and hit
*Shift+Insert*.

Download and configure VCPKG with:
```
git clone https://github.com/Microsoft/vcpkg
cd vcpkg
.\bootstrap-vcpkg.bat
```

GemRB provides a [manifest file](https://vcpkg.io/en/docs/maintainers/manifest-files.html) for VCPKG dependencies. During the GemRB build, VCPKG will automatically download and install all the dependencies specified in the manifest. The file is located in [/platforms/windows/vpkg.json](https://github.com/gemrb/gemrb/blob/master/platforms/windows/vcpkg.json).


## Get GemRB sources and build them
Open Visual Studio again, pick `Clone or check out code` and point it to your **fork**
or the main repository ([see note](https://gemrb.github.io/Dev-docs.html#getting-the-code)):

    https://github.com/gemrb/gemrb.git 

Visual Studio will gladly import GemRB as a CMake based project. The landing page
will give you the option to open the built-in CMake settings GUI if you wish to
change any default settings.

You should configure a couple of things: 
* CMake toolchain file (-DCMAKE_TOOLCHAIN_FILE=) - the CMake script for configuring VCPKG. Should be `vcpkg/scripts/buildsystems/vcpkg.cmake`
* The install prefix (-DCMAKE_INSTALL_PREFIX=) - installation destination folder.

Example:
![image](https://user-images.githubusercontent.com/11220053/181171063-58d0c16b-9380-44f0-a712-8485149ae727.png)


When you are happy with the configuration, go to `Project->Generate cache for GemRB`.

To build GemRB go to `Build->Build all` or hit `F7`.

If you get any compiler errors instead of a working executable, then save the
contents of the build log and open an issue on the tracker.


## Configure and run the game

Follow the common [instructions](https://gemrb.github.io/Install.html#configure-gemrb).

If you want to run GemRB from within Visual Studio with several config files
to be able to test several games at once, add new [launcher configurations](https://docs.microsoft.com/en-us/cpp/build/configure-cmake-debugging-sessions?view=msvc-170) that
specify a path to those config files, so the final invocation is eg. 
`gemrb.exe -c torment.cfg` or `gemrb.exe -c myiwd2.cfg`.
