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

Check this alternative one:

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

#-------------------------

1. Install Cuda and Nvidia driver

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



3. Fom Lambda stack

#What will be installed
TensorFlow v2.5.0
PyTorch v1.9.0
CUDA v11.1
cuDNN v8.2.1
Dependencies and other frameworks like Caffe and Theano

LAMBDA_REPO=$(mktemp) && \
wget -O${LAMBDA_REPO} https://lambdalabs.com/static/misc/lambda-stack-repo.deb && \
sudo dpkg -i ${LAMBDA_REPO} && rm -f ${LAMBDA_REPO} && \
sudo apt-get update && \
sudo apt-get --yes upgrade && \
sudo apt-get install --yes --no-install-recommends lambda-server && \
sudo apt-get install --yes --no-install-recommends nvidia-headless-470 && \
sudo apt-get install --yes --no-install-recommends lambda-stack-cuda
### 
