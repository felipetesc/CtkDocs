## CTkEntry

#### Example Code:
Default theme:
```python
entry = customtkinter.CTkEntry(master=root_tk, placeholder_text="CTkEntry")
entry.pack(padx=20, pady=10)
```

Customized:
```python
entry = customtkinter.CTkEntry(master=root_tk,
                               placeholder_text="CTkEntry",
                               width=120,
                               height=25,
                               border_width=2
                               corner_radius=10)
entry.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)
```

#### Arguments

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
variable | tkinter.StringVar object
width | entry width in px
height | entry height in px
corner_radius | corner radius in px
fg_color | foreground color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color
text_color | entry text color, tuple: (light_color, dark_color) or single color
placeholder_text_color | tuple: (light_color, dark_color) or single color
placeholder_text | hint on the entry input (disappears when selected), default is None
text_font | entry text font, tuple: (font_name, size)

and all arguments if `tkinter.Entry`

#### Methods:

```python
CTkEntry.delete(...)  # like the standard tkinter Entry...
CTkEntry.insert(...)
CTkEntry.configure(fg_color=..., text_color=..., corner_radius=...)
text = CTkEntry.get()
```
and all methods if `tkinter.Entry`