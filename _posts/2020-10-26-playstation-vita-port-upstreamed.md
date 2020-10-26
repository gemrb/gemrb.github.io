---
title: PlayStation Vita port included in sources
author: Jaka Kranjc
---

GemRB has been running on the PlayStation Vita since roughly the last
release, when **Taras "Northfear" Rohozhynskyi** published his work for the
[first time](https://vitadb.rinnegatamante.it/#/info/572). The port
includes the necessary input support, some performance improvements, a
a widescreen-like mode to optionally fill the whole screen when in game and
easy launching through its LiveArea content manager. All of the games
should be working, but BG2 is still limited by I/O performance, so it's
less playable than the rest.

{% include figure image_path="assets/img/news/ps-vita-bg1.jpg" 
   alt="PS Vita port image" 
   caption="PlayStation Vita GemRB port in action, showcasing the wider display." %}

As it often goes in porting to new platforms, many of the required changes
are quick fixes and hacks, just to get further in the process, uncover any
blocking issues and see how much work reallly remains. The result is usually
something we can't just include directly, but something that requires more
effort to find the correct solutions, not break functionality for others
and so on.

Luckily Taras not only submitted his code for review, but has been happy to
work with us to clean it up and find general solutions. As a result, the
changes required to make GemRB run on the Vita are now included in our main
tree and will benefit from other work going forward. It's something we'd
like to see from porters more often, as sometimes they don't even get in
touch.

We now have broader gamepad support, caching in the SDLAudio plugin and a
more performant engine for platforms that don't have a fast `mmap`. To
illustrate the importance of the last change: it was made before the
current release **as an optimization**, but it later turned out we haven't
accounted for all the platforms we support — a similar complaint was
voiced by porters to Amiga and MorpOS.

So thank you Taras for the port, making life easier for other porters and,
of course, for making GemRB that tad bit better!
