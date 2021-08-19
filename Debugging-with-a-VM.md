---
title: Debugging with a virtual machine and Linux
toc: true
---

Sometimes a problem can be reproduced only on a user's machine. Since most GemRB developers are not
using Windows, it's hard to provide good instructions to try to find out what's at fault. One option
presents itself as solving several obstacles — building GemRB manually on a Linux virtual machine.
That way the environment is predictable, known and all the usual developer tools and tricks are
available.

This page is a guide on how to set everything up. By the end of it you will be running Linux on your
Windows system without one affecting the other.

## What is a virtual machine?
 
A virtual machine (VM) allows you to run one operating system inside a sandbox in another system. A
machine inside another. A *host* is your operating system (probably Windows), a *guest* is the
system that is running inside the virtual machine.

The virtual machine in this guide is [VirtualBox](https://www.virtualbox.org/), a free software
project as well. In the last two sections, you can find brief instructions also for
[VMWare](#vmware)
and [WSL2](#wsl2).

It's easy to set up, but it doesn't work if you have
turned on Hyper-V on your Windows machine. If you don't know what that is - good, then it's most
likely not on. 
 
Performance when running in a VM will be worse than on your real operating system, but it largely
depends on how good your hardware is and what you are doing.
 
 
## A few general Linux notes
 
If you picked either Kubuntu (KDE) or Xubuntu (XFCE) your virtual machine will be slightly similar to windows. You'll have a start menu where you can find all your programs, default programs like Mozilla Firefox, a text editor, a file browser etc. Some things are quite different, though: 
 
- Linux is case sensitive. GemRB, gemrb and Gemrb would all be different files. 
- Linux uses forward slash instead of backwards slash for file paths. 
- Linux doesn't have drive letters. There is no C:\ etc. Drives and devices can be mounted anywhere, but are often under /mnt or /media. 
- Your main directory for user files is "home" which is found under /home/YourUserName. 
- `Sudo` is used to run something with basically admin privileges. While it's needed to install things (that's why we'll be using that), you should not use it for random commands, and also not just blindly copy stuff from the internet without knowing what it does (Oh, the irony). 
- You can open the manual for most commands with `man command`, for example, if you don't trust the usermod command, enter `man usermod` and you can read up exactly what this command does. 
- To navigate in the terminal, the main command is `cd` to `c`hange `d`irectory. `cd ..` moves one level up. `cd ~` will bring you back to your home directory. Also, if you have file paths with spaces or apostrophes in them, to use them in the terminal you'll need to *escape* them like so `~/Baldur\'s\ Gate\ 2`
- Careful: If you want to run something in your current directory, you need to use `./stuff`. With dot and slash. Just `stuff` would search for it in your installed apps and libraries, while `/stuff` would search for it in root. 
- By default, files are not executable. If you write a script, you need to allow the system to execute it. You can do that in (probably) every graphical file manager by right clicking on the file and finding the option for it under *Permissions*. Alternatively, you could enter `chmod +x FILENAME` in your terminal. 
- You can copy from and paste into the terminal, but (usually) not with Ctrl-C and Ctrl-V. Ctrl-C *terminates* the current proces. Instead, use `Ctrl-Shift-C` and `Ctrl-Shift-V`. 
- You create a directory with `mkdir`, a file with `touch`, copy a file with `cp` and move a file with `mv`. 
- For most software, you don't download files from the internet in Linux, but use your package manager. On Ubuntu like Systems that is apt, which will be used in these instructions. Different Linux distros use different package managers.
 
 
## Setting up a Linux VM
 
- First download VirtualBox from [this](https://www.virtualbox.org/wiki/Downloads) page, select the one for Windows hosts. 
- Install Virtual Box, reboot if prompted.
- Download a Linux distro of your choice. If you have no preference, something Ubuntu based is a good idea. I'd suggest [Kubuntu](https://kubuntu.org/) or [Xubuntu](https://xubuntu.org/), as their look is slightly similar to Windows - you have a start menu and a familiar task bar. Download the iso file. LTS (Long Term Support) releases have support for multiple years, so those are preferable if you don't want to mess with it; doesn't matter too much for a VM that probably won't even last that long. 
- Create a new virtual machine. 
  - Give it a name
  - Select Type Linux and Version Ubuntu (64 bit)
  - Allocate it a good bit of RAM (depending on the RAM your system has, it probably shouldn't be more than half of that, but if you can spare it, 4-8 GB is good)
  - Keep the settings for virtual hard disks at default, but change the size. If you just want to debug one or two unmodded games, 25GB should be enough. If you plan to install any huge mods or debug more games, you'll probably want to give that virtual drive 100GB+.
  - Once the setup wizard has finished, open settings again and go to the Display tab. Max out the Video Memory slider to 128MB. 
- Now it's time to start the virtual machine. It will ask you for a file, select the iso you just downloaded. It will take a moment, then the installer will start. Select "install" instead of "try", enter your preferred settings for keyboard, names and passwords and when asked, select "erase disk". Don't worry, this is just your virtual (25GB or more) disk. 
- After it's done installing, it will ask you to reboot. Do so, then when it asks you to remove the installation medium, go to Devices > Optical Drives > Remove disk from virtual drive. Your virtual machine will now reboot. 
- If you have picked an ubuntu-based guest system, open a terminal and enter `sudo apt install virtualbox-guest-additions-iso`. This will install dependencies needed for guest additions to work, if any are missing. 
- When it's done, in the VirtualBox menu, select Devices > Insert Guest Additions CD Image.
- If it didn't autorun/open, find the disc directory it in your file manager.
  - If you are lucky, double clicking autorun.sh will ask you if you want to run it and ask for your password (Most likely on Kubuntu).
  - If you are a bit less lucky, double clicking it will just open it as a text file, you need to right click somewhere in that folder and open a terminal and enter `sudo ./autorun.sh` (Most likely on Xubuntu) 
- Guest additions allows you to
  - Share your clipboard with the guest (enable under Devices > Shared Clipboard)
  - Share a folder on your host's drive with the guest
  - Arbitrary window resizing for the guest
- Enter `sudo usermod -a -G vboxsf $USER`, this will add your current user to the vboxsf group, allowing you to access the shared folder in the next step. 
- Turn off the virtual machine. 
- To add a shared folder, we open the VM's settings again. Shared Folders > Click the green plus icon > Select a folder you want to share, click auto-mount. Everything you place in this folder can be seen and used by both, the host and the guest. 
  - For easier access, you can set a mount point. A good one would be in your home directory, for example /home/YOURUSERNAME/VirtualBox
  - You should only use this to give the VM access to a single, isolated, shared folder. **Don't** give it access to C:\ or all your Documents and games or something like that. You can edit *and break* things inside the shared folder from inside your VM. 
- Boot into your VM. The folder should appear now. You can put your game installation in there, access it from your VM and move it into your VM. Since Windows uses a different file system than Linux, I would *not* recommend running the game from the shared folder. 
 
 
## Installing GemRB and the debugger
 
- Open a terminal. 
- Install the dependencies needed to build GemRB. `sudo apt install git cmake make clang libsdl2-2.0-0 libsdl2-dev libopenal1 libopenal-dev python-is-python2 libpython2.7-dev gdb python-is-python3 libpython3.8-dev`
- Clone the GemRB repository `git clone https://github.com/gemrb/gemrb`
  - This will create a gemrb folder right in your home directory. 
- Enter it with `cd gemrb`
- You need to create a directory called "build" inside it. You can do that in the terminal `mkdir build` or in your file manager as you would on Windows. 
- Enter in the terminal `cd build` to go into that directory. 
- To build GemRB (we do a debug build), you enter those commands into the terminal: `cmake -DCMAKE_BUILD_TYPE=Debug ..; make -j3`
- To run with the debugger, you need a cfg file in the build directory. Copy the example file "GemRB.cfg.noinstall.sample" from gemrb/gemrb into the build directory as "GemRB.cfg". You can do that in the terminal, too with `cp ../gemrb/GemRB.cfg.noinstall.sample GemRB.cfg`
- Edit at least the following things in this file. If any of those lines have a # in front in the cfg file, remove the #: 
  - GameType=auto
  - CaseSensitive=1
  - GamePath=/path/to/your/Game
  - You might have to set the paths for CD1-CD6 as well, for example for the GOG version of Baldur's Gate 2 all those would be set to /path/to/your/Game/data
  - You can change other things like the resolution or skipping intro videos as well, if you want to. 
  - The name doesn't actually have to be GemRB.cfg, it can be anything, especially if you want to test different games and each one needs its own config. You'll just have to adjust the run command accordingly below.
- To run the game with the debugger, enter from inside the build directory `../admin/run.gdb GemRB.cfg`
- While the game is running, you'll have the terminal in the background. If the game crashes at any point, switch to the terminal, you'll see some message that the game crashed. Enter `bt` to get a backtrace. You can copy that out of the terminal with `Ctrl-Shift-C`. There are other commands that the devs might ask you to enter into that window, that can give them more information.
- When you are ready to terminate the crashed game, enter `q` in the debugger window and confirm that you want to close the process, or `r` to restart it. 
- I found it useful to put all the build commands into a short script, so I wouldn't have to type them again. Here is my example script to pull the latest version from git, delete all the build files and build it from scratch. I saved it into the gemrb/build directory as update.sh (make it executable) and run it from inside the build directory with `./update.sh`. 
```
#!/bin/bash
rm -r CMake*
git pull
cmake -DCMAKE_BUILD_TYPE=Debug ..
make clean && make -j3
```
 
## About Git & Git Bisect
 
Git is a tool to track changes in files and especially useful for collaboration. You have a file and someone changes a line; you can go back, a year later, and check who added this line, and if they wrote why it was changed. You'll be using git mainly for two things:
 
- To update your local code to the last version from github
- To possibly revert to any older version and check when something broke
 
### Updating
 
- Go anywhere in your gemrb directory. Enter `git pull` into the terminal. 
- The first time you do this, git will complain about something that probably doesn't concern you if you don't do any changes yourself. You can still enter `git config pull.rebase false` and it will shut up.
- After pulling the latest version, you need to build it again (run the cmake and make commands from above again). 
 
### Bisecting
 
Git bisect is used to nail down the commit that broke a certain thing. Something was working 2 weeks ago, but isn't now? You feed git this info, and it will automatically present you with the least amount of necessary checks to find the exact commit that broke it. 
 Git bisect commands only work on the top directory of the repository (= the main gemrb folder). To start one: 
- In the gemrb top directory, enter `git bisect start` to start a new bisect. 
- Assuming the latest revision has the problem, enter `git bisect bad`
- Find the commit (that big line of numbers and letters) that still worked. Enter `git bisect good COMMITNUMBERHERE`. Release points like `v0.9.0` work, too.
- Git will then find one commit in the middle and check it out. You then have to build it and run it and see if it works. 
  - `cd build`
  - Build it, start the game, test it, close it
  - You can use the example script I posted further up, just remove the `git pull` line
- `cd ..` to get back to the top level
  - It works? `git bisect good`
  - It doesn't? `git bisect bad`
  - You cannot test it because of some other error, for example it doesn't build at all? `git bisect skip`
- A couple of runs later, you will be presented with the "first bad commit", i.e. the first commit that broke a certain thing. 
- To end the bisect, enter `git bisect reset`. This will bring you back to where you were before. 

## Alternatives for advanced users

### VMWare
[VMWare](https://www.vmware.com/products/workstation-player.html) is another popular virtual machine project.
It is a little more complicated to set up, but still follows the same basic process. You will just need to
follow the documentation that comes with VMWare a lot more closely to get it going.

You are going to want Workstation Player, the free version of VMWare. You will also need VMWare Tools for
passthrough. Scroll down the list here: https://my.vmware.com/en/web/vmware/downloads/#all_products

There is a lot more to tweak and a lot more instructions to set VMWare up, but it is well documented.    
Tips: 
- Make sure to set your VM space as big as you will need during the initial setup because you will break
all of your fake partitions if you try to expand it after the VM is set up.
- Copy from inside the VM terminal and not from the host. Your hard drive will be at
`/mnt/”letter”/` and copying from inside is much faster than copying from without.
- Remember to install your VMTools plugin. It will have its own setup process that will not be as easy to set
up and it will need to be set up from within the Workstation Player.

### WSL2

The third option is interesting for Windows 10 users and has built-in GUI support. It's a small linux
system embedded within Windows. Setting this up can still be tricky because it will require changing BIOS
settings. Most modern chipset have Virtualization technology built in, but do not have it enabled.

Restart Windows and hammer the F10 (or F2, or whatever key opens your BIOS). key while your PC posts.
You may need to turn off fast boot in Windows to get into your BIOS.
  1. Go to Control Panel.
  2. Select "Power Options".
  3. Click "Choose what the power buttons do".
  4. Click "Change settings that are currently unavailable". (Yes, that’s a real setting.)![image](https://user-images.githubusercontent.com/121515/130135435-7b2d384d-aaa7-4332-abe6-c0a8942382ce.png)
  5. Uncheck "Turn On Fast Startup" and click Save.

Navigating your BIOS can be tricky, so caution is advised. You will need to search through your BIOS
options for something about Virtualization or VT. On some systems it's under "Security". Enable it,
save changes and reboot.

You will need to head back into the Control Panel after your system reboots.

  1. Select "Programs and Features".
  2. Select "Turn Windows features on or off".
![image](https://user-images.githubusercontent.com/121515/130136030-1b057e9a-f0e0-4514-a237-e6107931890b.png)
  3. Make sure Hyper-V is unchecked. This will only allow you to install Windows-based virtual machines
and will block WSL. (Also, if you find Virtual Box or VMWare unable to create an Ubuntu VM for no
particular error code, this is probably why.)
![image](https://user-images.githubusercontent.com/121515/130136063-afbb25e2-1f29-48ac-bac2-2e8350f0a867.png)
  4. Scroll down and check the boxes for "Virtual Machine Platform", "Windows Hypervisor Platform", and
"Windows Powershell" and click OK.
![image](https://user-images.githubusercontent.com/121515/130136083-a35aa294-f59d-438e-acf5-08e4bdd7f716.png)
  5. Now open Windows Powershell elevated. 
Type: `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all`
  7. This will take a moment. When it is through, you will be prompted to reboot. Do so.
  8. Go back into an elevated Windows Powershell. Type: `wsl --set-default-version 2`
  9. The upgrade should happen quickly. Now, this will make our Linux friends really grind their teeth,
but open the Microsoft Store. Search for "Ubuntu" and click "Install" when it comes up.

The installation will only take a few minutes, but you will have an Ubuntu Start Menu icon.
Click it and VOY-LAH! Up pops an Ubuntu terminal natively in Windows that will run GUI software,
including GemRB. You will be able to find your drives under `/media/`.
