## CtkButton


#### Example Code:
Default theme:
```python
def button_event():
    print("button pressed")

button = customtkinter.CTkButton(master=root_tk, text="CTkButton", command=button_event)
button.pack(padx=20, pady=10)
```

Customized:
```python
button = customtkinter.CTkButton(master=root_tk,
                                 width=120,
                                 height=32,
                                 border_width=0,
                                 corner_radius=8,
                                 text="CTkButton",
                                 command=button_event)
button.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)
```


#### Arguments:

argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
command | callback function
textvariable | tkinter.StringVar object to change text of button
text | string
width | button width in px
height | button height in px
corner_radius | corner radius in px
border_width | button border width in px
fg_color | forground color, tuple: (light_color, dark_color) or single color
bg_color | background color, tuple: (light_color, dark_color) or single color
border_color | border color, tuple: (light_color, dark_color) or single color
hover_color | hover color, tuple: (light_color, dark_color) or single color
text_color | text color, tuple: (light_color, dark_color) or single color
text_color_disabled | text color when disabled, tuple: (light_color, dark_color) or single color
text_font | button text font, tuple: (font_name, size), (set negative size value for size in pixels)
hover | enable/disable hover effect: True, False
image | put an image on the button, removes the text, must be class PhotoImage
compound | set image orientation if image and text are given ("top", "left", "bottom", "right")
state | tkinter.NORMAL (standard) or tkinter.DISABLED (not clickable, darker color)

#### Methods:

```python
CTkButton.set_text(new_text)
CTkButton.set_image(new_image)
CTkButton.configure(text=new_text)
CTkButton.configure(bg_color=new_bg_color,
                    fg_color=new_fg_color,
                    hover_color=new_hover_color,
                    text_color=new_text_color)
CTkButton.configure(state=tkinter.DISABLED)
CTkButton.configure(state=tkinter.NORMAL)
button_state = CTkButton.state
```
