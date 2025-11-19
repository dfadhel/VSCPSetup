# Python & VS Code Setup on Windows 11

This document provides a step-by-step walkthrough to configure a robust Python development environment on Windows 11 using Visual Studio Code (VS Code).

## Table of Contents

1. Step 1: Installing Python   
2. Step 2: Installing Visual Studio Code
3. Step 3: Connecting Python to VS Code
4. Step 4: Creating Your First Project
5. Step 5: Understanding Virtual Environments (Best Practice)
6. Troubleshooting & References

## Step 1: Installing Python

We will install the official version of Python from the Python Software Foundation.

### Method A: The Standard Installer (Recommended)

1. **Download:** Visit the [Official Python Downloads Page](https://www.python.org/downloads/ "null").
    
    - Click the large yellow button (usually **Download Python 3.x.x**).
        
2. **Run Installer:** Open the downloaded `.exe` file.
    
3. **IMPORTANT CRITICAL STEP:** * On the first screen of the installer, **check the box** at the bottom that says:
    
    `[x] Add python.exe to PATH`
    
    - _If you miss this, you won't be able to run Python from the command line easily._
        
4. **Install:** Click **Install Now**.
    
5. **Finish:** Once done, you may see a button to "Disable path length limit". It is safe and recommended to click this. Close the installer.
    

### Method B: Using Winget (For Power Users)

If you are comfortable with the terminal, you can install Python via Windows Package Manager. Open PowerShell and run:

```
winget install Python.Python.3
```

### Verification

1. Open **Command Prompt** or **PowerShell** (Search "Terminal" in the Start Menu).
    
2. Type the following and press Enter:
    
    ```
    python --version
    ```
    
3. You should see a response like `Python 3.12.x`. If you see an error, restart your computer and try again.
    

## Step 2: Installing Visual Studio Code

VS Code is a lightweight code editor.

1. **Download:** Visit the [VS Code Official Website](https://code.visualstudio.com/ "null").
    
2. **Install:** Click **Download for Windows**.
    
3. **Run Installer:**
    
    - Accept the agreement.
        
    - **Recommended:** Check the boxes for **"Add 'Open with Code' action to Windows Explorer file context menu"** and **"directory context menu"**. This lets you right-click any folder and open it instantly in VS Code.
        
4. **Launch:** Open Visual Studio Code.
    

## Step 3: Connecting Python to VS Code

VS Code needs an extension to understand Python syntax and debugging.

1. Open VS Code.
    
2. Click on the **Extensions** icon in the left Sidebar (or press `Ctrl + Shift + X`).
    
3. In the search bar, type: `Python`.
    
4. Look for the extension named **Python** published by **Microsoft** (usually the first result with millions of downloads).
    
5. Click **Install**.
    
6. _Optional but Recommended:_ Also install the **Pylance** extension (usually installs automatically with the Python extension) for better IntelliSense (autocompletion).
    

## Step 4: Creating Your First Project

Never write code blindly; always work inside a folder (Project).

1. **Create a Folder:** Go to your Desktop or Documents, right-click, create a new folder named `PythonProject`.
    
2. **Open in VS Code:**
    
    - Right-click the folder and select **Open with Code**.
        
    - _Or_, inside VS Code, go to `File > Open Folder...` and select it.
        
3. **Create a File:**
    
    - In the "Explorer" pane (left side), click the "New File" icon.
        
    - Name it `main.py`.
        
4. **Select Interpreter:**
    
    - Look at the bottom right corner of VS Code. You should see a Python version listed (e.g., `3.12.0`).
        
    - If not, click the `{}` curly braces or the "Select Interpreter" warning, and click on the recommended Python path.
        
5. **Write Code:**
    
    ```
    print("Hello, Windows 11!")
    ```
    
6. **Run:**
    
    - Click the **Play Button** (Run Python File) in the top right corner.
        
    - A terminal panel will open at the bottom showing: `Hello, Windows 11!`.
        

## Step 5: Understanding Virtual Environments (Best Practice)

**Why?** Installing libraries globally (on your main computer system) can break things when different projects need different versions of the same library. Always use a Virtual Environment (`venv`).

### How to set it up in VS Code:

1. Open your terminal inside VS Code (`Ctrl +` ).
    
2. Type the following to create an environment named `.venv`:
    
    ```
    python -m venv .venv
    ```
    
3. **Activate it:**
    
    - VS Code will often detect this new folder and ask: _"We noticed a new environment has been created. Do you want to select it for the workspace folder?"_ -> Click **Yes**.
        
    - If it doesn't ask: Press `Ctrl + Shift + P`, type `Python: Select Interpreter`, and choose the one inside `.\.venv\Scripts\python.exe`.
        
4. **Verify:**
    
    - Kill the terminal (Trash can icon) and open a new one (`Ctrl +` ).
        
    - You should see `(.venv)` in green text at the start of your command line prompt.
        
5. **Install Packages:**
    
    - Now you can safely install libraries specifically for this project:
        
    
    ```
    pip install requests pandas
    ```
    

## Troubleshooting & References

### Common Issues

- **"Python is not recognized as an internal or external command":**
    
    - You forgot to check "Add to PATH" during installation.
        
    - _Fix:_ Re-run the Python installer, choose "Modify", and ensure "Add to environment variables" is checked.
        
- **PowerShell says "running scripts is disabled":**
    
    - Windows security blocks scripts by default.
        
    - _Fix:_ Open PowerShell as Administrator and run: `Set-ExecutionPolicy RemoteSigned`. Type `Y` to confirm.
        

### Useful Shortcuts

- `Ctrl + Shift + P`: Opens the Command Palette (Access all VS Code settings).
    
- `Ctrl + /`: Comment/Uncomment code.
    
- `Shift + Alt + F`: Format document (makes your code look pretty).
    

### Official Documentation Links

- [Python Documentation](https://docs.python.org/3/ "null")
    
- [VS Code Python Tutorial](https://code.visualstudio.com/docs/python/python-tutorial "null")
    
- [Pip (Package Installer) Docs](https://pip.pypa.io/en/stable/ "null")
