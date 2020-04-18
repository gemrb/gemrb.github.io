---
title: GUI structure
---

CHU files are refered to as "window packs" in GemRB, since that is what
they do. Some are available in several variants for different resolutions.
The windows then contain their own controls to function.

## Controls

Each control has an associated 'Value' which could be assigned to it by
the [SetVarAssoc](/functions/SetVarAssoc) command. The controls handle
this value according to their type and subtype. To set a button's subtype,
use the [Button_SetFlags](functions/Button_SetFlags) command.

See also: [SetVar](/functions/SetVar), [GetVar](/functions/GetVar),
[QueryText](/QueryText).

### Button

Buttons are the most versatile controls in the GUI engine. The following
button types exist: checkbox, radiobutton and normal button. Checkboxes
of the same type are cumulative, and usually hold a bit value.
Radiobuttons of the same type are mutually exclusive. Normal buttons are
similar to radiobuttons, but they are not affecting each other.

**Normal button:** the associated variable will be set to the 'Value',
other controls are unaffected.

**CheckBox:** the associated variable will be or-ed with the value,
other controls may change accordingly to the new value.

**RadioButton:** the associated variable will be set to the 'Value',
other controls are changed accordingly to the new value.

### Progressbar

This control has no equivalent in the original Infinity Engine. It
provides a graphical output of a numeric value, currently used only in
LoadScreen.

**Progressbar:** the progressbar will handle Value as a percentage (it
can't alter the value).

### Slider

A slider is used for limited numeric input.

**Slider:** the slider will handle Value as a scaling factor (not the
actual position\!), it will set the associated Variable to
Position\*Value.

### TextEdit

This is a text input field. It has a configurable maximum input length.

**TextEdit:** cannot be associated with a variable. You have to use
QueryText()

### TextArea

Textareas are used in two ways, primarily for massive text output, 
potentially colour coded and with status icons. Textareas are also
used to simulate list controls where you could select a line and
receive the row number of the selected item. It is also possible to
assign a specific value to each row.

**TextArea:** cannot be associated with a variable, use the various
TextArea commands.

### Label

A label is simply a static text control, but it defines a few mouse
events. Not so complex as a button.

**Label:** labels work like a normal button, the Value will be assigned
to the associated variable when the label was 'pushed'. No reason to
use this though.

### Scrollbar

A scrollbar is mostly used in connection with a Textarea, but it could
be used differently. (See GUILOAD as an example).

**ScrollBar:** Value will be set based on the scrollbar's knob position.
The scrollbar will be redrawn based on Value. If a textarea was
associated to the ScrollBar (via the .chu) then the textarea will also
be scrolled.

### Worldmap

This control has a button type placeholder in the original user
interface files. The current GemRB chui loader can't handle this type,
so you must create it via a CreateWorldMapControl command.

**WorldMapControl:** whether travel allowed or not (change the cursor)

### Map

This control has a button type placeholder in the original user
interface files. The current GemRB chui loader can't handle this type,
so you must create it via a CreateMapControl command.

**MapControl:** the mapcontrol will use the first bit of the associated
value to display mapnotes.

### Game

This control has no equivalent in the original user interface files. It
covers the main game area where the actors are placed. The engine
enforces that the game control is always the first control of the first
window. To achieve this, it will close all windows when entering the
game.

## Accessing GUI controls

To access a GUI control, you must know its window ID and control ID (CHU index).
You must use `LoadWindow` and `GetControl` to obtain a reference to the control.
Inspect the relevant CHU file to find all the control IDs.

Many GUI commands works only on one type of control. A wrong control type will
cause a Runtime Error and terminates the GUI script (not the game or the engine).

Setup example:
```python
StartWindow = GemRB.LoadWindow (7)
Label = StartWindow.GetControl (0x0fff0000)
Label.SetText (23445)
```

In the above example we load a window whose window ID is 7 and its child control
with ID 0xfff0000. Finally, we use a string reference (strref) to set the
control's text. These are references to dialog.tlk, which holds all the ingame
strings. Always use strrefs or you will break translations!

## Data exchange examples

```python
# GUILOAD.py snippet
Progress = 0
GemRB.SetVar ("Progress", Progress)
Bar = LoadScreen. GetControl (0)
Bar.SetVarAssoc ("Progress", Progress)
```

Bar is a ProgressBar control, the engine will refresh the "Progress"
Global Dictionary Variable as it progresses with the EnterGame command.

```python
THac0RollsB.SetFlags (IE_GUI_BUTTON_CHECKBOX, OP_OR)
THac0RollsB.SetVarAssoc ("Rolls", 1)
```

The above commands (from the options screen) will change the "Rolls"
variable according to the CheckBox' state.

```python
BppButtonB1 = GraphicsWindow.GetControl (5)
BppButtonB2 = GraphicsWindow.GetControl (6)
BppButtonB3 = GraphicsWindow.GetControl (7)
BppButtonB1.SetFlags (IE_GUI_BUTTON_RADIOBUTTON, OP_OR)
BppButtonB2.SetFlags (IE_GUI_BUTTON_RADIOBUTTON, OP_OR)
BppButtonB3.SetFlags (IE_GUI_BUTTON_RADIOBUTTON, OP_OR)
BppButtonB1.SetVarAssoc ("BitsPerPixel", 16)
BppButtonB2.SetVarAssoc ("BitsPerPixel", 24)
BppButtonB3.SetVarAssoc ("BitsPerPixel", 32)
```

The above commands will set up the BPP selection RadioButton group.
