### Multiple Frames

#### Sample 1

```python

import tkinter
import customtkinter

DARK_MODE = "dark"
customtkinter.set_appearance_mode(DARK_MODE)
customtkinter.set_default_color_theme("blue")


class App(customtkinter.CTk):

    frames = {"frame1": None, "frame2": None}

    def frame1_selector(self):
        App.frames["frame2"].pack_forget()
        App.frames["frame1"].pack(in_=self.right_side_container,side=tkinter.TOP, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

    def frame2_selector(self):
        App.frames["frame1"].pack_forget()
        App.frames["frame2"].pack(in_=self.right_side_container,side=tkinter.TOP, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

    def __init__(self):
        super().__init__()
        # self.state('withdraw')
        self.title("Change Frames")

        self.geometry("800x600")

        # contains everything
        main_container = customtkinter.CTkFrame(self)
        main_container.pack(fill=tkinter.BOTH, expand=True, padx=10, pady=10)

        # left side panel -> for frame selection
        left_side_panel = customtkinter.CTkFrame(main_container, width=150)
        left_side_panel.pack(side=tkinter.LEFT, fill=tkinter.Y, expand=False, padx=10, pady=10)

        # buttons to select the frames
        bt_frame1 = customtkinter.CTkButton(left_side_panel, padx=10, pady=10, text="Frame 1", command=self.frame1_selector)
        bt_frame1.grid(row=0, column=0)

        bt_frame2 = customtkinter.CTkButton(left_side_panel, padx=10, pady=10, text="Frame 2", command=self.frame2_selector)
        bt_frame2.grid(row=1, column=0)

        # right side panel -> to show the frame1 or frame 2
        self.right_side_panel = customtkinter.CTkFrame(main_container)
        self.right_side_panel.pack(side=tkinter.LEFT, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

        self.right_side_container = customtkinter.CTkFrame(self.right_side_panel)
        self.right_side_container.pack(side=tkinter.LEFT, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

        App.frames['frame1'] = customtkinter.CTkFrame(fg_color="red")
        bt_from_frame1 = customtkinter.CTkButton(App.frames['frame1'], text="Test 1", command=lambda:print("test 1") )
        bt_from_frame1.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)

        App.frames['frame2'] = customtkinter.CTkFrame(fg_color="blue")
        bt_from_frame2 = customtkinter.CTkButton(App.frames['frame2'], text="Test 2", command=lambda:print("test 2") )
        bt_from_frame2.place(relx=0.5, rely=0.5, anchor=tkinter.CENTER)

a = App()
a.mainloop()

```


#### Sample 2

##### Preview

![Project Packages](/assets/frame_selection.gif)

##### Code

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

    # button to select correct frame
    def frame_selector_bt(self, panel):
        bt_frame = customtkinter.CTkButton(panel, padx=10, pady=10, corner_radius=0,
            text=("Frame " + str(self.num_of_frames + 1)), command=partial(self.toggle_frame_by_id, "frame" + str(self.num_of_frames + 1) ))
        bt_frame.grid(row=self.num_of_frames, column=0)
        self.num_of_frames = self.num_of_frames + 1

    # create the frame
    def create_frame(self, frame_id, color):
        App.frames[frame_id] = customtkinter.CTkFrame(fg_color=color, corner_radius=0)
        bt_from_frame1 = customtkinter.CTkButton(App.frames[frame_id], text="Test 1", command=lambda:print("test " + color) )
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
        self.frame_selector_bt(parent)
        self.create_frame(frame_id, frame_color)

    def __init__(self):
        super().__init__()
        self.num_of_frames = 0
        # self.state('withdraw')
        self.title("Change Frames")

        self.geometry("800x600")

        # root!
        main_container = customtkinter.CTkFrame(self, corner_radius=0)
        main_container.pack(fill=tkinter.BOTH, expand=True, padx=10, pady=10)

        # left side panel -> for frame selection
        left_side_panel = customtkinter.CTkFrame(main_container, width=150, corner_radius=0)
        left_side_panel.pack(side=tkinter.LEFT, fill=tkinter.Y, expand=False, padx=0, pady=0)

        # right side panel -> to show the frame1 or frame 2
        self.right_side_panel = customtkinter.CTkFrame(main_container, corner_radius=0, fg_color="grey")
        self.right_side_panel.pack(side=tkinter.LEFT, fill=tkinter.BOTH, expand=True, padx=0, pady=0)

        self.create_nav( left_side_panel, "frame1", "blue")
        self.create_nav( left_side_panel, "frame2", "red")
        self.create_nav( left_side_panel, "frame3", "green")
        self.create_nav( left_side_panel, "frame4", "black")
        self.create_nav( left_side_panel, "frame5", "purple")

a = App()
a.mainloop()

```

