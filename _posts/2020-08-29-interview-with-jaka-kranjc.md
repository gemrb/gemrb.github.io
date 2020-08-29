---
title: Interview with Jaka "lynx" Kranjc on the 20 year anniversary of GemRB 
author: Marcel Heing-Becker
---

For the final day of anniversary celebrations, we asked a few questions of
Jaka "lynx" Kranjc. He is the current project maintainer, long time release manager,
experimental modder and IESDP steward.

**1. How did you find your way into GemRB?**

I'm pretty sure I first learned about the project from the The Linux Game Tome 
(HappyPenguin) release news website. I kept following the project and its 
occasional releases and at one point in late 2007 it just became clear that 
progress is too slow and that I can do something about it *as a forester*. I
compiled GemRB, ran it and immediately saw bugs in BG2 character generation.
Popping on IRC, some were fixed as soon as they were reported, but as I
started providing patches, it didn't take long for Avenger to grant me commit
access and not have to bother with manually applying them.


**2. Was it hard to get other people interested to contribute? How helpful were 
platforms like SourceForge, FLOSS communities of the time and the game 
fanbase?**

Projects like this have a nearly endless stream of interesting problems to 
solve, from fixing bugs, enhancing original behaviour, reverse engineering, code 
review and refactoring ... to less technical ones like maintaining project 
infrastructure, community engagement, testing, research, promotion, modding and 
more (*[check your fit here]({{ site.contribute }})*).

And all 
these tasks and roles attract different people at different stages. I think the 
most common motivation is still to scratch your own itch (do what you want), but 
it also helps when more people are active, since there are synergistic effects. 
And lively projects appear healthier and sexier, so that helps with attracting 
new talent. At times we are searching for particular skills and setups, but 
there's no easy way to just get it. As cool as the games are, even the wider 
community is a bit of a niche one and it's unlikely that technological problems 
themselves will be enough to attract people (though that has happened as well). 

So it's very important to be transparent and develop in the open, in a way let 
the project speak for itself. Having access to "cost free" infrastructure like 
SourceForge, GitHub, Travis, AppVeyor, Coverity, Sonar etc. is very valuable in 
the sense of productivity, but also in ensuring consistent project availability. 
Lowering the bar for entry has always helped us get more contributors, be it 
through better tooling (eg. revision control), documentation or clarity of 
needs. Which is all crucial if you want to convince people to volunteer some 
time for a crazy project like this. 

The game fan bases can't be underestimated 
either. What a resilient and curious bunch of people! :) To this day they 
continue to torture the games and themselves, trying to answer obscure questions 
about engine behaviour. Without that continuous thirst for knowledge and 
willingness to share it, we'd have a much harder time developing GemRB.


**3. For you, was reverse engineering more a thing of testing the games or 
looking at the disassembly? What tools and tactics did you use, especially 
considering there are 8 major versions of the IE engine out there?**

It's definitely more about playtesting, when needed, as I don't really read 
assembly. There's usually a wizard around that can answer such questions. For 
many things neither is needed though, especially if you played some of these 
games more times than you're willing to admit. Yep. 

