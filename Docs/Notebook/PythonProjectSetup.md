# Python Project Setup

***Author: Dingkun***

***Last Update:  2021/Nov/27***

***Visit [My GitHub](https://github.com/Oct19) for more info***

---

## GitHub initialize

- Install Github desktop
- Create repository/Clone repository
- Make sure to create .gitignore **BEFORE** generate virtual environment!

If .gitignore is not working:

    git rm -rf --cached .
    git add .

## Install specific Python version (Optional)

1. Download the Python version that you need, e.g. Python 3.8
2. Install the Python executable. I recommend a custom installation. There’s no need to add it to PATH.

## Virtual environment

### Create VEnv (Using virtualenv)

1. Run Virtual Studio Code (or any other editor or terminal). Windows: If the installation directory is within Program Files, run it as an Administrator.
2. Install virtualenv in your main Python version via `pip install virtualenv`
3. Create the virtual environment with virtualenv, and specify the -p parameter.

If your directory contains spaces, wrap it in double quotes. Like this:

    py -m virtualenv -p="C:\Program Files\Python38\python.Exe" .virtenv
    <venv_name>/Scripts/activate.bat

### Alternative way of creating Virtual environment: venv

    python -m venv <venv_name>
    <venv_name>/Scripts/activate.bat

Python: Select interpreter from `<venv_name>/Scripts/python.exe`

---

### Import required packages (Optional 1)

Open project with VEnv to copy from, generate requirements file

    pip freeze > requirements.txt

Copy `requirements.txt` to destination folder, and then

    pip install -r requirements.txt

---

### Manually install packages with pip (Option 2)

Ensure pip

    python -m ensurepip

Install packages

    pip install numpy

Install packages with user rights

    pip install numpy --user

Update packages

    pip install -U numpy

Problem: `Could not find a version that satisfies the requirement`

- Solution: Check package's compatible Python version; Check Terminal Python version. Powershell might not use the same Python version as current virtenv.

- For example: PyTorch only support Python 64-bit version; PyTorch does not support newest Python version

### Common problems

- Could not fetch URL, connect=None
  - Windows setting > Proxy > add exceptions: pypi.org
- No module named pip
  - python -m ensurepip
- WARNING: Ignoring invalid distribution -ip
  - In Env folder, delete files with names start with "~"

### Powershell

- cannot be loaded because the execution of scripts is disabled on this system.
  - Run as Admin
  - Set-ExecutionPolicy RemoteSigned

## Jupyter

Install Jupyter from VS Code Extensions

### Problems

- When running Python within cells, Cannot connect to kernel
  - Close and reopen VS code
  - python -m pip install 'traitlets==4.3.3' --force-reinstall
