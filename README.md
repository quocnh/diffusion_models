# Diffusion_models
```python
### 0. Remove CUDA and Nvidia toolkits if any in the system
There are two things- nvidia drivers and cuda toolkit- which you may want to remove. If you have installed using apt-get use the following to remove the packages completely from the system:

To remove cuda toolkit:

sudo apt-get --purge remove "*cublas*" "cuda*" "nsight*" 
To remove Nvidia drivers:

sudo apt-get --purge remove "*nvidia*"
If you have installed via source files (assuming the default location to be /usr/local) then remove it using:

sudo rm -rf /usr/local/cuda*
From cuda 11.4 onwards, an uninstaller script has been provided. Use it for the uninstallation instead:

#### To uninstall cuda
sudo /usr/local/cuda-11.4/bin/cuda-uninstaller 
#### To uninstall nvidia
sudo /usr/bin/nvidia-uninstall
If you get the problem of broken packages, it has happened since you added repo to the apt/sources.lst. Run the following to delete it:

sudo vim /etc/apt/sources.list
Go to the line containing reference to Nvidia repo and comment it by appending # in front of the line, for e.g.:

#deb http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1804/x86_64/ /
Then run

sudo apt-get update 
This will fix the problem.

### 1. Install Lambda stack
wget -nv -O- https://lambdalabs.com/install-lambda-stack.sh | I_AGREE_TO_THE_CUDNN_LICENSE=1 sh -
sudo reboot

```




### 
