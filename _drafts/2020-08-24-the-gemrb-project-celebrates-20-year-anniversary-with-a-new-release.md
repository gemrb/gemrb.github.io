---
title: The GemRB project celebrates 20 year anniversary with a new release
author: Jaka Kranjc
gallery:
  - url: assets/img/screenshots/iwd2-kuldahar-gem.jpg
    image_path: assets/img/screenshots/thumb/iwd2-kuldahar-gem.jpg
    alt: "IWD2 GemRB battle screenshot"
    title: "IWD2 remains to be fully understood"
  - url: assets/img/screenshots/10pp6.jpg
    image_path: assets/img/screenshots/thumb/10pp6.jpg
    alt: "10pp6.jpg"
    title: "10pp6.jpg"
  - url: assets/img/screenshots/iwd2stylecombat2.jpg
    image_path: assets/img/screenshots/thumb/iwd2stylecombat2.jpg
    alt: "IWD2-style combat output"
    title: "IWD2-style combat output"
  - url: assets/img/screenshots/goi.jpg
    image_path: assets/img/screenshots/thumb/goi.jpg
    alt: "Glory of Istar game shot"
    title: "Glory of Istar game shot"
  - url: assets/img/screenshots/sorcerer_monk.jpg
    image_path: assets/img/screenshots/thumb/sorcerer_monk.jpg
    alt: "Sorcerer/monk multiclass"
    title: "Sorcerer/monk multiclass"
  - url: assets/img/screenshots/fonts.png
    image_path: assets/img/screenshots/thumb/fonts.png
    alt: "Showcasing custom font support"
    title: "Showcasing custom font support"
---

main screenshot:
iwd2-kuldahar-gem.jpg
![image-center](/assets/images/filename.jpg){: .align-center}
"IWD2 remains to be fully understood"

WIP, NB: third person

---------

The GemRB team announces the availability of GemRB 0.8.7, a new minor release to kick off
a week of celebrations of the project's founding anniversary. 20 years ago, on the 21st of
August, the project initiator Daniele Colantoni registered it on SourceForge to try to make
it a team effort. Many things have happened since, the path was convoluted and bumpy, but
GemRB has continued to grow throughout the years.

GemRB is a portable free/libre open-source implementation of Bioware’s Infinity Engine, which
powered classic CRPGs like Baldur's Gate, Icewind Dale and Planescape: Torment. The goal of
the project is to make these games available on a wide range of platforms forever, fix or avoid
old bugs, add new features and provide a superb platform for mod (and eventually game) development.

It was started 20 years ago by a student fresh out of town, Daniele Colantoni:
_"I missed playing D&D with my friends so much /.../ I wanted to create my game to play
via internet. So I started my personal reverse engineering process on the base files
from Baldur's Gate."_

{% include gallery id="gallery" caption="Various screenshots." %}

Predictably it turned out to be much more complicated and time consuming than first
imagined, but the effort continued. From its Windows-only 32-bit beginnings GemRB was
made to run on all common and many niche platforms (from AmigaOS to IRIX and Symbian;
x86 to PPC, ARM, MIPS and WebAssembly). This was largely made possible through use
of open source libraries that are themselves very portable (SDL, OpenAL, libpython, zlib).
Without an open development model and supporting infrastructure, the project would have
never succeeded.

The engine can be used to play the full Baldur's Gate saga, the first Icewind Dale and
Planescape: Torment. The latter requires more reverse engineering and polishing, but
one can finish the game already. Icewind Dale 2 is a different matter — while it
appears more polished than Torment, only the first two chapters of the game are
playable.

As GemRB marks its 20th anniversary, Jaka Kranjc, the current maintainer, is optimistic about
the project's future. _"Our work is not finished, but this sort of thing is like an
ultramarathon — for most of the run the goal is not within reach. Companies come and go, but
FLOSS persists!"_

The [new release](https://gemrb.org/2020/08/24/gemrb-0-8-7-released.html)
brings over 500 changes manifested as bugfixes, smaller features, cleanups
and an improved setup experience. More than that, it introduces a new [smarter
pathfinder](https://gemrb.org/2020/07/16/new-pathfinder-smarter-movement.html) with
bumping support and other movement related improvements. At the same time work continued
on the drawing and GUI handling rewrite — stay tuned for a deeper dive later this week.
With this anniversary release out of the way, finishing that rewrite is again the team's
main priority. 

Overall it's clear that after all this time the GemRB effort is still active, slowly building
missing pieces of the Infinity Engine mosaic, revitalising older code, extending features and
working throughout the project to keep the effort vibrant for years to come. The team is
looking for [new contributors](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md),
especially programmers with OpenGL experience, who could help them finish a drawing backend
refactoring — for better performance and to remain available on a wide berth of platforms.

A pearl to you!

_PS: check our news section in the following days for a daily retrospective with past maintainers and a look into the project's future._ 

---
Project links:
- Web site: https://gemrb.org
- Downloads: https://gemrb.org/Install
- News: https://gemrb.org/News (RSS available)
- Screenshots: https://gemrb.org/Media

If you want to be notified of further releases, subscribe to
[gemrb-release](https://sourceforge.net/projects/gemrb/lists/gemrb-release) (low volume).

If you _need_ to get in touch via email, write to <registracije+gemrb20@lynxlynx.info>.
