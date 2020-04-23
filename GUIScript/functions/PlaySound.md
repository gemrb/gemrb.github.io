---
title: PlaySound
module: GemRB
layout: gs-function
---

**Prototype:** GemRB.PlaySound (SoundResource[, channel, xpos, ypos, type])
**Prototype:** GemRB.PlaySound (DefSoundIndex[, channel])
**Prototype:** GemRB.PlaySound (None)

**Description:** Plays a sound identified by resource reference or 
defsound.2da index. If there is a single PC selected, then it will play the 
sound as if it was said by that PC (EAX).

**Parameters:**
  * SoundResource - a sound resref (the format could be raw pcm, wavc or  ogg; 8/16 bit; mono/stereo). Use the None python object to simply stop the previous sound.
  * channel - the name of the channel the sound should be played on (optional, defaults to 
