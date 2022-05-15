## CustomTkinter: Ctk

### About
CustomTkinter is a python UI-library based on Tkinter, which provides new, modern and fully customizable widgets. They are created and used like normal Tkinter widgets and can also be used in combination with normal Tkinter elements. The widgets
and the window colors either adapt to the system appearance or the manually set mode ('light', 'dark'). With CustomTkinter you'll get a consistent and modern look across all desktop platforms (Windows, macOS, Linux).

This is the unofficial **CustomTkinter** documentation, where you can find detailed information on all available widgets and some more information on how the themes and the appearance mode works.

### Architecture

Under the hood CustomTkinter library, or Ctk, implements its widgets using Tkinter Canvas Widget to positionate and arange its custom ui elements.
Almost all widgets are children of the CtkBaseClass. This shared behaviour is needed to allow the class CTkDrawEngine to correctly render each component. As it's written inside the file ctk_draw_engine.py, CtkDrawEngine is the object offering the core functionallity of CustomTkinter library.  It is the part of the library responsible for drawing everything.
Before, we told you that not all the widgets descent from  CtkBaseClass, the exception is the class CtkCanvas, which is a modified child of tkinter.Canvas class and it's used inside each Ctk widget.

![Project Classes](/assets/classes.png)

![Project Packages](/assets/packages.png)



### Available Widgets

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


