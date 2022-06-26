
### Change Theme

If you want to change the appereance mode on-the-fly:

##### Preview
![Project Packages](/assets/change_theme.gif)

##### Code

```python

import tkinter
import customtkinter

DARK_MODE = "dark"
customtkinter.set_appearance_mode(DARK_MODE)
customtkinter.set_default_color_theme("blue")


class App(customtkinter.CTk):

    color = "dark"

    def toggle_color(self):

        if App.color == "dark":
            App.color = "light"
            return "light"
        else:
            App.color = "dark"
            return "dark"

    def alter_theme(self):
        self.color = self.toggle_color()
        customtkinter.set_appearance_mode(self.color)

    def __init__(self):
        super().__init__()
        # self.state('withdraw')
        self.title("Change Theme")

        self.geometry("800x600")
        bt = customtkinter.CTkButton(self, width=100, height=50, text="Click", command=self.alter_theme)
        bt.place(anchor="center", relx="0.5", rely="0.5")


a = App()
a.mainloop()

```