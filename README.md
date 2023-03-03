# Diffusion_models

### 1. setup cuda & pytorch
```python
# 1. Removing existing CUDA
sudo apt --purge remove "cublas*" "cuda*"
sudo apt --purge remove "nvidia*"
rm -rf /usr/local/cuda*
sudo apt-get autoremove && sudo apt-get autoclean
sudo apt-get purge nvidia*
sudo apt remove nvidia-*
sudo rm /etc/apt/sources.list.d/cuda*

# Now you need to reboot
# reboot

# system update
sudo apt-get update
sudo apt-get upgrade

# Check GPU card to see which cuda version is compatable.
sudo apt-get install nvidia-driver-470

wget https://developer.download.nvidia.com/compute/cuda/11.1.1/local_installers/cuda_11.1.1_455.32.00_linux.run
chmod +x cuda_11.1.1_455.32.00_linux.run
sudo ./cuda_11.1.1_455.32.00_linux.run

If you are unable to locate the NVIDIA driver packages with the command sudo apt-get remove --purge nvidia-*, it is possible that the drivers were installed using a different package manager or method.

You can try to search for the installed NVIDIA driver packages using the following command:

perl
Copy code
dpkg -l | grep nvidia
This command will list all packages containing the string "nvidia". You can then use the following command to remove all NVIDIA-related packages:

csharp
Copy code
sudo apt-get remove --purge <package-name>
```
### 
