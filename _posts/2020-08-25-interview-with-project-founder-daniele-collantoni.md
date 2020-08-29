---
title: Interview with project founder Daniele Collantoni on the 20 year anniversary of GemRB
author: Jaka Kranjc
---

On the occasion of the anniversary, we asked a few questions of Daniele "Balrog994"
Collantoni, the project founder and prolific contributor.

**1. What was the initial motivation to start GemRB, even before all the
games came out?**

It all started when I was a teenager. I was working in a movie rental shop
in a little town of 6000 inhabitants in the middle of Italy. At that time,
the shop was also selling videogames and consoles (you know, the good old
PS1 times). My job was about showing customers the new games available for
PS1 and PC and obviously make sales. So I was spending most of my day
talking about games and trying most of the new games that were coming to
the market.

While I was working there I met one of my best friends nowadays that
introduced me to Dungeons & Dragons 2nd edition. We started playing
tabletop games 2 or 3 times a week for a few years and I loved playing D&D.
Then "Baldur's Gate" came out in 1998 and obviously I had to buy that game;
it was based on D&D mechanics and I was a super fan of that. So me and my
friend played that game every day for a very long time trying to complete
every single side quest available. We loved that game! In the mean time I
was learning by myself some C++ while trying to hack the italian pay tv
(yeah, I know... It was a long time ago and I was too young). In the year
2000 (I was 18 at that time) I had to leave my small town to go to
university 200 km away and so I stopped playing tabletop games. I missed
playing D&D with my friends so much and I decided that I wanted to learn
more about how Baldur's Gate was made, because I wanted to create my game
to play with my friends via internet (56k was the best available at that
time, but it was better than nothing). So I started my personal reverse
engineering process on the base files from Baldur's Gate.

If I remember correctly I started from the main index file that was
containing references to all included resources. At the time I was a
noob at programming and I learned a lot developing GemRB, really a LOT!
I still remember today the first UI displayed on my old CRT monitor, it
was the loading progress bar of BG1 with the skull in the middle.
Unfortunately I don't remember exactly when the project was uploaded to
SourceForge, if before or after I met Avenger, but that's how it all
started.

**2. What's up with the odd name? Were acronyms just fashionable back then
 (eg. SCUMMVM), was there a lack of inspiration (*"There
 are 2 hard problems in computer science: cache invalidation, naming things,
 and off-by-1 errors"*) or something else?**
  
The story about the name, I guess, is pretty simple. I had to choose a
name for the project that had nothing in common with the original Infinity
Engine because of reasons... We were reverse engineering a commercial
product (still active and selling) without explicit permission, basically
violating the EULA, so the idea was to be as less visible as possible at
first. Yes, at that time acronyms were the naming style, but I was still
lacking inspiration. :) The only idea I had in mind was a Gem... Then I
tried to stick some kind of acronym to the word "gem". "RB" came after I
realized I needed at least 2 more words to give sense to the acronym.


**3. Was it hard to get other people interested and slowly turn it from
 one guy's hobby to a team effort? How helpful were platforms like
 SourceForge, FLOSS communities of the time and the game fanbase?**

Initially it was my personal project and it was not meant to become a
team effort, it never was. But I remember that, a few months after I
started working on GemRB, I realized I would never finish that project
alone in a decent time, so I opened a "search for help" position on
SourceForge and so the team effort started. I was not used to working
in a team and my English was pretty bad, so it was a bit hard at times
but was really rewarding. Especially after finding out IESDP thanks to
Avenger. At that time there was a lot less information, but it was
extremely useful for me. I had the opportunity to understand things
that were totally obscure before! 

At that time the open source
community was not as large as today, there were only a few people
willing to help and without SourceForge it would not be possible to
develop such a big project and find people who care and want to 
continue to bring the project forward. The fanbase was pretty much
unexistant at that time, maybe 1 or 2 people every six months was
asking something, but obviously the project was not complete nor usable
by end-users. It was still a development build, extremely complex to
setup, build and run.


**4. How did you perform reverse engineering in the very early stages? At
that time there was little tooling available and IESDP (file format
description project) didn't exist yet.**

As I said before, I started reverse engineering the file formats by myself
using UltraEdit32. It was basically done by trial and error, trying to
understand what a value meant and what you actually needed to implement
the feature. This was driving the research on the file formats. When I
met Avenger he already started working on IESDP, and some documentation
was already available, but all the work I did before was all done by trial
and error.


**5. Was there any help or obstruction from official developers at any
 point?**

I never heard anything from the official developers. No help, no
obstruction. They just ignored us, which was good and bad at the same
time. :D


**6. You were very prolific once the project really got going. Do you
 remember some contributions that you're really proud of? Or a
 problem that was especially infuriating to solve?**

Well almost everything about GemRB makes me proud. As I described above,
probably the thing that I remember the most was that loading screen with
the skull that was the first thing I worked on. I remember working on GemRB
on Windows 98 and I remember a lot of BSOD because I was not freeing GDI
resources (I didn't even know there was something to free at the time) and
the kernel crashed when reaching 65535 opened handles. I remember
introducing Python scripting for UI (python was pretty new in the early
2000) and I choose Python because it was simpler to integrate with C++. I
remember rage quitting trying to find a stupid memory leak in the UI code
(Avenger took over that memory leak and fixed it in a night). I remember
working on the A* pathfinder not even knowing what A* was. I remember
implementing the fog of war and the first interaction with areas on the map.
I remember my crazy calculation on how to change the color palette of
sprites so that character could have customizable dress, skin tone, and so
on. Too many things to remember really, I'm very proud of GemRB and I'm
proud of the people that continued working on the project in all these years.


**7. Do you remember any amusing anecdotes, discoveries or original
 engine quirks? What's the worst hack or most silly design that you
 encountered?**

The original plugin system used by GemRB was inspired by the plugin system
used by 3D Studio Max. Probably you could take a GemRB plugin and load it
in 3D Studio Max (the old year 2000 version) without any problems. :)

Originally GemRB was working only under windows and there were no plans to
make it portable. Since it was running under windows, the original rendering
was based on GDI (not even GDI+ if I remember correctly), but was really
really slow, so months later we moved to SDL (I even made an OpenGL renderer
at some point).


**8. Do you still play IE or other old games? Or contribute to other
 reverse-engineering/reimplementation projects?**

Unfortunately no, I don't play IE games anymore. With a family and a
6-years boy in the house, time for playing long games is almost impossible
to find. :D


**9. When you started out, did you forsee the longevity of GemRB? In the
sense of the length of development and the long term resilience of the
project?**

The initial plan was to create a game to play with my friends, but as soon
as I started working on the project I realized that multiplayer was a big
thing (and I had no networking knowledge at all... not even what a socket
was), so the multiplayer part was pretty much immediately excluded from the
project.

GemRB was always focused on IE games because it was simpler, the assets were
already there. It was *only* a matter of developing the same features the
original games had. Making new games from scratch is a huge effort and I was
not able to create the assets needed to build a new game. So the project was
resized to a more manageable objective.

I realized the project was a huge effort after a couple of months I started
writing code, but I never imagined that after 20 years there was still someone
who maintained the project and continued its development. That's amazing to
be honest!


**10. Any final thoughts about IE games and GemRB 20 years later?**

IE games, for me, are still the best D&D video games ever made. Today
games are far better in graphics but lacks the storytelling and complexity
that older games had. I remember the day I left GemRB and started working,
it was a really sad day because I knew I would not have time to work on
"my little creature" anymore. But I knew I left it in good hands, and so
it was. :)


_Tune in tomorrow to hear from Edheldil, the maintainer that succeeded Daniele._
