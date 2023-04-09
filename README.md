# A Sample Guide to Use Torch with GPU on Mac Sillion Chip

## Installation 

1. Create and Activate New Environment
```bash
$ conda create -n torch-gpu python=3.8
$ conda activate torch-gpu
```

2. Install Requirements
```bash
$ conda install pytorch torchvision torchaudio -c pytorch-nightly
```

3. Jupyter Notebook (Optional)
```bash
$ conda install -c conda-forge jupyter jupyterlab
```

# Varify if PyTorch can find the Metal Performance Shaders plugin.
```python
import torch
# this ensures that the current MacOS version is at least 12.3+
print(torch.backends.mps.is_available())
# this ensures that the current current PyTorch installation was built with MPS activated.
print(torch.backends.mps.is_built())
```
<span> 
    If both commands return True, then PyTorch has access to the GPU!
</span>


# Final test
```python
python test_gpu.py
```
<span> If you don’t see any error, everything works as expected! </span>