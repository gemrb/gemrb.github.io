---
title: Upcoming major pathfinding improvements
author: Jaka Kranjc
---

The next release will bring several landmark upgrades to pathfinding and movement, all due to meticulous work
and documentation by Dariusz Pyś. Let's take a closer look at the more interesting bits.

## Multithreaded pathfinding

GemRB prides itself on running on a vast array of hardware and software [platforms](Supported-platforms.md).
But your machine didn't have to be an old resource starved potato for it to sometimes buckle under the worst
pathfinding requests. Since the algorithm ran on the main thread that meant the engine would block any
interactivity while waiting, the drawing would skip frames and users would have a bad time.

With the introduction of multithreaded pathfinding this problem is now gone. The number of threads is
configurable and can even be disabled. In that case a queue system still slightly improves performance
compared to before. Users don't have to anything to opt-in, as a sane default taking into account their number
of physical cores will be chosen if the settings are not found.

add a few charts
add perf data

## Line of sight / performance

Profiling showed that now that searchmap state is effectively cached, line of sight checks are the next hot path bottleneck.
Our previous pathfinding expert suggested using Bresenham's algorithm might help, but it turns out it would be incorrect
for our use case, skipping checks and (hitting walls).

add comparison pic(s)

Dariusz instead implemented Wu's algorithm, which is both correct and much more performant. While trying to ensure it is
consistently fast with both gcc and clang (default semantic interposition difference), he discovered more points of
optimization...

add perf data
overall (pathfinding, not just LOS) x20 speedup?

## Walking skew removal

Working on optimizing line of sight checks revealed that there is a systematic difference between the path
returned by the pathfinder and what the actors actually walk. This is now fixed.

add a few charts

## Miscellanea

Last but not least, Dariusz built a framework for testing various details of the pathfinding system.
It complements the limited high level tests we had before, which use the real demo data. This is not so
important for users, but it makes it much easier for us to implement further improvements with a lesser
chance of introducing regressions. It already resulted in a lower path abandonment rate and the fix where
actor bumping could cause impassable wall traversal. 

In summary, all this work vastly improved performance and correctness of pathfinding, with the subsequent
movement and experience being much nicer.

Brave users can already experience these improvements by using our [development builds](Download.md).
Everyone else should wait for the next release, which is likely to come before the end of the year.
