---
title: A look into the next big thing for GemRB with Brad Allred
author: Jaka Kranjc
---

Brad "SyntaxError" Allred is a long time contributor that focuses mainly on internal
subsystems like text rendering, multibyte font support, input, the iOS port and
more. On the occasion of the anniversary, we talked to him about the current big
project, which will represent a leap forward for GemRB.

**1. First, how did you find your way into GemRB?**

It's hard to recall the exact circumstances now that more than 10 years have gone by.
I do remember I experiencing frustration that my favorite games from childhood wouldn't run
on my modern Mac. I remember WINE not being the best experience either.

I went on a "quest" for a better way and found GemRB. I got really excited about it until I
realized that it didn't work for (modern) Mac either! Since it was FOSS and I was exploring
software development as a hobby (and later as a formal education) I decided to give a crack
at patching it to work. Happily, I was able to do so after some moderate hair pulling and
later I also ported GemRB to iOS as well.


**2. You seem to have a preference for working on various aspects of the user
interface. Is there any special reason for that?**

That is an excelent question and I don't think I have just a single answer. At first it was
due to it being the most accessable part of the code for me. It was far easier to understand
at the time so it was just a natural starting place. There was some low hanging fruit to fix
to get my feet adequately soaked.

At some point somebody asked about using different fonts for GemRB and I thought it might be
a good challenge to get TTF fonts working. This led to some additional effort to make GemRB
more internationalized with some unicode support etc.

I guess the tl;dr version is that it was the most natural path for me to take given my initially
limited knowledge and later on expertice. It's also highly related to what I had wanted to 
originally acomplish since the ports for Mac and iOS required fiddling with SDL quite a bit.

**3. I thought we'd be good for a while after the big text subsystem rewrite
in 2015 that took over a year. But if I remember correctly, it was the lost
text editing support and slow drawing of (MTA) text with OpenGL that prompted
the start of an even longer project — the subviews branch. Tell us a bit
about its origin.**

Indeed, the things you mentioned were probably the straws that broke that camel's back. However,
the need for a major refactoring to the GUI, Event System, and necissarily by extension the video
driver was gestating ever since the port to iOS.

When I was porting to iOS, it became apaprent we needed some kind of SDL 2 support so
I had to hack together or SDL2 video dirver. It isn't great code to be honest, and it runs poorly
as it is really just an update to a texture everyframe. The touchscreen input is also just a
messy hack. All of this, combined with some other frustrations with the GUI rendering and event
handling, led me to finally break and start a long term (loger than anticipated for sure)
development branch where I could finally address many of the nagging issues and make a properly
hardware accelerated SDL 2 backend.

Other things eventually surfaced that made me grateful for starting this development when I did.
SDL 1.2 was "discontinued" and no longer functions very well at all on modern Macs (I get something
like 7 fps on a 2016 laptop). I'm not sure I would have continued working on the project if I hadn't
had this other branch to work on since the experience was so poor on master.

Of course I. hadn't planned on it taking so many years, and even more changes. Lots of parts of the 
engine I had no familiarity at all with ended up needing at least minor refactors to work with the new
rendering API.

**4. What do views, subviews and all the other accreted changes bring to
the table?**

With so many changes its impossible to list everything. Most of the major additiomns are summarized on
our [wiki](https://github.com/gemrb/gemrb/wiki/Subviews---Origins-and-Summary-of-Changes). We also have
several issues/features [tagged](https://github.com/gemrb/gemrb/issues?q=is%3Aissue+is%3Aopen+label%3Asubviews-recheck)
that will be resolved upon merging.

**5. The refactoring is slowly nearing completion and is currently the main 
TODO of the project. What are the remaining areas of work? Where could we
use further help?**

I think we finally see light at the end of the tunnel and there isn't much major work left to do on it.
Probably the main area we could use help is just general testing and bug reporting. PST still has some
rough spots that are hopefully just minor script changes. Of course so much has changed in areas far
beyond what was initially anticipated that there could be regressions in just about anything.

It would be great if somebody with Vulkan experience wanted to join up and add a proper accelerated backend.
The barebones SDL 2 backend has a couple of rendering limitations. The game is still quite playable, but for
the best experience you need to have SDL 2 + OpenGL and its only a matter of time before OpenGL fades out of
favor (Apple has already depricated it years ago).

**6. What comes after that? (post-subviews, py3, your own plans/wishes)**

First thing are a couple of issues I've purposely archived for after the merge is complete. Nothing exiting,
but there should be a nice performance boost for text rendering for people.

I'll probably take a short break after things settle down (I'm expecting at least a little fallout) to finish
and realease a project of mine I have sitting on the backburner.

In the future I'm likely to continue the same path. We desparately need some crossplatform configuration
GUI IMO. Luckily that development woundn't require any refactoring :)

Python 3 needs to happen of course. I'm still unsure of the best approach to addressing that elephant.

**7. Do you have a favourite IE game and do you still play it? Do you
contribute to other reimplementation projects?**

I would probably have to say Baldur's Gate II is my favorite. It's probably a nostalgia thing, but also haven't
had much experience with IWD/PST. I now own all the EE versions of the games and at some point maybe I'll find
time to play them all. I've never finished the Icewind Dale series, and never even played Planescape Torment.
I hear I'm missing out.

There were a couple of times I was tempted to make a contribution to other projects, but my time is so limited
and I have a great many other hobbies to enjoy.

**8. Any final thoughts about IE games and GemRB 20 years later?**

I must admit a certain sadness about the release of the Enhanced Edditions. Not that they arent well done, but
it feels like we lost a lot of development interest when they came out. I might be wrong there; after all the
project is still alive. I think that says a lot about how great these games are. They are timeless and will be
enjoyed for many years to come.

I certainly learned a lot while working on it. In fact I have the job I have now largely thanks to being able to
show my work on GemRB so I'm very grateful there are interesting FOSS projects to get involved with to help skillbuilding.


_Tune in tomorrow to hear from Avenger, the maintainer that succeeded Edheldil._
