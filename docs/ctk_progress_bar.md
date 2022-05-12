## CTkProgressBar

#### Example Code:
Default theme:
```python
progressbar = customtkinter.CTkProgressBar(master=root_tk)
progressbar.pack(padx=20, pady=10)
```

#### Arguments:

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
width | slider width in px
height | slider height in px
border_width | border width in px
corner_radius | corner_radius in px
fg_color | foreground color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color
border_color | slider border color, tuple: (light_color, dark_color) or single color
progress_color | progress color, tuple: (light_color, dark_color) or single color

#### Methods:
```Python
progressbar.configure(fg_color=...,
                      border_color=...,
                      progress_color=...,
                      border_witdh=...,
                      variable=...)

progressbar.set(value)
```