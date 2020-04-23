---
title: Button_SetPicture
module: _GemRB
layout: gs-function
---

**Prototype:** GemRB.SetButtonPicture (WindowIndex, ControlIndex, PictureResRef, DefaultResRef)

**Metaclass Prototype:** SetPicture (PictureResRef, DefaultResRef)

**Description:** Sets the Picture of a Button Control from a BMP file.

**Parameters:**
  * WindowIndex, ControlIndex - the control's reference
  * PictureResRef - the name of the picture (a .bmp resref)
  * DefaultResRef - an alternate bmp should the picture be nonexistent

**Return value:** N/A

**See also:** [Button_SetBAM](Button_SetBAM.md), [Button_SetPLT](Button_SetPLT.md), [Button_SetSprites](Button_SetSprites.md), [Button_SetPictureClipping](Button_SetPictureClipping.md), [Window_SetPicture](Window_SetPicture.md)
