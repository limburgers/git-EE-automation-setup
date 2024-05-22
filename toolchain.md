**## setup SPD in VSCode (Windows 10)**
 - Download Python 3 and VSCode
   - Download VSCode Python Extension
 - Open cmd or powershell (don't use VSC terminal; causes infrequent errors)
   - Type "mkdir [folder name]"
   - "cd [folder name]"
   - "code ."
 - Open Command Palette (Ctrl+Shift+P) in VSC and type "Python: Create Environment"
   - Select .venv (virtual environment)
   - Select "Python" (the software downloaded at the start)
 - Open Command Palette (Ctrl+Shift+P) in VSC and type "Python: Select Interpreter"
   - Select Python .venv (Option that is "Recommended")
 - From the File Explorer toolbar, select New File button on the [folder name] folder
   - Name the file: [file name].py (EX: hello.py)
 - Open Python Terminal
   - Type "py -m pip install pyvisa"
   - "py -m pip install pyvisa-py"
   - "py -m pip install pyusb"
   - "py -m pip install keyboard"
 - Open the [file name].py and follow code from dl.py, mso.py, & spd.py
**## Resources**
 - https://code.visualstudio.com/docs/python/python-tutorial
 - https://hackaday.com/2016/11/16/how-to-control-your-instruments-from-a-computer-its-easier-than-you-think/
 - https://www.youtube.com/watch?v=DUJpL9pMy8Y

 - https://siglentna.com/USA_website_2014/Documents/QuickStart/SPD3303X_QuickStart_QS0503X-E01B.pdf

**## git/bash tutorial**
 (make sure to git pull when loading up code in a new instance)
 look at file: "git bash tutorial"
 -
 - alternatively, i just added the file into the github branch manually through github itself (upload .py files)

  #When pulling from github into vscode, do git clone [github url] --branch [branch name]
  - after it finishes uploading into vscode, open the file that the clone is located in
