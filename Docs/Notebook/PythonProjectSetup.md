# Python Project Setup

***Author: Dingkun***

***Last Update:  2021/Dec/17***

***Visit [My GitHub](https://github.com/Oct19) for more info***

---

## GitHub initialize

- Install Github desktop
- Create repository/Clone repository
- Make sure to create .gitignore **BEFORE** generate virtual environment!

If .gitignore is not working:

    git rm -rf --cached .
    git add .

## Virtual environment (VEnv)

### Create VEnv

    python -m venv <venv_name>
    <venv_name>/Scripts/activate.bat

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
