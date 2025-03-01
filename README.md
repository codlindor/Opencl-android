# Opencl-android







# Adreno && Mali OpenCL GPU drivers for android

> building dependency
```
pkg update
```
```
pkg upgrade
```
```
sudo apt-get install build-essential
```
```
sudo apt-get install libtool
```
```
sudo apt-get install cmake
```
```
sudo apt-get install yasm
```
```
sudo apt-get install make
```
```
sudo apt-get install wget
```
```
sudo apt-get install git
```
```
sudo apt-get install libjansson
```
```
sudo apt-get install libgmp
```
```
sudo apt-get install opencl-headers
```
```
sudo apt-get install libmicrohttpd
```
```
sudo apt-get install libuv*
```
```
sudo apt-get install clang
```
```
sudo apt-get install binutils
```


android pthread-cancel not supported , for android you shoud install `libbthread`

```
git clone https://github.com/tux-mind/libbthread
```
```
cd libbthread
```
```
autoreconf -i
```
```
nano bthread.h
```

under `<bthread.h>` add 
```
#include <pthread.h>
```

then run

```
./configure
```
```
$PREFIX
```
```
make install
```
then install `gcc` because `clang` cannot compile `cgminer-android`

```
curl -LO https://its-pointless.github.io/setup-pointless-repo.sh
```
```
pkg i gcc-11 libgccjit-11-dev
```

now you should install OpenCL driver for (Adreno && Arm-Mali)


```
ln -s /system/vendor/lib64/libOpenCL.so $PREFIX/lib/libOpenCL.so
```
```
ln -s /system/vendor/lib64/egl/libmali.so $PREFIX/lib/libOpenCL.so
```
```
ln -s /system/vendor/lib64/egl/libmali.so $PREFIX/lib/libmali.so

```

add OPENCL LIB  PATH to .bashrc

```
nano ~/.bashrc

export LD_LIBRARY_PATH=$PREFIX/lib:/vendor/lib64:/vendor/lib64/egl
```

press `control+x` then type `y` exit from termux && re-open termux
