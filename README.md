# gpu-for-tensorflow

files to support gpu installation on windows/wsl and ubuntu

- Tensorflow for GPU 
- PyTorch for GPU 
- WSL envs created 
    - tf
    - 
<hr />

### References

- (NEW) [Installation steps on YT by Jeff](https://www.youtube.com/watch?v=0S81koZpwPA&ab_channel=JeffHeaton)

- [Official tensorflow installation Guide](https://www.tensorflow.org/install/pip#windows-wsl2)

Other Links open: 
- https://www.youtube.com/watch?v=StH5YNrY0mE&t=127s&ab_channel=KrishNaik
- https://www.youtube.com/watch?v=r9IqwpMR9TE&t=616s&ab_channel=PythonSimplified


- CUDA Links:
    - [NVIDIA CUDA installation guide for Windows](https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html)
    - [CUDA Quick Start Guide](https://docs.nvidia.com/cuda/cuda-quick-start-guide/index.html#:~:text=The%20Network%20Installer%20allows%20you,to%20the%20Windows%20Installation%20Guide.)
    - [CUDA Samples](https://github.com/NVIDIA/cuda-samples/tree/master/Samples/5_Domain_Specific/nbody)

- [Tensorflow for WSL2](https://www.tensorflow.org/install/pip#windows-wsl2)


<hr />

### Installation Tensorflow on GPU Desktop
- WSL, Miniconda, verv, CUDA and cuDNN
- (NEW) [Installation steps on YT by Jeff](https://www.youtube.com/watch?v=0S81koZpwPA&ab_channel=JeffHeaton)

1.1 Download and install [NVIDIA drivers](https://www.nvidia.com/download/index.aspx) for your GPU
1.2. Install WSL 
    - Open "Windows PowerShell"
    - \Users\vibud> wsl --install <br>
    (installs ubuntu by default)
    - Reboot the system and set password
2. Install Miniconda
    - Open powershell 
    - Open wsl <br>
    >>wsl
    - Download miniconda on wsl and install it: <br>
    >>curl https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh -o Miniconda3-latest-Linux-x86_64.sh   <br>
    >> bash Miniconda3-latest-Linux-x86_64.sh <br>
    >> yes  <br>
    >> yes (activate to base)  <br>
    (Ref -> https://www.tensorflow.org/install/pip#windows-wsl2) <br>
    >> exit <br>
    >> wsl  <br>
    (base)>> <br>
    (This verifies that we have miniconda activated to base)

- Sanity Check 
    a. Check Miniconda 
        - powershell <br>
        - (base)>> <br>
        (This verifies that we have miniconda activated to base)
    b. check for python 
        - (base)>> python --version  <br>
        3.11.4
        - (base)>> python3 --version  <br>
        3.11.4
    c. check for conda 
        - (base)>> conda --version <br>
        conda 23.5.2

3. Create a conda environment
    - (base)>> conda create --name tf python=3.9
    - (base)>> conda activate tf
    - (tf)>>

4. GPU setup 
    - Verify NVIDIA setup <br>
    (tf)>>nvidia-smi <br>
    Note the version of CUDA, cuda 12.2 is not supported by the TF. So we need the CUDA and CuDNN versions that is supported.
    - Install CUDA and cuDNN <br>
    (tf)>> conda install -c conda-forge cudatoolkit=11.8.0 <br>
    (tf)>> pip install nvidia-cudnn-cu11==8.6.0.163 <br>
    - Configure Paths  <br>
        - Option 1 (dont follow)
            - CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)")) <br>
            - export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib  <br>
        - Better Option<br>
            - mkdir -p $CONDA_PREFIX/etc/conda/activate.d  <br>
            - echo 'CUDNN_PATH=$(dirname $(python -c "import nvidia.cudnn;print(nvidia.cudnn.__file__)"))' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh <br>
            - echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/:$CUDNN_PATH/lib' >> $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh

5. Install Tensorflow 
    - pip install --upgrade pip
    - pip install tensorflow==2.13.*

- Reboot Necessary
    - Reboot 
    - powershell
    - >>wsl
    - >>conda activate tf


6. Verify Setup 
    - CPU  <br>
    python3 -c "import tensorflow as tf; print(tf.reduce_sum(tf.random.normal([1000, 1000])))"
    - GPU  <br>
    python3 -c "import tensorflow as tf; print(tf.config.list_physical_devices('GPU'))" <br>
    Look for CPU and GPU devices <br>
    [PhysicalDevice(name='/physical_device:GPU:0', device_type='GPU')]



<hr />

### Installation Pytorch on GPU Desktop
- WSL, Miniconda, verv, CUDA and cuDNN
- Follow steps 1, 2, and 3 
- name the verv as pytorch insteam of tf


