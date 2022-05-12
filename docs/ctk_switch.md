## CTkSwitch

The switch should behave similar to the CTkCheckBox.

#### Example Code:
Default theme:
```python
switch_var = tkinter.StringVar("on")

def switch_event():
    print("switch toggled, current value:", switch_1.get())

switch_1 = customtkinter.CTkSwitch(master=root_tk, text="CTkSwitch", command=switch_event,
                                   variable= switch_var, onvalue="on", offvalue="off")
switch_1.pack(padx=20, pady=10)
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
border_color | border color, tuple: (light_color, dark_color) or single color, default is None
button_color | color of button, tuple: (light_color, dark_color) or single color
button_hover_color | hover color of button, tuple: (light_color, dark_color) or single color
hover_color | hover color, tuple: (light_color, dark_color) or single color
text_color | text color, tuple: (light_color, dark_color) or single color
text_font | button text font, tuple: (font_name, size)
command | function will be called when the checkbox is clicked 
variable | Tkinter variable to control or read checkbox state
onvalue | string or int for variable in checked state
offvalue | string or int for variable in unchecked state

#### Methods:
```python
switch_1.get()  # 1 or 0 (checked or not checked)
switch_1.select()  # turns on switch
switch_1.deselect()  # turns off switch
switch_1.toggle()  # change check state of switch
switch_1.configure(text=new_text)
switch_1.configure(fg_color=...,
                   progress_color=...,
                   button_color=...,
                   button_hover_color=...,
                   border_color=...,
                   border_width=...)
switch_1.configure(command=new_command)
```