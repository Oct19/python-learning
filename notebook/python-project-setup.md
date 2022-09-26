# Python Project Setup

***Author: Dingkun***

***Last Update:  2022/Sep/24***

***Visit [My GitHub](https://github.com/oct19) for more info***

---

## Python Installation

- Download and install desired version of Python, choose `add PATH` when prompted

Your PATH should contain the following:

    ...\Python\python-3.10.4-amd64
    ...\Python\python-3.10.4-amd64\Scripts

## VS Code

- Install VS Code
- (Optional) Login account and sync settings
- Add extensions
  - Python, Pylance, Tabnine, Jupyter

## GitHub initialize

- Install Git
- Install Github desktop
- Create repository(with gitignore&README)/Clone repository

If .gitignore is not working:

    git rm -rf --cached .
    git add .

## Virtual environment

### Create VEnv

New bash Terminal (not powershell Terminal)

    python -m venv venv
    venv/Scripts/activate.bat

Python: Select interpreter from `<venv_name>/Scripts/python.exe`

---

## Testing

Install packages

    pip install numpy

If package requirements are recorded in `requirements.txt` file:

    pip install -r requirements.txt

To generate requirements.txt file:

    pip install pipreqs

    pipreqs /path/to/project

### Common problems

- Could not find a version that satisfies the requirement

  Check package's compatible Python version (64-bit or 32-bit, 3.10 or newer);
  
  Check Terminal Python version

- Could not fetch URL, connect=None

  Turn off proxy

- Slow download speed:

  Update default download url to `清华pypi镜像`:

      pip config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple

- No module named pip

      python -m ensurepip

- WARNING: Ignoring invalid distribution -ip

  In `venv` folder, delete files with names start with "~"

- When running Python within Jupyter cells, Cannot connect to kernel
  
  Close and reopen VScode
  
      python -m pip install 'traitlets==4.3.3' --force-reinstall
