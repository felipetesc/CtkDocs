## Resizable Frame

If you want to divide an area with two reziable frames

##### Preview
![Project Packages](/assets/drag_panel.gif)

##### Code

```python
	import tkinter as tk
	from tkinter import ttk

	import customtkinter
	customtkinter.set_appearance_mode("dark")

	def on_clik_print():
		print("bt clicked")

	app = customtkinter.CTk()
	app.title('Title')
	app.geometry("400x300")

	panel_divider = ttk.PanedWindow(orient="horizontal")
	panel_divider.pack(fill="both", expand=True)


	left_panel = customtkinter.CTkFrame(master=panel_divider)
	left_button = customtkinter.CTkButton(master=left_panel, text="left button", command=on_clik_print)
	left_button.place(relx=0.5, rely=0.5, anchor=tk.CENTER)

	right_panel = customtkinter.CTkFrame(master=panel_divider)
	right_button = customtkinter.CTkButton(master=right_panel, text="right button", command=on_clik_print)
	right_button.place(relx=0.5, rely=0.5, anchor=tk.CENTER)

	panel_divider.add(left_panel)
	panel_divider.add(right_panel)


	app.mainloop()


```