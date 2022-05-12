## Change Tkinter Icon


If you want to change the icon from the window:

```python

# Prerequisites
# python installed and added to the path
# tkinter installed
# customtkinter installed
import os
import sys
import tkinter
import customtkinter

# 1. we need to find the current path 
# so we can pass the string result to iconbitmap function
def get_file_str():
	
	current_path = os.getcwd()
	print(current_path)
	path_n_file = ""
	
	if sys.platform == 'linux':
		path_n_file = "@" + current_path + "/assets/ic.xbm"
	
	elif os.name == 'win32':
		path_n_file = current_path + "\\assets\\ic.icon"
	
	elif sys.platform == 'darwin':
		path_n_file = "@" + current_path + "/assets/ic.icns"
	
	else:
		raise Exception("Unknown system")
		exit(1)
	
	print(path_n_file)
	return path_n_file

customtkinter.set_appearance_mode("dark")

app = customtkinter.CTk()
app.title('Title')
app.iconbitmap(get_file_str())
app.geometry("400x300")


app.mainloop()


```

PS: You can find sample icon images inside the folder assets at: https://github.com/felipetesc/CtkDocs/tree/main/docs/assets