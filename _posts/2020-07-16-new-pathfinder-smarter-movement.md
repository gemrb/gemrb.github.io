---
title:  "New pathfinder: smarter movement"
author: Kevin Michael Frick
---

After a year of work and countless corner cases the pathfinder upgrade is finally
done! Yay, cool. But what's a pathfinder?

It's an implementation of one of the algorithms developed as part of the graph
theory branch of mathematics, that is a "single-source shortest path" algorithm
which...

> zzz

Yeah, okay, sorry. Think of it as "movement code". When you order your party to
move, or when enemies come to you to try and kick your ass, that's the
pathfinder at work.

What it does is build a set of points that characters must move to to get to
their destination. So you take point A, point B, point C and move one step at a
time, that's the gist of it. Control engineers call "moving one step at a time
towards your goal" a "proportional regulator" and it's also how cruise control
on your car works. 

The issue that prompted this upgrade is that, with the old pathfinding code,
characters could only move at 45-degree angles, which didn't match the
originals. Therefore the main improvement is that characters can now **move
at any angle**, providing more fluid and realistic character movement.

This upgrade also brings in one new feature from the originals: **actor bumping**.
When somebody's moving and a "nice enough" actor stands in his or her way,
that actor can move out of the way for just the time needed for the moving
character to pass. This is done only if there is no other way, like when an
actor is blocking an open door; characters will always prefer moving around
somebody instead of bumping.

Furthermore, as in the originals, characters will now **back off and wait** for a
while when the situation is too crowded, again providing smoother movement
instead of continuously re-calculating the paths to be taken.

The whole movement pipeline was also improved: characters will only stop
mid-way if there really is no hope of reaching their targets and **bigger
parties will not get tangled up** when moving all together. 

One last bonus is that, previously, base walking speed was the same for all
games, while the originals all had different speeds. This is most noticeable
in Planescape: Torment with its bigger sprites. This pathfinder **unhardcodes
base speed** into an .ini file variable, allowing varying speed between games
and providing one more degrees of freedom for making new games with GemRB.

So here it is and we hope you will like that your characters now learned
how to walk smarter. :)
