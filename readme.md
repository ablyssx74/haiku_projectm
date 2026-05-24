## A guide to build and install projectm for x86 and x86_64 on Haiku OS 

### x86_64 Builds
```
git clone https://github.com/projectM-visualizer/projectm.git projectm
cd projectm
git fetch --all --tags
git submodule init
git submodule update
mkdir build
cd build
cmake  -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/boot/system/lib/ ..
cmake --build . -- -j4
# Create package that points to /boot/system/lib

#Local Installs
#cmake -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/boot/home/config/non-packaged ..
#cmake --build . -- -j4
#cmake --build . --target install
```

### x86 Builds
```
git clone https://github.com/projectM-visualizer/projectm.git projectm
cd projectm
git fetch --all --tags
git submodule init
git submodule update
mkdir build
cd build
setarch x86 cmake -DCMAKE_C_COMPILER=gcc-x86 -DCMAKE_CXX_COMPILER=g++-x86 -DENABLE_BOOST_FILESYSTEM=OFF -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/boot/system/lib/x86 ..
cmake --build . -- -j4
# Create package that points to /boot/system/lib/x86

#Local Installs
#setarch x86 cmake -DCMAKE_C_COMPILER=gcc-x86 -DCMAKE_CXX_COMPILER=g++-x86 -DENABLE_BOOST_FILESYSTEM=OFF -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/boot/home/config/non-packaged ..
#cmake --build . -- -j4
#cmake --build . --target install
```
