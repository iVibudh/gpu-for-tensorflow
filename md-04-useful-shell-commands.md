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
cmd
>>wsl -l -v
>> wsl --unregister ubuntu


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
