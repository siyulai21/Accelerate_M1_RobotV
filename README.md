# Accelerate_M1_RobotV

This project is to accelerate my prev robot vision CNN inference using TVM on Apple M1. **Still working**

Download Miniforge from official page (https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-MacOSX-arm64.sh)

Create an environment for TVM and all dependencies

Install TVM dependencies
```
conda install numpy decorator attrs cython pytest
conda install llvmdev
conda install cmake
```
Checkout the last stable version
```
git clone --recursive https://github.com/apache/tvm.git
cd tvm
git checkout v0.19.0
```
Build
```
mkdir build
cd build
cp ../cmake/config.cmake .
```
Edit the config.cmake file
```
USE_METAL ON
USE_LLVM ON
USE_OPENMP gnu
```
Make
```
cmake -DCMAKE_OSX_ARCHITECTURES=arm64 ..
```
