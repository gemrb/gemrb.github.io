---
title: External font support
toc: true
---

## About Fonts in GemRB

Fonts in GemRB (as well as original IE games), aren't fonts in the
traditional sense. The fonts are actually a simple sprite with each
glyph rendered in order (ie A-Z). Image resources for these sprites are
stored in IE BAM files. Implications of this method are:

1.  Fonts are fixed size
2.  Fonts take more memory the more characters they contain
3.  Fonts take more memory the larger they are
4.  Fonts cannot effectively be manipulated after creation (aside from
    changing the color palette)
5.  You are stuck using the fonts included with the game or modding your
    own (meaning no extra characters)
6.  Fonts cannot be kerned etc. (TTF fonts support basic kerning)

## TL;DR replacing fonts in GemRB

1.  **Choose** the desired fonts and which ingame fonts they should
    replace.
2.  **Copy** them to the **game override** folder or point the
    **CustomFontPath** GemRB config option to them.
3.  Edit the **FONT_NAME** column in
    gemrb/**unhardcoded/your-game-type/fonts.2da** to contain your new
    font names. Don't include file extensions. The RESREF column says
    which ingame bitmap font each line is for.
4.  Change also PT_SIZE if you want the fonts to be bigger.
5.  **Run** GemRB and enjoy.
6.  Return to point 3. if you mapped the fonts to the wrong ingame
    counterpart or want to change something else.

## TrueType Fonts in GemRB

Technically TrueType fonts aren't limited in the same ways as "BAM"
fonts. However, in order to support most of what TTF is capable of an
that is important without having to write a new font renderer/breaking
BAM support, TTF fonts in GemRB are done as Sprites in the same manner
as the original fonts. What this means is that while the fonts are
static once created we can supply parameters at engine start to create
them in any size and any style supported by *any* TTF font you have
available.

The TTF plugin for GemRB requires these libraries:

  - [FreeType](http://www.freetype.org/)
  - [iconv](http://www.gnu.org/software/libiconv/) (only needed if using
    a non unicode compatible dialog.tlk)

## fonts.2da

Inside GemRB's *"unhardcoded"* folder there are subfolders for each game
type which contain fonts.2da files for each game. These files tell GemRB
how to construct fonts for a given *"resref"*.

``` 
2DA V1.0
NORMAL
  RESREF      NEED_PALETTE   FONT_NAME   PT_SIZE  STYLE   COLOR
0 NORMAL      1              NORMAL      14       0       0xffffffff 
1 INFOFONT    1              INFOFONT    14       0       0xffffffff
2 NUMBER      0              NUMBER      14       0       0xffffffff 
3 INITIALS    0              INITIALS    14       0       0xffffffff
4 NUMBER2     0              NUMBER2     14       0       0xffffffff 
5 NUMBER3     0              NUMBER3     14       0       0xffffffff
6 NUMFONT     1              NUMFONT     14       0       0xffffffff 
7 REALMS      0              REALMS      14       0       0xffffffff 
8 REALMS2     1              REALMS2     14       0       0xffffffff 
9 STONEBIG    0              STONEBIG    14       0       0xffffffff
10 STONESM2   0              STONESM2    14       0       0xffffffff 
11 STONESM3   0              STONESM3    14       0       0xffffffff 
12 STONESML   0              STONESML    14       0       0xffffffff 
13 TOOLFONT   1              TOOLFONT    14       0       0xffffffff
14 STATES     0              STATES      14       0       0xffffffff 
15 STATES2    0              STATES2     14       0       0xffffffff
```

The columns: *FONT\_NAME*, *PT\_SIZE*, and *STYLE* are for TTF
fonts only. *FONT\_NAME* is the file name (*NOT* the path) of the TTF
font you wish to use, and *PT\_SIZE* controls the size of the font.
*STYLE* controls the font style and accepts the following values:

  - 0=NORMAL
  - 1=BOLD
  - 2=ITALIC
  - 3=UNDERLINE

*COLOR* is the RGBA hexadecimal color to use to create the color
palette. It applies to BAM fonts only if *NEED\_PALETTE* is set. It
applies to TTF fonts regardless of the value of *NEED\_PALETTE*.

If you want to see an example using TTF fonts, check the [demo file](https://github.com/gemrb/gemrb/blob/master/demo/data/fonts.2da)

## GemRB config

In GemRB.cfg **you must specify** the following option (or copy the
fonts to GamePath/override):

  - CustomFontPath is a string indicating the absolute path of the
    directory containing the non-BAM font files you wish to use.
    *FONT\_NAME* must match a file name in this directory (without
    extension and may be case sensitive).

You may mix and match BAM and TTF fonts however you like.
