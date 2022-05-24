### Resize Window

If you want to change the window size on-the-fly:


##### Preview

![Project Packages](/assets/resize_window.gif)


##### Code

```python

import tkinter
import customtkinter


class App(customtkinter.CTk):

    def alter_size(self):
        if self.is_max is True:
            new_val = str(self.half_geometry[0]) + "x" + str(self.half_geometry[1])
            self.geometry(new_val)
            self.is_max = False
        else:
            new_val = str(self.max_geometry[0]) + "x" + str(self.max_geometry[1])
            self.geometry(new_val)
            self.is_max = True

    def __init__(self):
        super().__init__()
        self.is_max = False
        self.max_geometry = [self.winfo_screenwidth(), self.winfo_screenheight()]
        self.half_geometry = [int(self.winfo_screenwidth()/2), int(self.winfo_screenheight()/2)]

        self.title("fullscreen")
        start_half = str(self.half_geometry[0]) + "x" + str(self.half_geometry[1])

        self.geometry(start_half)

        bt = customtkinter.CTkButton(self, width=100, height=50, text="Click", command=self.alter_size)
        bt.place(anchor="center", relx="0.5", rely="0.5")


a = App()
a.mainloop()

```