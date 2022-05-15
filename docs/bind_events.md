## Bind Event Frame

If you want to use bind from tkinter:

```python

import tkinter as Lib
import customtkinter as CtkLib

CtkLib.set_appearance_mode("dark")


def callback():
   label = CtkLib.CTkLabel(app, text="Hello World!")
   label.pack(pady=0)


app = CtkLib.CTk()

app.title('Title')

app.geometry("400x300")

panel = CtkLib.CTkFrame(master=app, width=120, height=50)

panel.place(relx=0.15, rely=0.5, anchor=Lib.CENTER)

bt = CtkLib.CTkButton(master=panel, text="left button", command= callback, width=70)

bt.place(relx=0.5, rely=0.5, anchor=Lib.CENTER)

app.bind('<Button-1>', lambda event: callback())

app.mainloop()


```


```python
from tkinter import *
import customtkinter

def Click(event=None):
    print(slider_1.get())

root = customtkinter.CTk()

customtkinter.set_appearance_mode("Dark")  # Modes: "System" (standard), "Dark", "Light"
customtkinter.set_default_color_theme("blue")  # Themes: "blue" (standard), "green", "dark-blue"

frame_right = customtkinter.CTkFrame(master=root)
frame_right.grid(row=0, column=1, sticky="nswe", padx=20, pady=20)

slider_1 = customtkinter.CTkSlider(master=frame_right, from_=0, to=1)
slider_1.grid(row=0, column=0, columnspan=2, pady=10, padx=20, sticky="we")

slider_1.bind('<Button-1>', Click)
root.mainloop()
```