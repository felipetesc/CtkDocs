## Contribution

You can contribute in several ways:
- open a new issue tracker for a new bug
- help to fix bugs
- creating new themes
- creating  new widgets
- creating tests (performance, security, unit tests)
- sharing projects using CustomTkinter
- writing documentation
- requesting new widgets
- spreading the word about CustomTkinter
- adding new functionality
- improving code performance

### Issues ?
If You find a new issue, You can categorize it using this labels:

- enhancement 
- bug
- documentation
- help wanted
- question

So, a new issue could be created using as a title, something like this:
<br/>
**Bug: button disappears on click**

And as a body of the new issue, it could be like this:<br/>

**OS Used: Windows 11**

**Python version : 3.10.4**

Expected Behavior
On click button changes its state from the normal state to the dropdown state
	
Actual Behavior
When clicked, the button becomes invisble

Steps to reproduce the behavior 

```python
	def button_event():
		print("button pressed")

	button = customtkinter.CTkButton(master=root_tk,text="CTkButton",command=button_event)
	
	button.pack(padx=20, pady=10)
```


So, feel free to ask questions in the [Issues tab](https://github.com/TomSchimansky/CustomTkinter/issues).

