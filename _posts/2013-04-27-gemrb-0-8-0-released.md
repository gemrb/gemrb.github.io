---
title:  "GemRB 0.8.0 released! (Fork Me edition)"
author: Jaka Kranjc
---

The GemRB team is proud to announce a new major release.

It is a mix of new engine features, painstaking BG1 polishing, much improved IWD2/3ed support and hundreds
of miscellaneus fixes. Almost a thousand revisions have been made since the previous release, so the
following changelog does it no justice:

**GemRB v0.8.0:**
New features:
- iwd2: Chapter 0+1 completable, full spellbook and ECL support
- multibyte font support (chinese, korean, japanese)
- favourite weapon/spell tracking, bg1 dreams
- most gemrb overrides were moved and are now moddable via game override
- initial bundled gemrb demo stubs

Improved features:
- random encounters and spawns (properly difficult)
- iwd2 combat, stats, spells, skills, effects and actions
- animations, speech, input
- looting, worldmap, hotkeys (work everywhere), fatigue
- bugfixes

Gamewise, BG2 and IWD1 haven't received many changes, but for the first time IWD:ToTLM is playable to the end. 
IWD2 made the biggest strides and its Prologue can be played through with some minor caveats. BG1 got polished
to make the whole TotSC a pleasant and complete(able) experience, something we thought we had already achieved.
It turned out nobody tried Durlag's tower or told us of all its problems before. PST support had no major updates,
but a playtesting attempt revealed most of the todos and that the plot can be followed far into the game.

The last two things would not be possible without extensive, reactive and documented testing by "traveler" and "chiv"
respectively, which is greatly appreciated. This allowed the thralls to focus on actually fixing those problems and
cursing at the idiosyncracies of the original implementations. While PST hasn't seen many changes, we now have a
detailed list of gameplay issues to work on and test with. Interestingly, IWD2 support turned out to be much more
complete than we had anticipated, so the doors are wide open to making it as nicely supported as BG2 in a release
or two! We've also started a small dataset that is bundled with GemRB, a sort of demo. On that note, we're looking
for help in any available form!

To make collaboration even easier, we moved our GIT code hosting to Github. Existing users of git gemrb don't
need to restart the download, but just run "git remote set-url origin git://github.com/gemrb/gemrb.git" first
and then continue updating as usual.

Exciting times!

Currently only the sources and some packages are available. You can get them from here.

Release notes:

GemRBOverridePath was split, so it now contains only the few real gemrb
overrides. A new preset path variable has been introduced to hold the
remaining files, called GemRBUnhardcodedPath. It is searched after the
game paths, so its can be easily modified by being placed in the game's
override folder.

New optional dependency on iconv for chinese, korean and japanese
translations of the game (we need to convert their dialog.tlk).

