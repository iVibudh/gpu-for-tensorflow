### 03 Install Pytorch on GPU with Applicatio for WSL (Windows Desktop)

References
- [GPU vs CPU Parallel Computing for Beginners](https://www.youtube.com/watch?v=r9IqwpMR9TE&t=616s&ab_channel=PythonSimplified)

- (base)>>conda create -n llama-2-on-GPU python=3.9
- y
- (base)>>conda activate llama-2-on-GPU

- Now follow installation Guide #1 to install Cuda-toolkit and cudNN 
- Now check for Pytorch version on the pytorch websites 
    - [ref1](https://joelognn.medium.com/installing-wsl2-pytorch-and-cuda-on-windows-11-65a739158d76): Medium Article
	- [ref2](https://pytorch.org/get-started/locally/): Pytorch official guide
- Install the appropriate version of pytorch 
    - (llama-2-on-GPU)>> conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
- (llama-2-on-GPU)>>jupyter notebook
- Look at the notebook 01_GPU_vs_CPU.ipynb