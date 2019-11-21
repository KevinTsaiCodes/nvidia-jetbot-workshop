#Building the Project from Source

Provided with the repo is a library of TensorRT-accelerated deep learning networks for image recognition, object detection with localization (i.e. bounding boxes), and semantic segmentation. This inferencing library (libjetson-inference) is intended to be built & run on the Jetson, and includes support for both C++ and Python.

Various pre-trained DNN models are automatically downloaded to get you up and running quickly. It's also setup to accept customized models that you may have trained yourself, including support for Caffe, TensorFlow UFF, and ONNX.

The latest source can be obtained from GitHub and compiled onboard Jetson Nano, Jetson TX1/TX2, and Jetson AGX Xavier once they have been flashed with JetPack or setup with the pre-populated SD card image for Jetson Nan

##Cloning the Repo

To download the code, navigate to a folder of your choosing on the Jetson. First, make sure git and cmake are installed:


Then clone the jetson-inference project:



Remember to run the git submodule update --init step (or clone with the --recursive flag).

##Python Development Packages

The Python functionality of this project is implemented through Python extension modules that provide bindings to the native C++ code using the Python C API. While configuring the project, the repo searches for versions of Python that have development packages installed on the system, and will then build the bindings for each version of Python that's present (e.g. Python 2.7, 3.6, and 3.7). It will also build numpy bindings for versions of numpy that are installed.

By default, Ubuntu comes with the libpython-dev and python-numpy packages pre-installed (which are for Python 2.7). Although the Python 3.6 interpreter is pre-installed by Ubuntu, the Python 3.6 development packages (libpython3-dev) and python3-numpy are not. These development packages are required for the bindings to build using the Python C API.

So if you want the project to create bindings for Python 3.6, install these packages before proceeding:

Installing these additional packages will enable the repo to build the extension bindings for Python 3.6, in addition to Python 2.7 (which is already pre-installed). Then after the build process, the jetson.inference and jetson.utils packages will be available to use within your Python environments.

##Configuring with CMake

Next, create a build directory within the project and run cmake to configure the build. When cmake is run, a script is launched (CMakePreBuild.sh) that will install any required dependencies and download DNN models for you.





##Downloading Models

The project comes with many pre-trained networks that can you can choose to have downloaded and installed through the Model Downloader tool (download-models.sh). By default, not all of the models are initially selected for download to save disk space. You can select the models you want, or run the tool again later to download more models another time.
When initially configuring the project, cmake will automatically run the downloader tool for you:

To run the Model Downloader tool again later, you can use the following commands:


##Installing PyTorch

If you are using JetPack 4.2 or newer, another tool will now run that can optionally install PyTorch on your Jetson if you want to re-train networks with transfer learning later in the tutorial. This step is optional, and if you don't wish to do the transfer learning steps, you don't need to install PyTorch and can skip this step.

If desired, select the PyTorch package versions for Python 2.7 and/or Python 3.6 that you want installed and hit Enter to continue. Otherwise, leave the options un-selected, and it will skip the installation of PyTorch.

You can also run this tool again later if you decide that you want to install PyTorch at another time:


Running these commands will prompt you with the same dialog as seen above.

##Compiling the Project

Make sure you are still in the jetson-inference/build directory, created above in step #3.
Then run make followed by sudo make install to build the libraries, Python extension bindings, and code samples:




In the build tree, you can find the binaries residing in build/aarch64/bin/, headers in build/aarch64/include/, and libraries in build/aarch64/lib/. These also get installed under /usr/local/ during the sudo make install step.

The Python bindings for the jetson.inference and jetson.utils modules also get installed during the sudo make install step under /usr/lib/python*/dist-packages/. If you update the code, remember to run it again.

$ cd jetson-inference / build / aarch64 / bin <br>
$ ./imagenet-console.py --network = googlenet images / orange_0.jpg output_0.jpg   ＃-- network標誌是可選的
