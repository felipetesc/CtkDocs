## CTkToplevel

CTkToplevel works exactly like the `Tkinter.Toplevel`, and should be used to create more than one window.

#### Example Code:
```python
import tkinter
import customtkinter


class ExampleApp(customtkinter.CTk):
    def __init__(self):
        super().__init__()

        self.geometry("500x400")

        self.button = customtkinter.CTkButton(self, text="Create Toplevel", command=self.create_toplevel)
        self.button.pack(side="top", padx=40, pady=40)

    def create_toplevel(self):
        window = customtkinter.CTkToplevel(self)
        window.geometry("400x200")

        # create label on CTkToplevel window
        label = customtkinter.CTkLabel(window, text="CTkToplevel window")
        label.pack(side="top", fill="both", expand=True, padx=40, pady=40)


app = ExampleApp()
app.mainloop()
```
The example code results in the following windows:
![Bildschirmfoto 2022-03-07 um 22 10 29](https://user-images.githubusercontent.com/66446067/157118345-de96d7f9-faf0-4da5-a901-f08f67f72ce9.png)

#### Arguments:
argument | value
--- | ---
bg_color or bg | tuple: (light_color, dark_color) or single color

and all arguments and methods of `tkinter.Toplevel`.
