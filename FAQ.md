---
title: Frequently asked questions
toc: true
---

## What is GemRB?

GemRB isn't a mod in the normal sense. GemRB is an open source
reimplementation of the Infinity Engine™ which powers the original games
and most of the existing mods and total conversions. This means we started
from scratch, zero, and programmed, cursed and reverse engineered our way
to [where GemRB is today](Features.md).

We are not affiliated in any way with BioWare, BlackIsle, Beamdog, or any
of the companies involved in the making of the original games. 
We are however affiliated with the wider modding community (and 
[Gibberlings3](https://gibberlings3.net) in particular).
Besides providing support and inspiration, many of you (us) have
contributed to [IESDP](https://gibberlings3.github.io/iesdp/) which
made GemRB possible. 

## X/Y/Z doesn't work or is buggy. Where to report it?

Click the Feedback link on the top of the page.

## Does GemRB work on platform X/Y/Z?

GemRB already supports a [wide array of software and hardware
platforms](Supported-platforms.md) and so it shouldn't be hard to extend to
new ones. Get in touch if you are interested, we are happy to help!

## Which engines are supported at a playable state?

What is "playable" is subjective, but check the details on the
[status page](Features.md).

## Which mods don't work with GemRB?

GemRB aims to support all mods that would work with one of
the original engines. It can also support many of the mods that require
EXE modification, but these mods may need to take some different steps,
usually just tweak one of the data files shipped with GemRB. It is
possible that some EXE modifications are not compatible with GemRB, but
we work on making these as few as possible. **Some of the EXE hacks are
obsoleted with this engine.**

See the [modding page](Modding.md) for some extra information.

## Can you play with more than 6 party members?

**Yes**\! You just have to install the [*10 player parties* (10pp)
mod](https://github.com/lynxlynxlynx/gemrb-mods/tree/master/10pp).

## Will GemRB support new feature X/Y/Z?

Perhaps. It is all about the limited resources we have, so any
[help](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md) is
welcome. The first goal is to make the original games normally playable.
Larger extensions will have to wait or be done by you. You can request
new features [here](https://github.com/gemrb/gemrb/issues/new/choose).

## Can you use GemRB without any of the original games?

Sure. Firstly, a minimal dataset needed to run gemrb is included. It
just makes sure the engine works, so not that fun.

Secondly, a minimal demo is included, which sets up an area and your actor.

Thirdly, you could use the
[bg2 demo](http://www.fileplanet.com/164134/160000/fileinfo/Baldur%27s-Gate-II-Demo-%5BFull-Install%5D)
to get a better feel of what the games or GemRB are about.

## Is it possible to create a new game with GemRB?

Of course, but don't underestimate the effort involved. A basic demo is
bundled with GemRB, but you can only awkwardly walk around there.

For more details and discussions, see [newgame](New-game.md) and the linked
forum threads.
