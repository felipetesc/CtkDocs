## CTk


Theoretically you could also use the normal `tkinter.Tk` class to create a window and place CTK widgets on it,
but it is highly recommended to use the `cuatomtkinter.CTk` to create the window if you use CustomTkinter.
Because only with the `CTk` window you get a dark window background and header which adapts to the dark/light mode
set by `customtkinter.set_appearance_mode(...)`.

Apart from the changing background and header color, the `CTk` class behaves exactly like the `tkinter.Tk` class.

## Example Code:

```python
root_tk = customtkinter.CTk()
root_tk.geometry(f"{600}x{500}")
root_tk.title("CTk example")

... program ...

root_tk.mainloop()
```


```python
class App(customtkinter.CTk)
    def __init__(self):
        super().__init__()

        self.geometry(f"{600}x{500}")
        self.title("CTk example")

        ... create widgets ...

    ... program methods ...

app = App()
app.mainloop()
```

#### Arguments:

argument | value
--- | ---
bg_color or bg | tuple: (light_color, dark_color) or single color and all arguments from `tkinter.Tk`

#### Methods:

```python
root_tk = customtkinter.CTk()
# configure bg color with single or tuple color
root_tk.configure(bg_color="gray20")
root_tk.configure(bg_color=(<light-mode color>, <dark-mode color>))
```
and all methods from `tkinter.Tk`