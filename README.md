# Accelerate-AppleM1

Install Miniforge from official (https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)

Create an environment for TVM and all dependencies to run

Install PyTorch
```
conda install -c pytorch pytorch torchvision
```
Install TVM dependencies
```
conda install numpy decorator attrs cython pytest
conda install llvmdev
conda install cmake
```
Checkout my last stable version
```
git clone --recursive https://github.com/apache/tvm.git
cd tvm
git checkout v0.19.0
```
Edit the config.cmake file in the build
```
mkdir build
cd build
cp ../cmake/config.cmake .
USE_METAL ON
USE_LLVM ON
USE_OPENMP gnu
```
cmake -DCMAKE_OSX_ARCHITECTURES=arm64 ..
