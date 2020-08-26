---
title: Interview with Jarda "Edheldil" Benkovský on the 20 year anniversary of GemRB
author: Jaka Kranjc
---

For the third day of anniversary celebrations, we asked a few questions from Jarda
"Edheldil" Benkovský, a long time project maintainer, [iesh](https://github.com/gemrb/iesh)
creator and the first web guru.

**1. How did you find your way into GemRB?**

I thought that it would be hard for me to remember, but fortunately I 
found our project's old backups still rotting somewhere in 
backups/BACKUP/backup_2005 directory on a NAS, so after a bit of digging 
and bouts of nostalgia I had the answer.

Sometime in the second half of 2003 I read on Slashdot or Freshmeat 
about a project to reimplement the engine for Baldur's Gate, Icewind Dale 
and, crucially, Planescape Torment, my favorite AD&D setting.  I had the 
boxed material from TSR, I had played through the computer game and had 
been facinated by its storytelling, by stories of brash Annah, zen-cool 
Fall-from-Grace and sorrowful Deionarra, loving from behind the grave. I 
am a bit romantic, you see ... I wanted to participate in that project 
so that I could play it it again (I wholy switched to Linux years 
earlier) and also to make it accessible to other Linux users. Sigil, the 
City of Doors, opened a door for me to enter.


**2. Was it hard to get other people interested to contribute? How helpful
 were platforms like SourceForge, FLOSS communities of the time and the
 game fanbase?**

To be honest, I am not sure how people mostly found about us. I guess it 
was the combination of OSS-centered news sites and people searching for 
mods stumbling over us by chance. I tried to get some coder friends 
interested, but they were unfortunately put off by the archaic dialect 
of C++ we were using back then.


**3. For you, was reverse engineering more a thing of testing the games
 or looking at the disassembly? What tools and tactics did you use,
 especially considering there are 8 major versions of the IE engine out
 there?**

I like poring over disassembly, but I did not get to it with Infinity 
Engine - other guys had already much more experience with it, so I did 
not see the need. I mostly just ran the original games under Wine and 
compared their look and behavior to GemRB. Otherwise I used IDA, Near 
Infinity, iesh and custom Python scripts.


**4. Was there any help or obstruction from official developers at any
 point?**

None I know of. I did not really believe that the original source code 
had been lost, as somebody was telling us (it hadn't), but I did not 
think the original devs could legally provide it anyway, so it doesn't 
count.


**5. Do you remember some contributions that you're really proud of? Or
 a problem that was especially infuriating to solve?**

Oh, I do not know ... I was very proud when I converted the adhoc 
Makefiles we used when I joined to automake + autoconf + libtool. 
Fortunately it has been since replaced with cmake. I spent a lot of
time with PS:T's [GUIScripts](/GUIScript/Index.html), so perhaps that counts as well.


**6. Do you remember any amusing anecdotes, discoveries or original
 engine quirks? What's the worst hack or most silly design that you
 encountered?**

I was quite surprised to find out that Baldur's Gate 2 data directory 
contains quite a few Baldur's Gate 1 files and stand-in images.


**7. Which one was your favourite IE game and do you still play it? Or
 other old games? Or contribute to other
 reverse-engineering/reimplementation projects?**

My favourite was definitely Planescape: Torment. The imagination of its 
world, all the lost souls, a certain body-disadvantaged companion... 
It's some time since I have played it last, though. But reverse 
engineering old games is still my ocasional passtime; I use to dig into 
Darkseed when I want to  rack my brain with assembly.


**8. Any final thoughts about IE games and GemRB 20 years later?**

I am really glad that I could collaborate with some very talented and 
nice people. I am also proud of the work we have done on the project.  
Too bad that we did not attract some indie game studio to build a new 
game using our engine.


