---
title: Interview with László "Avenger" Tóth on the 20 year anniversary of GemRB
author: Jaka Kranjc, László Tóth
---

László "Avenger" Tóth, a long time project maintainer, was one of the most prolific
contributors to GemRB, tools for modding and the wider quest to understand the
original engines. On the occasion of the anniversary, we asked him a few questions.

**1. How did you find your way into GemRB?**

I was still modding and coding my editor in the TeamBG community when
Balrog approached us with his budding project. It could already render bg1
areas and had all the basic framework in place. This seemed ideal to me,
because I couldn't myself start such a big project, do the administration
and all the other jobs, but there was still a lot to do.

**2. Was it hard to get other people interested to contribute? How helpful
 were platforms like SourceForge, FLOSS communities of the time and the
 game fanbase?**

There were always interested people, but it was somewhat hard to keep them.
I think we were understaffed by 1-2 people, and this slowed the work a bit.
Especially when Balrog left us, but luckily we had enough people at that
crucial time.  SourceForge was a bit different at that time. The fanbase
was always mixed, we had many trolls who couldn't believe that GemRB would
ever work and "supported" us with trolling. There were also fans who tried
to compile GemRB (and succeed) on the wildest platforms I could imagine.

**3. For you, was reverse engineering more a thing of testing the games
 or looking at the disassembly? What tools and tactics did you use,
 especially considering there are 8 major versions of the IE engine out
 there?**

First, reverse engineering (with IDA) was a necessity. We couldn't
continue work on a few obscure parts that seemed to be used internally, but
there was no way to directly test them. It took me a week to get a grasp of
the effect framework. By that time, we already had something in place, and
I was surprised that a lot of things were coded exactly the same way we
did. By the end of my work, I had 99% of the code recovered and I could
read it like it was source. Having decoded one engine, the rest was much
easier (The first disassembly worked like a Rosetta Stone).

**4. Was there any help or obstruction from official developers at any
 point?**

No, there was never any obstruction from developers (Neither Bioware nor
Beamdog). A minor obstruction was that I got hired by Beamdog, so that
kinda ended my GemRB involvement. Not like they forbid it, I just couldn't
work on the "same" code all the time.

**5. Do you remember some contributions that you're really proud of (be
 it a milestone like getting a subsystem to work, first area to draw
 etc. or something else)? Or a problem that was especially infuriating
 to solve?**

I'm pretty proud of the effect subsystem. The fact that the same GemRB
version could simulate all the Infinity versions. To some degree, I also
like the projectile system, some parts of it (mostly the extended .PRO
structures) got their way into the EE engine.

**6. Do you remember any amusing anecdotes, discoveries or original
 engine quirks? What's the worst hack or most silly design that you
 encountered?**

There were ugly hacks, and hacks of hacks, but I don't always remember the
time when I discovered them (at the time I already saw the original
Infinity code, or not). So best lets not talk about what is under the hood.
One can look at GemRB and find their ugly hacks there, rest assured, it
isn't looking worse than the original.

**7. Which one was your favourite IE game and do you still play it? Or
 other old games? Or contribute to other
 reverse-engineering/reimplementation projects?**

My favorite game as a player was Planescape Torment, but as a reverse
engineer / coder I hated it and even seeing the original code didn't help
that feeling. After I finished my involvement with Beamdog, I don't think I
will ever play any other IE game. Unless someone makes a totally new one
with GemRB.

**8. Any final thoughts about IE games and GemRB 20 years later?**

I hope someone finds GemRB useful and motivating enough to develop a new game.
