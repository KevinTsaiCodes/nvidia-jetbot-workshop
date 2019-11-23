# Workshop Tools
## Tools you need:
#### Keras, Tensorflow-gpu, OpenCV-Python, Pandas, Matplotlib, Numpy, Scipy
### Install python3-pip. In order to install Keras, Tensorflow-gpu, OpenCV-Python, Pandas, Matplotlib, Numpy, Scipy
##### pip3 install command
    $ sudo apt-get install python3-pip
### OpenCV
![opencv](https://user-images.githubusercontent.com/53148219/69027016-4c0a9700-0a08-11ea-998e-0c0360039ce5.jpg)
##### opencv-python install command
    $ sudo apt-get install python3-opencv
### Pandas, Matplotlib, Numpy, Scipy
<img width="565" alt="Skærmbillede-2017-09-04-kl -17 06 45" src="https://user-images.githubusercontent.com/53148219/69063934-4c328300-0a58-11ea-8bac-9b200d9fb714.png">

##### Pandas, Matplotlib, Numpy, Scipy install command
    $ sudo apt-get install python3-pandas
    $ sudo apt-get install python3-numpy
    $ sudo apt-get install python3-scipy
    $ sudo apt-get install python3-matplotlib
### Keras, Tnsorflow-GPU
##### Keras, Tensorflow-GPU install command
#### Install keras tools:
    $ sudo apt-get install python3-h5py
#### Install keras
    $ sudo -H pip3 install keras
#### Install tensorflow-gpu tools:
#### Install CUDA for GPU command
    $ cd ~ && vi .bashrc
    $ vi .bashrc
    $ export PATH=${PATH}:/usr/local/cuda/bin
    $ export LD_LIBRARY_PATH=${LD_LIBRARY_PATH}:/usr/local/cuda/lib64
###### Also do this on Terminal
![cuda](https://user-images.githubusercontent.com/53148219/69472488-cec08880-0d5f-11ea-8b76-337be6242c19.png)
#### Verify
    $ nvcc -V # make sure CUDA has been installed
#### Install tensorflow-gpu:
    $ sudo apt-get install python3-pip libhdf5-serial-dev hdf5-tools
    $ pip3 install --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v42 tensorflow-gpu==1.13.1+nv19.3 --user
##### Verify your Install
    $ python3
    $ import keras
    tensorflow backend
    $ import tensorflow as tf
    $ import cv2
##### If there isn't any error, that is, opencv, keras and tensorflow-gpu were installed Successfully
    $ import pandas as pd
    $ import numpy as np
    $ import scipy as sp
    $ from matplotlib import pyplot
##### If there isn't any error, that is, pandas, numpy, scipy and matplotlib were installed Successfully
### Jupyter-Notebook
#### Install Jupyter-Notebook:
    $ sudo apt-get install jupyter
#### Launch Jupyter-Notebook:
    $ jupyter-notebook
### If you run out of
### E: Could not get lock var lib dpkg lock frontend — open (11: Resource temporarily unavailable)
### during the installation process, the following is the [solution](https://github.com/KevinTsaiCodes/nvidia-jetbot-workshop/wiki/E:-Could-not-get-lock--var-lib-dpkg-lock-frontend-%E2%80%94-open-(11:-Resource-temporarily-unavailable)).
