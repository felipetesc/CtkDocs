## CTkSlider

#### Example Code:
Default theme:
```python
def slider_event(value):
    print(value)

slider = customtkinter.CTkSlider(master=root_tk, from_=0, to=100, command=slider_event)
slider.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)
```

#### Arguments:

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
command | callback function, gest called when slider gets changed
variable | tkinter.IntVar or tkinter.DoubleVar object
width | slider width in px
height | slider height in px
border_width | space around the slider rail in px
from_ | lower slider value
to | upper slider value
number_of_steps | number of steps in which the slider can be positioned
fg_color | foreground color, tuple: (light_color, dark_color) or single color
progress_color | tuple: (light_color, dark_color) or single color, color of the slider line before the button
bg_color | background color, tuple: (light_color, dark_color) or single color
border_color | slider border color, normally transparent (None)
button_color | color of the slider button, tuple: (light_color, dark_color) or single color
button_hover_color | hover color, tuple: (light_color, dark_color) or single color

#### Methods:
```python
CTkSlider.configure(fg_color=...,
                    progress_color=...,
                    button_color=...,
                    button_hover_color=...,
                    border_color=...)

CTkSlider.configure(border_width=...,
                    from_=...,
                    to=...,
                    number_of_steps=...,
                    command=...,
                    variable=...)

value = CTkSlider.get()
CTkSlider.set(value)
```

</details>