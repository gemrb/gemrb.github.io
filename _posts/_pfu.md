---
title: Upcoming major pathfinding improvements
author: Jaka Kranjc
skew:
  - url: assets/img/news/fig4_movement_trajectory.webp
    image_path: assets/img/news/fig4_movement_trajectory.webp
    alt: "Skew illustration 1"
    title: "Skew on a short path."
  - url: assets/img/news/fig6_bend.webp
    image_path: assets/img/news/fig6_bend.webp
    alt: "Skew illustration 2"
    title: "Skew range."
  - url: assets/img/news/fig7_bend_leaves_corridor.webp
    image_path: assets/img/news/fig7_bend_leaves_corridor.webp
    alt: "Skew illustration 3"
    title: "Skew causing path abandonment."
  - url: assets/img/news/fig8_curved_paths.webp
    image_path: assets/img/news/fig8_curved_paths.webp
    alt: "Skew illustration 4"
    title: "Skew examples."
multithreaded:
  - url: assets/img/news/baseline.immediate.queued.png.webp
    image_path: assets/img/news/baseline.immediate.queued.png.webp
    alt: "Multithreaded performance 4"
    title: "Mode comparison"
- url: assets/img/news/max.frame.time.png.webp
    image_path: assets/img/news/max.frame.time.png.webp
    alt: "Multithreaded performance 1"
    title: "Maximum frame time comparison."
  - url: assets/img/news/frame.pacing.case3.png.webp
    image_path: assets/img/news/frame.pacing.case3.png.webp
    alt: "Multithreaded performance 2"
    title: "Frame pacing comparison."
  - url: assets/img/news/baseline.immediate.queued.frame.pacing.png.webp
    image_path: assets/img/news/baseline.immediate.queued.frame.pacing.png.webp
    alt: "Multithreaded performance 3"
    title: "Frame pacing comparison by mode."
  - url: assets/img/news/thread.scaling.png.webp
    image_path: assets/img/news/thread.scaling.png.webp
    alt: "Multithreaded performance 5"
    title: "Thread scaling comparison."
---

The next release will bring several landmark upgrades to pathfinding and movement, all due to meticulous work
and documentation by Dariusz Pyś. Let's take a closer look at the more interesting bits. All the images were created by Dariusz.

## Multithreaded pathfinding

GemRB prides itself on running on a vast array of hardware and software [platforms](Supported-platforms.md).
But your machine didn't have to be an old resource starved potato for it to sometimes buckle under the worst
pathfinding requests. Since the algorithm ran on the main thread that meant the engine would block any
interactivity while waiting, the drawing would skip frames and users would have a bad time.

With the introduction of multithreaded pathfinding this problem is now gone. The number of threads is
configurable and can even be disabled. In that case either an immediate (like before) or a queue system can be chosen. Even the first still slightly improves performance
compared to before. Users don't have to anything to opt-in, as a sane default taking into account their number
of physical cores will be chosen if the settings are not found.

{% include gallery id="multithreaded" layout="third" caption="Performance comparisons." %}

Anyone interested in the details of the implementation should read the [design documentation](https://github.com/gemrb/gemrb/blob/master/gemrb/docs/en/Engine/Multithreaded_pathfinding.md).

## Line of sight / performance

Profiling showed that now that searchmap state is effectively cached, line of sight checks are the next hot path bottleneck.
Our previous pathfinding expert suggested using Bresenham's algorithm might help, but it turns out it would be incorrect
for our use case, skipping checks and hitting walls.

{% include figure popup=true image_path="/assets/img/news/fig9_bresenham_missed_walls.webp" alt="Bresenham vs Wu comparison" caption="Comparing Bresenham vs Wu." %}

Dariusz instead implemented Wu's algorithm, which is both correct and much more performant. While trying to ensure it is
consistently fast with both gcc and clang (default semantic interposition difference), he discovered more points of
optimization...

add perf data
{% include gallery layout="/half/third" caption="" %}
overall (pathfinding, not just LOS) x20 speedup?

## Walking skew removal

Working on optimizing line of sight checks revealed that there is a systematic difference between the path
returned by the pathfinder and what the actors actually walk. This is now fixed.

{% include gallery id="skew" layout="third" caption="Comparison of intended and actual walks. Image 3 shows how disruptive this can be in the worst case examples." %}

## Miscellanea

Last but not least, Dariusz built a framework for testing various details of the pathfinding system.
It complements the limited high level tests we had before, which use the real demo data. This is not so
important for users, but it makes it much easier for us to implement further improvements with a lesser
chance of introducing regressions. It already resulted in a lower path abandonment rate and the fix where
actor bumping could cause impassable wall traversal.

In summary, all this work vastly improved performance and correctness of pathfinding, with the subsequent
actor movement and experience being much nicer.

Brave users can already experience these improvements by using our [development builds](Download.md).
Everyone else should wait for the next release, which is likely to come before the end of the year.