As far as tools go, the 
existing modding tools are of great help when exploring and deciding what's a 
data bug and what's ours. Plain old "strings" can be used to check if something 
was hardcoded in the original EXEs. I upgrade 
[iesh](https://github.com/gemrb/iesh) as needed to support more formats; this 
tool is great for answering questions like "Is this field/bit unused?", since 
you can script it to check all files in all games. Using it or ielister to 
pretty-print binary files is also very useful. For one to enable a readable `git 
log` for the unhardcoded binary data that we ship, but also to compare savegames 
between the engines, which is important for compatibility.


**4. Was there any help or obstruction from official developers at any point?**

I don't know of any obstruction, though one could say we had a case of "stealing 
developers" with the release of the enhanced editions. But not really. They 
released a few file format headers, which helped confirm some reverse-engineered 
guesses and provided other info, as in a sense, everyone was seeing the code for 
the first time. 

Looking forward, the fact that they copied some of our designs will 
inadvertently enable us to provide compatibility more easily. More importantly, 
reviving the broader community and general interest is probably the single most 
important contribution.


**5. Do you remember some contributions that you're really proud of? Or a 
problem that was especially infuriating to solve?**

There have been many exciting moments in the project. For example when we made 
Planescape: Torment completable for the first time in 2016. Or when the 
10-player party mod was good enough (a perl monster). Or this new website. I've 
also removed a lot of duplicated code — GitHub stats state that in all these 
years I've still removed more code than added (23k lines left to equalize). 

In the rare case I find something infuriating, I avoid it or pause for a while.
It has worked so far, but I'm not easily riled up.


**6. Do you remember any amusing anecdotes, discoveries or original engine 
quirks? What's the worst hack or most silly design that you encountered?**

At least one of the GUI data files uses one of the Windows 95 desktop wallpapers 
as a background. The originals are littered with hacks and quirks and 
unfortunately we have to copy many of them in some way. Cursing and eye-rolling 
are not that rare, especially when you see they invented something new, badly, 
while there was already a good mechanism of achieving the same.

Once I wrote a [limerick in a commit 
message](https://github.com/gemrb/gemrb/commit/c00a2303adf8319dc3bb8e3a93419456d824ffbc),
asking for help. A new contributor joined soon after and did much more than was
asked for. Appears serendipitous, but surely just a thing of chance.

If we weren't stuck with the game data, I'd retroactively change the scripting 
design to have linear execution, so successful trigger evaluation is 
immediately followed by the execution of their action block. Probably would end 
up just using Python directly. For all the other features that would bring and
to make the experience more like reading books and other programming languages.


**7. Which one was your favourite IE game and do you still play it? Or other old 
games? Or contribute to other reverse-engineering/reimplementation projects?**

I started with BG2 and most often played that. But I really like the story and 
elegance of IWD2, not to mention the mind-boggling PST. I'm hard pressed to 
choose an overall winner. I still play them for testing now and then, sometimes 
at a properly non-rushed pace. Having worked on their implementation made me 
appreciate them in new lights, eg. even the bag of hacks that is PST has done 
some things better than all the games that came after it.

Other older games ... I'm trying various RPG classics now and then, but the only 
other game I've replayed several times is a strategy mix: Jagged Alliance 2. It 
was later poorly open-sourced and the proper continuation of the improvement and 
porting efforts resulted in the [Jagged Alliance 2 
Stracciatella](https://ja2-stracciatella.github.io/) project. I mostly do code 
review there and help steer it; GemRB and the Infinity engine remain my main 
passion.


**8. What's on the GemRB feature/tech plan for the future?** 

[Brad talked about the major plans](/2020/08/27/a-look-into-the-next-big-thing-for-gemrb-with-brad-allred.html)
in a separate article, but personally I'd like to get the 
time to work more on IWD2. It's already a surprisingly polished experience, but 
the game remains unfinishable after a few chapters. And it's our last original 
game to be conquered! However, the subviews branch needs to be finished, so
I have to help with that first.

I also have an old stash of the beginning of a combat code refactor, since the 
originals used quite an exotic way to figure out round timing (a picture), which 
we don't support yet. Externalizing more of the combat logic is also important 
for anyone else that may want to use the engine.

At some point we'll also have to clean up our character animation subsystem.
It's my least favourite part of the codebase and I barely touched it, but it's
again something that can reduce the need for a bunch of hacks and also make
adding new animations much easier to understand and implement. It definitely
won't be done by me though!


**9. Is there any organizational or financial support on your wishlist? 
Something else you consider still missing or worth improving?**

Striving to get the [CII Best 
Practices](https://bestpractices.coreinfrastructure.org/en/) badges helped shine 
some light on the weak areas of our project. This work is now done and there's 
not much room to meaningfully improve further until we grow enough or change 
significantly. It includes things like license assignment (CLA) that are just 
off-putting, but that's also the only thing that comes to mind where 
organizational support would be required (eg. from the Software Freedom 
Conservancy).

One obvious thing that should always be worked on is getting more people on 
board and increasing the bus factor. In a technical sense, recruiting someone 
strong in graphics programming would really help for our next release and making 
the SDL backends the best they can be. Our mobile ports have bitrotten, so until 
someone that cares enough comes along, they will remain unusable.

Project communication is also something that can always be improved; both 
external and internal. How to get more people to notice our news, is syndication 
(planets) still a thing, should we consider social media etc. For internal 
communications we have enough channels, but some contributors don't use them, so 
most of the discussion is done on the tracker. That's not inherently bad, but 
it's also not ideal, since it's drier and less realtime, meaning it's easier to 
get misunderstood and worked up.

As for financial support, we've always redirected donations and never sought 
them, since there's no obvious cost involved. I don't think anyone ever 
considered trying to make a partial living out of it (as someone did with OpenMW 
IIRC), setting up bounties or just hoarding it. It could be used if we ever 
wanted to have an in-person hackathon or to cover costs for some other event 
like FOSDEM, but like I said, nobody ever bothered and the motivation comes from 
elsewhere.


**10. How much time do you currently spend on GemRB for contributing? Per week 
or month, or generally.** 

It varies with time, work stress and motivation. At 
minimum I check the Gibberlings3 forums almost every day, to see if anyone needs 
help, any new discoveries have been made or if anything else interesting 
happened. Similarly with email to see the latest chatter on the issue tracker, 
review code changes and triage bugs.

Sometimes things just align and I fall into the Zone, deep hack mode or however 
you want to call it. Then time just disappears, a whole day is gone without 
noticing, and while a lot is achieved, I have to remind myself of the loading 
hint from BG2: _While your character does not have to eat, remember that YOU do. 
We don't want to lose any dedicated players._


**11. Any final thoughts about IE games and GemRB 20 years later?**

From the onset it has been a gargantuan task, so I'm immensely grateful to 
everyone that has contributed to GemRB over its history, making it as good as it 
is today. Our work is not finished, but this sort of thing is like an 
ultramarathon — for most of the run the goal is not within reach.

Companies come and go, but FLOSS persists and GemRB is even archived in GitHub's 
[Arctic code vault](https://archiveprogram.github.com/), ensuring our beloved 
games will be able to be played for decades to come. Come and help us continue 
[our run](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md)!

