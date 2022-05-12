## CTkCheckBox

#### Example Code:
Default theme:
```python
check_var = tkinter.StringVar("on")

def checkbox_event():
    print("checkbox toggled, current value:", check_var.get())

checkbox = customtkinter.CTkCheckBox(master=root_tk, text="CTkCheckBox", command=checkbox_event,
                                     variable=check_var, onvalue="on", offvalue="off")
checkbox.pack(padx=20, pady=10)
```

#### Arguments:

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
text | string
textvariable | Tkinter StringVar to control the text
width | box width in px
height | box height in px
corner_radius | corner radius in px
border_width | box border width in px
fg_color | foreground (inside) color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color, default is None
border_color | border color, tuple: (light_color, dark_color) or single color
hover_color | hover color, tuple: (light_color, dark_color) or single color
text_color | text color, tuple: (light_color, dark_color) or single color
text_color_disabled | text color when disabled, tuple: (light_color, dark_color) or single color
text_font | button text font, tuple: (font_name, size)
hover | enable/disable hover effect: True, False
state | tkinter.NORMAL (standard) or tkinter.DISABLED (not clickable, darker color)
command | function will be called when the checkbox is clicked 
variable | Tkinter variable to control or read checkbox state
onvalue | string or int for variable in checked state
offvalue | string or int for variable in unchecked state

#### Methods:
```python
CTkCheckBox.get()  # 1 or 0 (checked or not checked)
CTkCheckBox.select()  # turns on checkbox
CTkCheckBox.deselect()  # turns off checkbox
CTkCheckBox.toggle()  # change check state of checkbox
CTkCheckBox.configure(text=new_text)
CTkCheckBox.configure(bg_color=new_bg_color,
                      fg_color=new_fg_color,
                      hover_color=new_hover_color,
                      text_color=new_text_color)
CTkCheckBox.configure(state=tkinter.DISABLED)
CTkCheckBox.configure(state=tkinter.NORMAL)
checkbox_state = CTkCheckBox.state
```