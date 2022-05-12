## CTkLabel

#### Example Code:
Default theme:
```python
label = customtkinter.CTkLabel(master=root_tk, text="CTkLabel")
label.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)
```

Customized:
```python
text_var = tkinter.StringVar(value="CTkLabel")

label = customtkinter.CTkLabel(master=root_tk,
                               variable=text_var,
                               width=120,
                               height=25,
                               fg_color=("white", "gray75"),
                               corner_radius=8)
label.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)
```

#### Arguments:

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
variable | tkinter.StringVar object
text | string
width | label width in px
height | label height in px
corner_radius | corner radius in px
fg_color | foreground color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color, default is None
text_color | label text color, tuple: (light_color, dark_color) or single color
text_font | label text font, tuple: (font_name, size)

and many arguments of `tkinter.Label`

#### Methods:

```python
CTkLabel.configure(text=new_text)
CTkLabel.configure(fg_color=new_fg_color,
                   bg_color=new_bg_color,
                   text_color=new_text_color)
```
and many methods of `tkinter.Label