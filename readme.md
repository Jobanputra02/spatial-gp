# T5: Notebook Setup Guide

1. **Python & Virtual Environment**
   - Ensure Python 3.11 is installed.
   - Create a virtual environment:
     - Windows: `py -3.11 -m venv .venv && .venv\Scripts\activate`
     - macOS/Linux: `python3.11 -m venv .venv && source .venv/bin/activate`
   - Upgrade pip: `python -m pip install --upgrade pip`

2. **Install Dependencies**
   - `pip install -r requirements.txt`
   - Optional: `pip install --upgrade pymc` to ensure latest version

3. **Graphviz**
   - Must install system binaries and add to PATH .
     - Windows: download installer (https://graphviz.org/download/), add `C:\Program Files\Graphviz\bin` to PATH
     - macOS: `brew install graphviz`
     - Linux: `sudo apt install graphviz -y`
   - Test: `dot -V`

4. **Aesara BLAS fix**

   - Create `.aesararc` in home directory (Should look like C:/Users/YourUsername/.aesararc for windows users and  at ~/.aesararc for macOS/Linux users):
     ```
     [blas]
     ldflags=
     ```
   - Delete any `__pycache__` folders if appears.

5. **Jupyter Kernel**
   - `python -m ipykernel install --user --name=.venv --display-name "Python 3.11 (.venv)"`

6. **Launch Notebook**
   - `jupyter notebook` or `jupyter lab`
   - Select the kernel: `Python 3.11 (.venv)`

**Warnings ⚠️**
- If you encounter Aesara circular import errors, restart your IDE or notebook server.
- Graphviz setup is often the trickiest part; ensure system binaries are in PATH.
- If Graphviz not set up correctly, PyMC/ArviZ (model graphs) plotting may fail.
