## CTkInputDialog

This is a simple dialog to input a string or number.

#### Example Code:
```python
import customtkinter
import tkinter

customtkinter.set_appearance_mode("dark")

app = customtkinter.CTk()
app.geometry("400x300")


def button_click_event():
    dialog = customtkinter.CTkInputDialog(master=None, text="Type in a number:", title="Test")
    print("Number:", dialog.get_input())


button = customtkinter.CTkButton(app, text="Open Dialog", command=button_click_event)
button.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)

app.mainloop()
```
This example code results in the following window and dialog:

![Bildschirmfoto 2022-03-07 um 22 00 17](https://user-images.githubusercontent.com/66446067/157117053-3f8ae28f-43f8-49a5-aa69-d7ee7214d896.png)

#### Arguments:
argument | value
--- | ---
master | root, tkinter.Frame or CTkFrame
title | string for the dialog title
text | text for the dialog itself
fg_color | fg_color of buttons, tuple: (light_color, dark_color) or single color
hover_color | hover color of buttons, tuple: (light_color, dark_color) or single color
border_color | border color of buttons, tuple: (light_color, dark_color) or single color


#### Methods:
```python
input_value = dialog.get_input()  # opens the dialog
```
