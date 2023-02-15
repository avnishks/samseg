# samseg
test repo for standalone Samseg code.

## Manual Installation

#### Requirements
- A C++ compiler compatible with C++ 11
- Python ≥ 3.6
- CMake
- Make (Linux/MacOS)
- Visual Studio (Windows)

#### Preparation
This repository imports ITk as git-submodule. To start it, use:
```
git submodule init
git submodule update
```
#### Linux/MacOS
1. Build ITK:
```
mkdir ITK-build
cd ITK-build
cmake \
    -DBUILD_SHARED_LIBS=OFF \
    -DBUILD_TESTING=OFF \
    -DBUILD_EXAMPLES=OFF \
    -DCMAKE_BUILD_TYPE=Release \
    -DCMAKE_INSTALL_PREFIX=../ITK-install \
    ../ITK
make install
cd ..
```

2. Create a wheel:
```
ITK_DIR=ITK-install python setup.py bdist_wheel
```
The wheel will be created under the /dist
directory.

3. Install the wheel:
```
python -m pip install <filename.whl>
```

#### Windows OS
1. Build ITK:
```
md ITK-build
cd ITK-build
cmake.exe ^
    -DBUILD_SHARED_LIBS=OFF ^
    -DBUILD_TESTING=OFF ^
    -DBUILD_EXAMPLES=OFF ^
    -DCMAKE_BUILD_TYPE=Release ^
    -DCMAKE_INSTALL_PREFIX=..\ITK-install ^
    ..\ITK
cmake --build . --config Release --target Install
cd ..
```

3. Install Samseg:
```
set ITK_DIR=ITK-install
python setup.py install
```
