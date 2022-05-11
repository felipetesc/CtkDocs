## About
This is the official **CustomTkinter** documentation, where you can find detailed information on all available widgets and some more information on how the themes and the appearance mode works.

Under the hood CustomTkinter library, or Ctk, implements its widgets using Tkinter Canvas Widget to positionate and arange its custom ui elements.
Almost all widgets are children of the CtkBaseClass. This shared behaviour is needed to allow the class CTkDrawEngine to correctly render each component. As it's written inside the file ctk_draw_engine.py, CtkDrawEngine is the object offering the core functionallity of CustomTkinter library.  It is the part of the library responsible for drawing everything
Before, we told you that not all the widgets descent from  CtkBaseClass, the exception is the class CtkCanvas, which is a modified child of tkinter.Canvas class and it's used inside each Ctk widget.


## Available Widgets

Each ui component is structured as class, and as told before, all widgets have a common parent, the class CtkBaseClass. Today, the library offers the following widgets:

- CtkButton
- CtkCanvas
- CtkCheckBox
- CtkEntry
- CtkFrame
- CtkLabel
- CtkProgressbar
- CtkRadioButton
- CtkSlider
- CtkSwitch


## Contribution
You can contribute in several ways:
- open a new issue tracker for a new bug
- help to fix bugs
- creating new themes
- creating  new widgets
- creating tests (performance, security, unit tests)
- sharing projects using CustomTkinter
- writing documentation
- requesting new widgets
- spreading the word about CustomTkinter
- adding new functionality
- improving code performance


Before we mentioned that every widget extends the class

## Questions and Bugs ?

Feel free to ask questions in the [Issues tab](https://github.com/TomSchimansky/CustomTkinter/issues) when something is unclear, or if you have ideas on improvements or requests for new widgets.
