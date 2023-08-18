### 00-windows-native-paths



When you are installing CUDA for windows native environments then make sure that you add the cuda file paths to the stsyem paths for allowing it to run with your system commands
 <br> <br>

C:\Users\vibud\AppData\Local\Programs\Microsoft VS Code\bin <br>
C:\Users\vibud\AppData\Local\Microsoft\WindowsApps <br>
C:\ProgramData\anaconda3\Library\bin <br>
C:\ProgramData\anaconda3\Scripts <br>
C:\ProgramData\anaconda3\condabin <br>
C:\ProgramData\anaconda3\ <br>

 <br> <br> <br>

C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\bin  <br>
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\libnvvp  <br>


C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\extras\CUPTI\lib64  <br>
C:\Program Files\NVIDIA GPU Computing Toolkit\CUDA\v12.2\include  <br>


C:\tools\cudnn-windows-x86_64-8.9.3.28_cuda12-archive\bin <br>
C:\tools\cudnn-windows-x86_64-8.9.3.28_cuda12-archive\include  <br>


Activate Tensorflow envitonment:  <br>
C:\Users\vibud>conda create -y --name tensorflow python=3  <br>
conda activate tensorflow  <br>
X----- conda install ipykernel  <br>
python -m ipykernel install --user --name tensorflow --display-name "Python 3.9 (tensorflow)"  <br>

python -m ipykernel install --user --name tensorflow --display-name "Python 3.9 (tensorflow)" <br>