---
title: Features
classes: wide
---

GemRB is a portable open-source implementation of Bioware's 8 [Infinity Engine versions](History.md).

  - Runs the Baldur's Gate, Icewind Dale and Planescape: Torment games, their expansions
    and [mods](Modding.md)
  - [Cross-platform](Supported-platforms.md): runs on Windows, OS X, Linux,
    \*BSD, Android, iOS and [more](https://gemrb.github.io/Media#exotic-platforms)
  - Free Libre Open Source Software, available under the [GPL](https://github.com/gemrb/gemrb/blob/master/COPYING)
  - Nearly feature-complete ([TODO](https://github.com/gemrb/gemrb/issues?q=is%3Aopen+is%3Aissue+label%3Afeature))
  - Usability [innovations](Innovations.md), including touch based input and scaling
  - Extensible plugin-based design that removes many limitations of the
    Infinity Engine
  - Increased [moddability](Modding.md) over the originals

Not convinced? Check out some **[screenshots](Media.md)** and **[videos](Media.md#videos)**
or perhaps the [FAQ](FAQ.md).

# Status

<table style="text-align: center">
  <thead>
    <tr>
      <th>Game</th>
      <th>Playable</th>
      <th>Completable</th>
      <th>Polished</th>
      <th style="text-align: center">TODOs</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align: left">Baldur’s Gate 1</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20bg1">bg1</a></td>
    </tr>
    <tr>
      <td style="text-align: left">Planescape: Torment</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chocolate;">no</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20pst">pst</a></td>
    </tr>
    <tr>
      <td style="text-align: left">Icewind Dale  1</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20iwd1">iwd1</a></td>
    </tr>
    <tr>
      <td style="text-align: left">Baldur’s Gate 2</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20bg2">bg2</a></td>
    </tr>
    <tr>
      <td style="text-align: left">Icewind Dale  2</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chocolate;">no</td>
      <td style="background: chocolate;">no</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20iwd2">iwd2</a></td>
    </tr>
    <tr>
      <td style="text-align: left">New game</td>
      <td style="background: chocolate;">no</td>
      <td style="background: chocolate;">no</td>
      <td style="background: chocolate;">no</td>
      <td><a href="/New-game.html">New game</a></td>
    </tr>
    <tr>
      <td style="text-align: left">Any Enhanced Edition</td>
      <td style="background: chocolate;">no</td>
      <td style="background: chocolate;">no</td>
      <td style="background: chocolate;">no</td>
      <td><a href="https://github.com/gemrb/gemrb/issues/164">EE</a></td>
    </tr>
  </tbody>
</table>

{% comment %}
can't style markdown as well as raw html
Game | Playable | Completable | Polished | TODOs
---- | -------- | ----------- | -------- | ------
Baldur's Gate 1 | yes | yes | yes | [bg1](https://github.com/gemrb/gemrb/labels/game%3A%20bg1)
Planescape: Torment | yes | yes | no | [pst](https://github.com/gemrb/gemrb/labels/game%3A%20pst)
Icewind Dale  1 | yes | yes | yes | [iwd1](https://github.com/gemrb/gemrb/labels/game%3A%20iwd1)
Baldur's Gate 2 | yes | yes | yes | [bg2](https://github.com/gemrb/gemrb/labels/game%3A%20bg2)
Icewind Dale  2 | yes | no | no | [iwd2](https://github.com/gemrb/gemrb/labels/game%3A%20iwd2)
New game        | no | no | no | [New game](New-game.md)
Any Enhanced Edition | no | no | no | [EE](https://github.com/gemrb/gemrb/issues/164)
{% endcomment %}

PST is completable, but has some notable missing features, making it the least polished game.
IWD2 is playable quite nicely up until the Ice Temple. Both still require [a lot more
love](https://github.com/gemrb/gemrb/blob/master/CONTRIBUTING.md) to reach the level of the
other games.

There is also a [tiny tech
demo](https://github.com/gemrb/gemrb/tree/master/demo) bundled with GemRB,
but it requires more content to be more than a simple test case.

If you can't wait to see what improvements the next release will bring, a terse overview of what
has already been done is in the [changelog in the making](https://github.com/gemrb/gemrb/blob/master/NEWS),
updated approximately every 100 changes.
