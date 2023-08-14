## 02 Installation Tensorflow with Applications

- (New) [Install Tensorflow/Keras in WSL2 for Applications of Deep Neural Networks](https://www.youtube.com/watch?v=KinTNHO-6IY&t=316s&ab_channel=JeffHeaton)
- [Git Link](https://github.com/jeffheaton/t81_558_deep_learning/blob/master/install/tensorflow-install-march-2023.ipynb)
- WSL, Miniconda, verv, CUDA and cuDNN

#### Steps:
- Follow steps 1, and 2. Install NVIDIA drivers and create a WSL env 
- (base)>>conda install jupyter 
- Download tool.yml file (cuda + cuDNN any other tools )


1. Install NVIDIA drivers and WSL2

    - Download and install [NVIDIA drivers](https://www.nvidia.com/download/index.aspx) for your GPU
    <br> <br>
    - Open "Windows PowerShell"
    - \Users\vibud> wsl --install <br>
    (installs ubuntu by default)
    - Reboot the system and set password
2. Installing Miniconda, and Jupyter
Miniconda
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
    <br><br>
    (base)>> <br>
    (This verifies that we have miniconda activated to base) <br>
    Close the powershell and open it again  <br>
    >> wsl  <br>

Install Jupyter 
    - (base)>>conda install -y jupyter



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

3. Install tensorflow and create a conda environment
    - Install tensorflow using Jeff's Yaml file <br>
    (base)>>wget https://raw.githubusercontent.com/jeffheaton/t81_558_deep_learning/master/tools.yml 
    - (base)>> conda env create -f tools.yml -n tensorflow

        -Now this tools.yml is outdated with cudnn version
        -So, open this file to view its contents <br>
        >> cat tool.yml <br>
        Check cuDNN version for your file from [cuDNN File](https://developer.nvidia.com/rdp/cudnn-download) 
        - Now open, edit and save the correct file<br> 
        >>nano tools.ml <br>
        - cudnn=8.9.4
    - (base)>> conda activate tensorflow
    - (tensorflow)>> <br>

Now, lets add Jupyter support to your new environment.
    - (tensorflow)>> conda install -c conda-forge nb_conda
    - (tensorflow)>> python -m ipykernel install --user --name tensorflow --display-name "Python 3.9 (tensorflow)"
    - now our newly created virtual environment will show up on Jupyter

4. Setup Library Paths 

    - Verify NVIDIA setup <br>
    (tensorflow)>>nvidia-smi <br>
    Note the version of CUDA, cuda 12.2 is not supported by the TF. So we need the CUDA and cuDNN versions that is supported. <br>
    The message does not change if you have already installed the correct version of CUDA and cuDNN. In this case the .yaml file had cuda and cuDNN
    - ~~Install CUDA and cuDNN ~~ <br>
    ~~(tf)>> conda install -c conda-forge cudatoolkit=11.8.0 ~~ <br>
    ~~(tf)>> pip install nvidia-cudnn-cu11==8.6.0.163 ~~ <br>
    - Configure Paths  <br>
        - Better Option<br>
            - mkdir -p $CONDA_PREFIX/etc/conda/activate.d  <br>
            - echo 'export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:$CONDA_PREFIX/lib/' > $CONDA_PREFIX/etc/conda/activate.d/env_vars.sh


5. Reboot Necessary
    - Reboot 
    - powershell
    - >>wsl
    - >>conda activate tf


6. Verify Setup 
    - open powershell
    - (base)>> wsl
    - (tensorflow)>> conda activate tensorflow
    - (tensorflow)>> jupyter notebook

**Python Code**
import sys

import tensorflow.keras
import pandas as pd
import sklearn as sk
import tensorflow as tf

print(f"Tensor Flow Version: {tf.__version__}")
print(f"Keras Version: {tensorflow.keras.__version__}")
print()
print(f"Python {sys.version}")
print(f"Pandas {pd.__version__}")
print(f"Scikit-Learn {sk.__version__}")
gpu = len(tf.config.list_physical_devices('GPU'))>0
print("GPU is", "available" if gpu else "NOT AVAILABLE")




- tools.yml file contents <br>
channels:
    - conda-forge
dependencies:
    - cudatoolkit=11.8.0 
    - cudnn=8.6.0.163
    - jupyter
    - scikit-learn
    - scipy
    - pandas
    - pandas-datareader
    - matplotlib
    - pillow
    - tqdm
    - requests
    - h5py
    - pyyaml
    - flask
    - boto3
    - pip
    - pip:
        - tensorflow
        - bayesian-optimization
        - gym
        - kaggle
        