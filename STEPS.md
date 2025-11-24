- Generated repository from denisecase/applied-ml-template
- Downloaded repository using `git clone https://github.com/matthewpblock/applied-ml-new-matthew-block`
- Changed VS Code folder to APPLIED-ML-NEW-MATTHEW-BLOCK
- Build virtual environment with `python -m venv .venv`
- Activated virtual environment with `.\.venv\Scripts\activate`
- `pip install ipykernel`
- `python.exe -m pip install --upgrade pip`
- Ctrl+Shift+P - Python: Select Interpreter
  - Navigated to python.exe within .venv folder
  - 'Detecting Kernels' still continuously spinning
- `pip install jupyter`
  - Received error
> ERROR: Could not install packages due to an OSError: [Errno 2] No such file or directory: 
> 'C:\\Projects\\MS_Data_Analytics\\Applied-Machine-Learning\\applied-ml-new-matthew-block\\.venv\\share\\jupyter\\labextensions\\@jupyter-widgets\\jupyterlab-manager\\static\\packages_base_lib_index_js-webpack_sharing_consume_default_jquery_jquery.5dd13f8e980fa3c50bfe.js.map'
> HINT: This error might have occurred since this system does not have Windows Long Path support enabled. You can find information on how to enable this at https://pip.pypa.io/warnings/enable-long-paths
- In PowerShell
  - attempted `New-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\FileSystem" -Name "LongPathsEnabled" -Value 1 -PropertyType DWORD -Force`
  - received error:
    - >New-ItemProperty : Requested registry access is not allowed.
      > At line:1 char:1
      >+ New-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\FileSy ...
      >+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
      >+ CategoryInfo          : PermissionDenied: (HKEY_LOCAL_MACH...trol\FileSystem:String) [New-ItemProperty], SecurityException
      >+ FullyQualifiedErrorId : System.Security.SecurityException,Microsoft.PowerShell.Commands.NewItemPropertyCommand

- Open PowerShell as admin:
  - ran `New-ItemProperty -Path "HKLM:\SYSTEM\CurrentControlSet\Control\FileSystem" -Name "LongPathsEnabled" -Value 1 -PropertyType DWORD -Force`
  - Received:
    - >LongPathsEnabled : 1
      >PSPath           : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\FileSystem
      >PSParentPath     : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control
      >PSChildName      : FileSystem
      >PSDrive          : HKLM
      >PSProvider       : Microsoft.PowerShell.Core\Registry

- `pip install jupyter` again
  - successful
- Checked notebook again; 'Detecting Kernels' still unsuccessful
- Deleted 'settings.json'
  - Still unsuccessful
- Deleted 'python-version'
- Deleted uv.lock
- Deleted pyproject.toml

- `jupyter kernelspec list`
  - >Available kernels:
    > python3    C:\Projects\MS_Data_Analytics\Applied-Machine-Learning\applied-ml-new-matthew-block\.venv\share\jupyter\kernels\python3
    > .venv      C:\Users\matth\AppData\Roaming\jupyter\kernels\.venv
- `jupyter kernelspec remove .venv`
- 
