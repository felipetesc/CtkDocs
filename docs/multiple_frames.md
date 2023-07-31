### Multiple Frames

#### Sample - Ctk Version 

```python

import tkinter
import customtkinter
from functools import partial

DARK_MODE = "dark"
customtkinter.set_appearance_mode(DARK_MODE)
customtkinter.set_default_color_theme("blue")


class App(customtkinter.CTk):

    frames = {}
    current = None
    bg = ""


    def __init__(self):
        super().__init__()
        self.bg = self.cget("fg_color")
        self.num_of_frames = 0
        # self.state('withdraw')
        self.title("Change Frames")

        # screen size
        self.geometry("800x600")

        # root!
        main_container = customtkinter.CTkFrame(self, corner_radius=8, fg_color=self.bg)
        main_container.pack(fill=tkinter.BOTH, expand=True, padx=8, pady=8)

        # left side panel -> for frame selection
        self.left_side_panel = customtkinter.CTkFrame(main_container, width=280, corner_radius=8, fg_color=self.bg)
        self.left_side_panel.pack(side=tkinter.LEFT, fill=tkinter.Y, expand=False, padx=18, pady=10)

        # right side panel -> to show the frame1 or frame 2, or ... frame + n where n <= 5
        self.right_side_panel = customtkinter.CTkFrame(main_container, corner_radius=8, fg_color="#212121")
        self.right_side_panel.pack(side=tkinter.LEFT, fill=tkinter.BOTH, expand=True, padx=0, pady=0)
        self.right_side_panel.configure(border_width = 1)
        self.right_side_panel.configure(border_color = "#323232")
        self.create_nav( self.left_side_panel, "frame1", self.color_by_id(1))
        self.create_nav( self.left_side_panel, "frame2", self.color_by_id(2))
        self.create_nav( self.left_side_panel, "frame3", self.color_by_id(3))
        self.create_nav( self.left_side_panel, "frame4", self.color_by_id(4))
        self.create_nav( self.left_side_panel, "frame5", self.color_by_id(5))


    def color_by_id(self, id):
        if id == 1: 
            return "blue"
        
        elif id == 2:
            return "green"
        
        elif id == 3:
            return "orange"
        
        elif id == 4:
            return "purple"
        
        elif id == 5:
            return "grey" 
        
        else:
            return "red"

    # button to select the correct frame
    def frame_selector_bt(self, parent, frame_id):
        
        # create frame 
        bt_frame = customtkinter.CTkButton(parent)
        # style frame
        bt_frame.configure(height = 40)
        # creates a text label
        bt_frame.configure(text = self.color_by_id(self.num_of_frames + 1)  )
        bt_frame.configure(command =  partial( self.toggle_frame_by_id,  "frame" + str(self.num_of_frames + 1) ) )
        # set layout
        bt_frame.grid(pady = 3, row=self.num_of_frames, column=0)
        # update state
        self.num_of_frames = self.num_of_frames + 1

    # create the frame
    def create_frame(self, frame_id, color):
        App.frames[frame_id] = customtkinter.CTkFrame(self, fg_color=self.cget("fg_color"))
        App.frames[frame_id].configure(corner_radius = 8)
        App.frames[frame_id].configure(fg_color = color)
        App.frames[frame_id].configure(border_width = 2)
        App.frames[frame_id].configure(border_color = "#323232")
        App.frames[frame_id].padx = 8

        bt_from_frame1 = customtkinter.CTkButton(App.frames[frame_id], text="Test "+ self.color_by_id(self.num_of_frames) , command=lambda:print("test " + color) )
        bt_from_frame1.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)

    # method to change frames
    def toggle_frame_by_id(self, frame_id):
        
        if App.frames[frame_id] is not None:
            if App.current is App.frames[frame_id]:
                App.current.pack_forget()
                App.current = None
            elif App.current is not None:
                App.current.pack_forget()
                App.current = App.frames[frame_id]
                App.current.pack(in_=self.right_side_panel, side=tkinter.TOP, fill=tkinter.BOTH, expand=True, padx=0, pady=0)
            else:
                App.current = App.frames[frame_id]
                App.current.pack(in_=self.right_side_panel, side=tkinter.TOP, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

    # method to create a pair button selector and its related frame
    def create_nav(self, parent, frame_id, frame_color):
        self.frame_selector_bt(parent, frame_id)
        self.create_frame(frame_id, frame_color)


a = App()
a.mainloop()

```
https://github.com/felipetesc/CtkDocs/assets/2336812/5c5d24ce-46b7-40b6-b022-0d450d66de6b


