## Samples

### Example 1
To test customtkinter you can try this simple example with only a single button:
```python
import tkinter
import customtkinter

customtkinter.set_appearance_mode("System")  # Modes: system (default), light, dark
customtkinter.set_default_color_theme("blue")  # Themes: blue (default), dark-blue, green

root_tk = customtkinter.CTk()  # create CTk window like you do with the Tk window
root_tk.geometry("400x240")

def button_function():
    print("button pressed")

# Use CTkButton instead of tkinter Button
button = customtkinter.CTkButton(master=root_tk, text="CTkButton", command=button_function)
button.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)

root_tk.mainloop()
```
which gives the following (macOS dark mode on):

![](documentation_images/macOS_button_dark.png)

In the [examples folder](https://github.com/TomSchimansky/CustomTkinter/tree/master/examples), you can find more example programs and in the [Documentation](https://github.com/TomSchimansky/CustomTkinter/wiki) you can find further information on the appearance mode, the themes and all widgets.