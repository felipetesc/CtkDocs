## CTkRadioButton


This CTkRadioButton works similar to the `tkinter.Radiobutton`.

### Example Code:
Default theme:
```python
radio_var = tkinter.IntVar(0)

def radiobutton_event():
    print("radiobutton toggled, current value:", radio_var.get())

radiobutton_1 = customtkinter.CTkRadioButton(master=root_tk, text="CTkRadioButton 1",
                                             command=radiobutton_event, variable= radio_var, value=1)
radiobutton_2 = customtkinter.CTkRadioButton(master=root_tk, text="CTkRadioButton 2",
                                             command=radiobutton_event, variable= radio_var, value=1)

radiobutton_1.pack(padx=20, pady=10)
radiobutton_2.pack(padx=20, pady=10)
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
border_width_unchecked | border width in unchecked state in px
border_width_checked | border width in checked state in px
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
value | string or int value for variable when RadioButton is clicked

#### Methods:
```python
radiobutton.invoke()  # simulate user click
radiobutton.select()  # turns on checkbox
radiobutton.deselect()  # turns off checkbox

radiobutton.configure(text=new_text)
radiobutton.configure(fg_color=new_fg_color,
                      hover_color=new_hover_color,
                      text_color=new_text_color)
radiobutton.configure(state=tkinter.DISABLED)
radiobutton.configure(state=tkinter.NORMAL)
radiobutton_state = radiobutton.state
```