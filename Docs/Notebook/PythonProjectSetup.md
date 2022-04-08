# Python Project Setup

***Author: Dingkun***

***Last Update:  2022/Apr/9***

***Visit [My GitHub](https://github.com/Oct19) for more info***

---
## Python Installation

- Download and install desired version of Python(Do not add PATH)
- For first time install, add Python and Python/Script to "PATH" in environment variables.

It should like this:

    C:\Python\python-3.10.4-amd64
    C:\Python\python-3.10.4-amd64\Scripts


## VS Code

- Install VS Code
- Login account and sync settings
- Add extensions for Python, Pylance, Vim, Tabnine, Jupyter, etc

## GitHub initialize

- Install Git
- Install Github desktop
- Create repository(with gitignore&README)/Clone repository

If .gitignore is not working:

    git rm -rf --cached .
    git add .

## Virtual environment

### Create VEnv

    python -m venv venv
    venv/Scripts/activate.bat

Python: Select interpreter from `<venv_name>/Scripts/python.exe`

---

## Import required packages 

Optional 1: Open project with VEnv to copy from, generate requirements file

    pip freeze > requirements.txt

Copy `requirements.txt` to destination folder, and then

    pip install -r requirements.txt

---

Option 2: Ensure pip

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
- Slow download speed:
Update default download url to `清华pypi镜像`:
      
      pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

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
