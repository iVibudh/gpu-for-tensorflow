### 03. Useful Shell Commands 


#### 1. Install WSL on windows 11 or 10
    - Open "Windows PowerShell"
    - \Users\vibud> wsl --install <br>
    (installs ubuntu by default)
    - Reboot the system and set password

#### 2. Open wsl  
    - Open "Windows PowerShell" or "CMD"
    - >>wsl 

#### 3. Remove Conda environment
- [Ref - FreecodeCamp](https://www.freecodecamp.org/news/how-to-delete-an-environment-in-conda/)
- Remove conda env 
	- conda env list 
	- conda remove --name ENV_NAME --all
	
#### 4. Remove registered jupyter kernel
- [Ref - blog](https://queirozf.com/entries/jupyter-kernels-how-to-add-change-remove)
- Remove jupyter kernesl
	- jupyter kernelspec list
	- jupyter kernelspec remove <kernel-name>

#### 5. Uninstall wsl for windows 11
1. Unrehgister wsl 
	- cmd <br>
	- >>wsl -l -v <br>
	- >> wsl --unregister ubuntu <br>
2. Open Add or remove programs in windows 
	- Search and delete each one of them 
		- "wsl" or "windows subsystem for linux"
		- ubuntu 
		- linux
3. Uninstall WSL and Virtual Machine Platform
[ref](https://www.makeuseof.com/uninstall-wsl-windows/#:~:text=Uninstall%20the%20WSL%20Components&text=Go%20to%20Settings%20>%20Apps%20>%20Apps,name%20and%20then%20click%20Uninstall.)
	- Open the Windows Features panel by going to Settings > Apps > Optional Features > More Windows Features. You can also search for Windows Features and click Turn Windows features on or off.
	- Scroll down the list of features to find and deselect the Windows Subsystem for Linux option.
	- If you don't need to run any other virtual environments, you can also deselect the Virtual Machine Platform option.
	- Click Ok, and then restart your computer.

#### 5. open the directory in explorer 
	# explorer.exe


#### 6-NA. Clear cache memory in NVIDIA-GPU
	- nvidia-smi --gpu-reset
	- "%appdata%" in search 
	- Go to "AppData/Local/NVIDIA Corporation/NV Cache"
		- Delete everything in this folder 
	- Go to "AppData/Local/NVIDIA"
		- Delete everything in this folder
	- Go to "AppData/Local/Temp/"
		- Delete
	- Go to "C:/ProgramData/NVIDIA Corporation/NV Cache
