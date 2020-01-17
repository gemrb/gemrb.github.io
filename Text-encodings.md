---
title: Text enconding support
---

## Support for non-ASCII (multibyte) languages

If you have a multibyte encoded `dialog.tlk` you will have to add the
Encoding setting to your gemrb.cfg. Set Encoding = to your language and
make sure that an ini file matching your language exists under
*unhardcoded/shared*. If no ini file matching your language exists, one
must be created.

The TTF plugin *must* be either compiled with *iconv* support, or you
must convert your dialog.tlk (see [tlk_convert](https://github.com/gemrb/gemrb/tree/master/tools/tlk_convert))
to UTF-8 to use a non-Unicode compatible dialog.tlk/font.

To create your own *language*.ini, make a new text file like this
(Chinese example):

    [encoding]
    TLKEncoding = GBK

Consult the following sections to learn what encoding
your dialog.tlk is in.

After you have a working *language*.ini, you should be able to play
using either Unicode compatible TTF fonts or the BAM fonts supplied with
your language pack.

In case the original strings are in a different encoding and you want to
use common fonts, you can use `tlk_convert` to convert them to
utf-8 first.

## Language overview

Here is an incomplete overview of known non-English versions of IE games.
This is documentation of what we are facing to support non-ASCII characters
(and other languages in general, but that's more tricky due to IE engine
limitations).

### Czech

Uses CP1250 encoding (1 byte per character). The language uses cases,
genders and other features making a perfect translation impossible with
IE.

### Polish

Polish for BG1 uses an ad-hoc encoding invented by CDProjekt. It's
definitely not any Polish encoding mentioned at
[Wikipedia](http://en.wikipedia.org/wiki/Polish_code_pages).

### Russian

There seem to be at least two different translations of BG1 - one has
strref 15415 "фильмы", the other has "ролики". At least the first one
uses cp1251 encoding, where cyrillic letters have codepoints 192-255,
first uppercase and then lowercase letters. Unlike in our default
encodings, uppercase of code 255 is code 223, not code 159.

### Korean

Korean patch for PS:T uses CP949 encoding, but many strings in the TLK
were left in French. Additionally some of the French strings contain
some garbled characters (possibly Korean again) looking like a haphazard
mix of 2byte and 1byte characters, that is not utf8 :-) )

The PS:T patch consists of

  - Dialog.tlk
  - Torment.exe

### Chinese

BG 1 and 2 Have two different Chinese versions, with unofficial
corrections to them that can all be found at [The Ring Of
Wonder](http://trow.cc)

The BG1 patch uses a custom executable, probably to add double byte
support. It can be found at the site.

BG2 Seems to have this natively, just follow the instructions in the
readme to enable.

Both patches simply replace realms.bam and normal.bam fonts and
dialog.tlk - the other fonts are mapped to one of the aforementioned.

Patch for PS:T uses CP950 (Big5) encoding, that's according to wikipedia
used on Taiwan.

  - cachemos.bif
  - CFONT.DAT, CFONT\[012\].DAT
  - CFONT.TBL
  - CHITIN.KEY
  - CREFiles.bif
  - CS\_0404.bif
  - dialogF.tlk
  - Dialog.tlk
  - GTRSCRN.mos
  - Interface.bif
  - setfont.exe
  - \_Torment.exe

### Japanese

The official BG2:SoA patch uses CP932 (Shift-JIS) encoding. It adds a
possibility to switch alphabets between katakana and hiragana with F3,
probably for the input. It also does some tweaks to improve legibility
that might require code changes. The font is in a BAM file that contains
LOTS of empty positions and in addition to latin characters and Japanese
it contains Russian as well.

  - BGMain.exe
  - override/floattxt.bam
  - override/Realms.bam
  - override/Normal.bam
  - dialogF.tlk
  - dialog.tlk

(It also contains lot of files in override/, but those are bugfixes not
related to Japanese)
