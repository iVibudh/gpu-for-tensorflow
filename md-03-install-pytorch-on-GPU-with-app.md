### 03 Install Pytorch on GPU with Applicatio for WSL (Windows Desktop)

References
- [GPU vs CPU Parallel Computing for Beginners](https://www.youtube.com/watch?v=r9IqwpMR9TE&t=616s&ab_channel=PythonSimplified)

- (base)>>conda create -n llama-2-on-GPU python=3.9
- y
- (base)>>conda activate llama-2-on-GPU
- (llama-2-on-GPU)>>conda install -c pytorch pytorch
- Now check if Cuda is installed automatically then that's great. If not
    - Check for Pytorch version on the pytorch websites 
    - [ref1](https://joelognn.medium.com/installing-wsl2-pytorch-and-cuda-on-windows-11-65a739158d76): Medium Article
	- [ref2](https://pytorch.org/get-started/locally/): Pytorch official guide
-  (llama-2-on-GPU)>>conda install -c anaconda jupyter
- (llama-2-on-GPU)>>jupyter notebook
- Look at the notebook 01_GPU_vs_CPU.ipynb