## CTkFrame

#### Example Code:
```python
frame = customtkinter.CTkFrame(master=root_tk,
                               width=200,
                               height=200,
                               corner_radius=10)
frame.pack(padx=20, pady=20, sticky="nsew")
```

#### Arguments:

argument | value
--- | ---
master | root, Frame or Toplevel
width | slider width in px
height | slider height in px
border_width | width of border in px
fg_color | foreground color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color
border_color | border color, tuple: (light_color, dark_color) or single color

and all arguments of `tkinter.Frame`

#### Methods:
```python
frame.configure(fg_color=..., bg_color=..., corner_radius=...)
```
and all methods of `tkinter.Frame`