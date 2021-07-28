# Windows (WSL) 

**Required Reading**
This will require you to be on Version 1903 of Windows 10. If you need to update, you may use Windows Update or the Update Assitant from Microsoft.


**What you need**
 - Admin Permissions 
 - WSL Updater from [here](https://wslstorestorage.blob.core.windows.net/wslblob/wsl_update_x64.msi)

**Instructions**

1. Open PowerShell with administrator permissions.
2. Using PowerShell, enable WSL using the following command: `dism.exe /online /enable-feature /featurename:Microsoft-Windows-Subsystem-Linux /all /norestart`
3. Using PowerSheel, enable the Windows Virtual Machine feature using the following command: `dism.exe /online /enable-feature /featurename:VirtualMachinePlatform /all /norestart`
4. Run the WSL updater that you downloaded earlier.
5. Open the Microsoft Store and install Ubuntu. Any version is fine.
6. Open the installed distro and setup your username and password. Close it when you are done.
7. Going back to PowerShell, run `wsl --list --verbose` to get a list of installations.
8. Run `wsl --set-version <distribution name> 2`, replacing <distribution name> with your install's name. This may take a few minutes.
9. Reopen the linux install and run `sudo apt update` and `sudo apt upgrade`, this will take you to the latest versions of packages available. 
10. Run `python3 -m pip install --user qmk` to setup the qmk tool. 
 *Currently due to a bug within Ubuntu's terminal, qmk will not be in your path, run `echo 'PATH="$HOME/.local/bin:$PATH"' >> $HOME/.bashrc && source $HOME/.bashrc` to fix.*
11. Run `qmk setup -b develop` from  your WSL instance. If you prompted to install submodules, say yes.
  
Continue to [Making a Keymap](making-keymap)
{: .notice--info}
