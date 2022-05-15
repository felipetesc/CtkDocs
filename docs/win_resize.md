### Change Theme


```python

import tkinter
import customtkinter  # <- import the CustomTkinter module
from functools import partial


DARK_MODE = "dark"
customtkinter.set_appearance_mode(DARK_MODE)
customtkinter.set_default_color_theme("blue")

class App(customtkinter.CTk):
    color = "dark"
    def __init__():
        super().__init__()

    def toggle_color(self):

        if App.color == "dark":
            App.color = "light"
            return "light"
        else:
            App.color = "dark"
            return "dark"

    def alter_color(self):
        self.color = self.toggle_color()
        customtkinter.set_appearance_mode(self.color)

    def __init__(self):
        super().__init__()
        # self.state('withdraw')
        self.title("fullscreen")
        WIDTH = self.winfo_screenwidth()
        print("Width: " + str(WIDTH))
        HEIGHT = self.winfo_screenheight()
        print("Height: " + str(HEIGHT))
        X_POS = self.winfo_x()
        print("X_POS: " + str(X_POS))
        Y_POS = self.winfo_y()
        print("Y_POS: " + str(Y_POS))
        # self.myfont = font.Font(family="Courier", size=14)
        self.geometry(f"{WIDTH}x{HEIGHT}+{X_POS}+{Y_POS}")
        bt = customtkinter.CTkButton(self, width=100, height=50, text="Click", command=self.alter_color)
        bt.place(anchor="center", relx="0.5", rely="0.5")


a = App()
a.mainloop()

```