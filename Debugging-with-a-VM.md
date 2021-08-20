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
[VMWare](#vmware) and [WSL2](#wsl2).

It's easy to set up, but it doesn't work if you have
turned on Hyper-V on your Windows machine. If you don't know what that is — good, then it's most
likely not on.
  

## A few general Linux notes
 
If you picked either Kubuntu (KDE) or Xubuntu (XFCE) your virtual machine will be slightly similar
to windows. You'll have a start menu where you can find all your programs, default programs like
Mozilla Firefox, a text editor, a file browser etc. Some things are quite different, though: 
 
- Linux is case sensitive. `GemRB`, `gemrb` and `Gemrb` would all be different files. 
- Linux uses forward slash instead of backwards slash for file paths. 
- Linux doesn't have drive letters (no `C:\`). Drives are available under `/media`. 
- Your main directory for user files is "home" which is found under `/home/YourUserName` or `~` fo short. 
- `sudo` is used to run something with admin privileges. It's needed to install things system-wide.
- To navigate in the terminal, the main command is `cd` to `c`hange `d`irectory. `cd ..` moves
one level up. `cd ~` will bring you back to your home directory. Also, if you have file paths
with spaces or apostrophes in them, to use them in the terminal you'll need to *escape* them like
so `~/Baldur's\ Gate\ 2` or `"~/Baldur's Gate 2"`.
- You can copy from and paste into the terminal, but (usually) not with Ctrl-C and Ctrl-V. Ctrl-C
*terminates* the current proces. Instead, use `Ctrl-Shift-C` and `Ctrl-Shift-V`.
- To install software, you don't download files manually, but let the package manager do that for
you (`apt` on Ubuntu).


## Setting up a Linux VM with VirtualBox
 
- First download VirtualBox from [this](https://www.virtualbox.org/wiki/Downloads) page, **select
the one for Windows hosts**. 
- Install Virtual Box, reboot if prompted.
- Download a Linux distribution, which is an assortment of packages that makes a full system. We
suggest [Kubuntu](https://kubuntu.org/) as it looks slightly similar to Windows — you have a start
menu and a familiar task bar. Download the latest LTS (Long Term Support) release ISO file. 
- Create a new virtual machine. 
  - Give it a name
  - Select Type Linux and Version Ubuntu (64 bit)
  - Allocate it a good bit of memory, RAM (depending on the RAM your system has, it shouldn't be
more than half of that, 4-8 GB is enough)
  - Keep the settings for virtual hard disks at default, but change the size. If you just want to
debug one or two unmodded games, 25GB should be enough. If you plan to install any huge mods or
debug more games, you'll probably want to give that virtual drive 100GB+.
  - Once the setup wizard has finished, open settings again and go to the Display tab. Max out
the Video Memory slider to 128MB. 
- Now it's time to start the virtual machine. It will ask you for a file, select the ISO you
just downloaded. It will take a moment, then the installer will start. Select "install" instead
of "try", enter your preferred settings for keyboard, names and passwords and when asked, select
"erase disk". Don't worry, this is just your virtual disk, no the real one. 
- After it's done installing, it will ask you to reboot. Agree, then when it asks you to remove
the installation medium, go to Devices > Optical Drives > Remove disk from virtual drive. Your
virtual machine will now reboot.

### Making your existing files visible to the virtual machine

- Open a terminal ("Konsole") and install dependencies for guest additions:
```
sudo apt install virtualbox-guest-additions-iso
```
- When it's done, in the VirtualBox menu, select Devices > Insert Guest Additions CD Image.
- If it didn't autorun/open, find the disc directory in your file manager.
  - If you are lucky, double clicking autorun.sh will ask you if you want to run it and ask for
your password.
  - If opens it as a text file instead, you need to right click somewhere in that folder and
open a terminal (Actions > Open Terminal Here) and enter `sudo ./autorun.sh`
- Guest additions allows you to:
  - Share your clipboard with the guest (enable under Devices > Shared Clipboard)
  - Share a folder on your host's drive with the guest
  - Arbitrary resize windows for the guest
- Enter `sudo usermod -a -G vboxsf $USER`, this will add your current user to the vboxsf group,
allowing you to access the shared folder in the next step. 
- Turn off the virtual machine. 
- To add a shared folder, we open the VM's settings again. Shared Folders > Click the green plus
icon > Select a folder you want to share, click auto-mount. Everything you place in this folder can
be seen and used by both, the host and the guest. 
  - For easier access, you can set a mount point. A good one would be in your home directory, for
example ~/VirtualBox
  - You should only use this to give the VM access to a single, isolated, shared folder. **Don't**
give it access to `C:\` or all your Documents and games or anything like that. You can edit
*and break* things inside the shared folder from inside your VM.
- Boot into your VM. The folder should appear now. You can put your game installation in there,
access it from your VM and move it into your VM.
 
 
## Installing GemRB and the debugger
 
- Open a terminal ("Konsole").
- Install the dependencies needed to build GemRB. 
```
sudo apt install git cmake make clang libsdl2-2.0-0 \
  libsdl2-dev libopenal1 libopenal-dev libpython3-dev gdb
```
- Grab the GemRB code and prepare directories for building (a `gemrb` folder will appear in your home):
```bash
git clone https://github.com/gemrb/gemrb ~/gemrb
cd gemrb
mkdir build
cd build
```
- Build GemRB
```sh
cmake -DCMAKE_BUILD_TYPE=Debug ..
make -j2
```
- Copy the example settings file into "GemRB.cfg" and automatically fix some settings:
```sh
cp ../gemrb/GemRB.cfg.noinstall.sample GemRB.cfg
sed -i 's,GameType=test,GameType=auto,' GemRB.cfg
sed -i 's,^#CaseSensitive,CaseSensitive,' GemRB.cfg
```
- Open the file by clicking on it in Dolphin, the file manager. Find and set
`GamePath` to point to where you copied or mounted the game data (eg. `~/bg2`)
  - Check [the docs](Manpage.md) if you're curious about other settings

## Running GemRB in the debugger

- Open a terminal
- If you're not already in the build dir: `cd ~/gemrb/build`
- Run it with 
```
../admin/run.gdb GemRB.cfg
```
- While the game is running, you'll have the terminal in the background. If
the game crashes at any point, switch to the terminal and you'll see some message that
the game crashed. Enter `bt` to get a backtrace. You can copy that out of the terminal
with `Ctrl-Shift-C`. There are other commands that the devs might ask you to enter into that
window, that can give them more information.
- When you are ready to terminate the crashed game, enter `q` in the debugger window and
confirm that you want to close the process, or `r` to restart the engine.

## Updating to the latest code

The developers might ask you to test a fix, so you'll need to get the latest code. This
doesn't mean you have to go through the whole process again though! As usual open a
terminal and run:
```sh
cd ~/gemrb/build
git pull
make -j2
```
You can ignore warnings from git.

## Git Bisect
 
Git is a tool to track changes in files and especially useful for collaboration. You have a
file and someone changes a line; you can go back, a year later, and check who added this line,
and if they wrote why, mentioned test cases or any other useful info.

So when something breaks and you don't want to wait for it to get fixed, it's easy to switch
to a known working version.

It also enables bisection, a quick search to find with what change a problem started occuring.
Something was working 2 weeks ago, but isn't now? You feed git this info, and it will
automatically present you with the least amount of necessary checks (changes to verify) to find
the exact commit that broke it. 

### Bisecting
 
`git bisect` is used to nail down the change (commit) that broke the thing you're testing. 
These commands only work on the top directory of the repository (`~/gemrb`).

To start a bisection:
- `git bisect start` 
- Assuming the latest revision has the problem, enter `git bisect bad`

Now we need to find a state when things were working fine. Since you probably
have to guess, let's try 50 changes before now: `git checkout HEAD~50`. Rebuild as usual:
```sh
cd build
make -j2
```
If it's bad, run git checkout again and repeat until you find a good version. Once you
have it: `git bisect good`.
 
Now the main cycle starts. Git will suggest a new commit to test and repeat until it finds the
point in time, the change of code, the commit that introduced the problem.
- Rebuild as above
- It works? `git bisect good`
- It doesn't? `git bisect bad`
- You cannot test it because of some other error, for example it doesn't build at all? `git bisect skip`

A couple of runs later, you will be presented with the "first bad commit", which you should report. 

To end the bisect, enter `git bisect reset`. This will bring you back to where you were before. 

## Virtual Box alternatives for advanced users10401040

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
- Copy from inside the VM terminal and not from the host. Your hard drive will be inside
`/mnt/` and copying from inside is much faster than copying from without.
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
  4. Click "Change settings that are currently unavailable". (Yes, that’s a real setting.)
![image](https://user-images.githubusercontent.com/121515/130135435-7b2d384d-aaa7-4332-abe6-c0a8942382ce.png)
  6. Uncheck "Turn On Fast Startup" and click Save.

Navigating your BIOS can be tricky, so caution is advised. You will need to search through your BIOS
options for something about Virtualization or VT. On some systems it's under "Security". Enable it,
save changes and reboot.

You will need to head back into the Control Panel after your system reboots.

  1. Select "Programs and Features".
  2. Select "Turn Windows features on or off".
![image](https://user-images.githubusercontent.com/121515/130136030-1b057e9a-f0e0-4514-a237-e6107931890b.png)
  3. Make sure Hyper-V is unchecked. This will only allow you to install Windows-based virtual machines
and will block WSL. (Same reason for your Virtual Box or VMWare not being unable to create an Ubuntu VM with no
particular error.)
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
