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
      <td style="text-align: left">GemRB demo</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chartreuse;">yes</td>
      <td style="background: chocolate;">no</td>
      <td><a href="https://github.com/gemrb/gemrb/labels/game%3A%20demo">demo</a></td>
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

PST is completable, but has some notable missing features, making it the least polished game.
IWD2 is playable quite nicely up until the Volcano time loop. Both still require [a lot more
love]({{ site.contribute }}) to reach the level of the other games.

The GemRB demo is bundled with GemRB, so it can be ran immediately.

Multiplayer is **not** supported.

If you can't wait to see what improvements the next release will bring, a terse overview of what
has already been done is in the [changelog in the making](https://github.com/gemrb/gemrb/blob/master/NEWS),
updated approximately every 100 changes.

# Wide screen, higher resolutions

The original games only supported a fixed list of resolutions through their data, with the
widescreen mod enabling more choice. GemRB on the other hand supports whole-window scaling (resize the window to see),
which in effect produces larger pixels and looks best at integer multiples of the base
resolution (eg. 3x bigger). GemRB also supports arbitrary resolutions without the widescreen
mod, but in that case the GUIs will remain the same size, only centered.

Setup        | Resolution | Pixel scaling | Requires mod
-------------|------------|---------------|-------------
Originals    | [Fixed](https://github.com/gemrb/gemrb/blob/master/gemrb/GemRB.cfg.sample.in#L64-L70)      | no       | no
GemRB 0.8.7  | Fixed      | optional | no
GemRB 0.9.0+ | Arbitrary  | optional | no
Widescreen   | Arbitrary  | no       | yes

So feel free to run at any resolution and if you're discontent with the GUI, consider
installing the widescreen mod and bigger fonts.

If you're using scaling, you can change the type of interpolation used with the `ScaleQuality` configuration
key. It defaults to "best", but if you want a sharper image, "nearest" is a better choice.

Confused? Watch [this video explainer](https://youtu.be/nn1v-yG4-lo).
{: .notice--warning}

