---
title: History of the engines and games
toc: true
---

## Infinity engine games

They came out at the start of the millennium and from different authors only
partly sharing code, resulting in quite a mess: several different systems for
the same things and many many avoidable hacks.

![timeline](/assets/img/ie_chronology.png)

If you want to learn more about their development and times when these games
were made, David Craddock wrote a nice [interview series
(book)](https://www.shacknews.com/article/103473/beneath-a-starless-sky-pillars-of-eternity-and-the-infinity-engine-era-of-rpgs?page=1)
with the authors from the various studios.

In 2012 and onward, all but IWD2 received Enhanced Edition versions, by being
ported to an upgraded BG2 version of the engine or getting high resolution and
input upgrades.


## Modding communities

What made the games last so long is their extensibility, as several things are
easily edited with a text editor and at the same time, the publishers and
developers didn't discourage serious modding. Some even joined the efforts as
was the case with the Ascension mod for Throne of Bhaal.

Besides wider RPG communities like Sorcerer's Place and RPG Codex, several
dedicated ones sprang up and eventually wound down. One notable example is
TeamBG, which harbored many seasoned programmers and reverse engineers,
demonstrating a lot more can be done than previously thought. At some point
[IESDP](https://gibberlings3.github.io/iesdp/) was started to host technical
documentation from the reverse engineering of the original engines.

In the long term, as even the official forums closed as they are always bound
to, we are left with several active modding sites, all part of the same wider
community. [Pocket Plane Group](http://pocketplane.net/),
[Spellhold Studios](http://www.shsforums.net) and
[Gibberlings3](https://www.gibberlings3.net/) are among the most prolific
(if not sturdy) of the English ones and the latter is also where GemRB found
its true home.


## GemRB is born

The exact origins of GemRB are lost to time, but on the **21st of August
2000** the project registered on the SourceForge hosting platform, which
is our main [file host](https://sourceforge.net/p/gemrb) to this day. So
**GemRB development started even before all games were released!**

But it's clear the talks started sooner, since the first message to a
mailing list created the following day mentions older pine mailing
lists. **Daniele Collantoni** was the initial driving force and after
some rough beginnings, serious and full blown development was again
underway by late 2003, as evidenced by the CVS logs and news items.

That was the start of version tracking for the project, which later
transitioned to SVN and finally GIT. Code hosting was moved to GitHub in
2013, which made flyby contributions much easier. Eventually in 2019, the
bug tracker was moved there as well and now in 2020, it hosts the project
home page.

Forums were initially hosted on SourceForge, but by early 2005, we opened
a subforum on the Gibberlings3 community forums, which is still used today.
Another change through the years was in instant messaging. Some of the first
talks happened over ICQ, since 2003 on IRC, but most recently users have
been migrating to Discord.

For the [20 year anniversary](/2020/08/24/the-gemrb-project-celebrates-20-year-anniversary-with-a-new-release.html)
in 2020, retrospective interviews with several prominent contributors to
the project were made
([1](/2020/08/25/interview-with-project-founder-daniele-collantoni.html), 
[2](/2020/08/26/interview-with-jarda-benkovsky.html), 
[3](/2020/08/27/a-look-into-the-next-big-thing-for-gemrb-with-brad-allred.html), 
[4](/2020/08/28/interview-with-laszlo-toth.html), 
[5](/2020/08/29/interview-with-jaka-kranjc.html)).

With 0.9.0 a major internal project dubbed *subviews* was completed after
over five years of effort, modernizing the GUI, drawing and input handling
among other things. A [technical overview](https://github.com/gemrb/gemrb/wiki/Subviews---Origins-and-Summary-of-Changes)
is available.

## Development milestones

Major game milestones, GemRB releases when a certain game became completable:
- **0.5.1**, 2009: BG2:SoA
- **0.6.0**, 2009: BG1, IWD
- **0.6.3**, 2010: IWD:HoW
- **0.7.0**, 2011: full BG saga (BG2:ToB support)
- **0.8.0**, 2013: IWD:TotLM, BG1:TotSC
- **0.8.4**, 2016: PS:T
- **0.9.0**, 2021: GemRB Demo
- **0.9.4**, 2024: IWD2
