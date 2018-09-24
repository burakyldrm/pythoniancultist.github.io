---
layout: default
---

## Using Keras on GPU with Tensorflow Backend

If you have a CUDA compatible Nvidia GPU, it is possible to speed up your machine learning tasks significantly. Before you read any futher, please check the list of CUDA compatible devices from the link below to make sure you have the proper hardware.

[List of supported devices](https://developer.nvidia.com/cuda-gpus)

This tutorial will teach you how to deploy your Keras models with Tensorflow-GPU backend (If you are feeling adventurous, Tensorflow-GPU itself can be utilized for the same task as well). Before we begin, make sure you have the following ready (Feel free to replace items with your own preferred software):

* Ubuntu 18.04 Lts
* Latest Anaconda distribution for Python 3.6
* Empty Anaconda environment with Python 3.6

### 1. Install Java

Run the following on a terminal:

>sudo apt update
>
>sudo apt install openjdk-8-jdk

### 2. Install Nvidia Graphics Drivers

Run the following on a terminal:

>sudo add-apt-repository ppa:graphics-drivers/ppa
>
>sudo apt update
>
>sudo apt upgrade

Optional: Check drivers to be installed using "ubuntu-drivers devices" command on a terminal.

>== /sys/devices/pci0000:00/0000:00:01.0/0000:01:00.0 ==
>
>modalias : pci:v000010DEd0000139Asv00001462sd00001138bc03sc02i00
>
>vendor   : NVIDIA Corporation
>
>model    : GM107M [GeForce GTX 950M]
>
>driver   : nvidia-driver-396 - third-party free recommended
>
>driver   : nvidia-driver-390 - third-party free
>
>driver   : xserver-xorg-video-nouveau - distro free builtin

If you see an output resembling the one above, you are good to go for the next step. Run the following on a terminal to install the aforementioned drivers:

>sudo ubuntu-drivers autoinstall

Reboot your machine.

### 3. Install CUDA

Using the link below, download the base installer for CUDA. Do not change the platform selection.

[Download CUDA](https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1704&target_type=runfilelocal)

Go to your download folder. Run the following on a terminal (Don't panic if you don't see any response in terminal about installation, it is intended):

>sudo sh cuda_9.0.176_384.81_linux.run --override --silent --toolkit
>
>export PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
>
>export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

### 4. Install cuDNN

Using the link below, download the compressed cuDNN folder. You are going to need a Nvidia account for this.

 [Download cuDNN](https://developer.nvidia.com/compute/machine-learning/cudnn/secure/v7.1.4/prod/9.0_20180516/cudnn-9.0-linux-x64-v7.1)

Go to your download folder. Run the following on a terminal:

>tar -xzvf cudnn-9.0-linux-x64-v7.1.tgz
>
>sudo cp cuda/include/cudnn.h /usr/local/cuda/includesudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
>
>sudo chmod a+r /usr/local/cuda/include/cudnn.h /usr/local/cuda/lib64/libcudnn*

Open your "bashrc" file using:

>gedit ~/.bashrc

Go to the end of the file, add the following lines and save before exiting.

>export LD_LIBRARY_PATH="$LD_LIBRARY_PATH:/usr/local/cuda/lib64:/usr/local/cuda/extras/CUPTI/lib64"
>
>export CUDA_HOME=/usr/local/cuda
>
>export PATH=/usr/local/cuda-9.0/bin${PATH:+:${PATH}}
>
>export LD_LIBRARY_PATH=/usr/local/cuda-9.0/lib64\${LD_LIBRARY_PATH:+:${LD_LIBRARY_PATH}}

Run the following on a terminal:

>source ~/.bashrc
>
>sudo ldconfig

### 5. Install Keras and Tensorflow-GPU

Run the following on a terminal to create an empty Anaconda environment if you didn't create one yet.

>conda create -n environment_name pip python==3.6

Activate your fresh environment on the terminal using:

>source activate environment_name

Install Tensorflow-GPU

>conda install tensorflow-gpu

Install Keras

>conda install keras

### 6. Experiment

Open Pycharm, select your environment from project interpreter option. Let Pycharm index for few minutes, then copy-paste the following code to Pycharm in the link below:

[Keras Example Code](https://github.com/keras-team/keras/blob/master/examples/mnist_mlp.py)

Open a terminal and run the following command:

>watch -n 0.5 nvidia-smi

Run the example code in Pycharm and look the "nvidia-smi" output. If you see a task with name "Anaconda" in it taking up memory, it means that Keras is utilizing your GPU.

Enjoy the accelerated machine learning experience!

[back](./)
