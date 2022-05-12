## Packing and distributing

### Windows PyInstaller (Auto Py to Exe)

When you create a .exe on Windows with pyinstaller, there are two things you have to consider.
Firstly, you cannot use the `--onefile` option of pyinstaller, because the customtkinter library includes not only .py files, but also data files like .json and .otf. PyInstaller is not able to pack them into a single .exe file, so **you have to use the `--onedir` option.**

And secondly, you have to include the customtkinter directory manually with the `--add-data` option of pyinstaller. Because for some reason, pyinstaller doesn't automatically include datafiles like .json from the library.
You can find the install location of the customtkinter library with the following command:
```
pip show customtkinter
```
A Location will be shown, for example: `c:\users\<user_name>\appdata\local\programs\python\python310\lib\site-packages`

Then add the library folder like this: `--add-data "C:/Users/<user_name>/AppData/Local/Programs/Python/Python310/Lib/site-packages/customtkinter;customtkinter/"`

With Auto Py to Exe you would do it like this:

![Bildschirmfoto 2022-03-22 um 19 47 32](https://user-images.githubusercontent.com/66446067/159553835-29a8dcfc-91b6-4610-a1bf-ef0c24c21988.png)

**For the full command you get something like this:**
```
pyinstaller --noconfirm --onedir --windowed --add-data "<CustomTkinter Location>/customtkinter;customtkinter/"  "<Path to Python Script>"
```