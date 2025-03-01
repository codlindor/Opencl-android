# Opencl-android








# Adreno && Mali OpenCL GPU && aarch64 CPU miner for android

>> Original developers

This code is provided entirely free of charge by the programmer in his spare
time so donations would be greatly appreciated. Please consider donating to the
address below.

Con Kolivas <kernel@kolivas.org>
15qSxP1SQcUX3o4nhkfdbgyoWEFMomJ4rZ

GIT TREE:

https://github.com/ckolivas/cgminer

Support thread:

http://bitcointalk.org/index.php?topic=28402.0

IRC Channel:

irc://irc.freenode.net/cgminer 

Forked from https://github.com/JordanRulz/cgminer.git

# warning

# This Projects have no warranty, so everyone use your own risk

> building dependency 
`pkg up && pkg upg && pkg i build-essential libtool cmake yasm make wget git libjansson libgmp opencl-headers libmicrohttpd libuv* clang binutils`

android pthread-cancel not supported , for android you shoud install `libbthread`

```
git clone https://github.com/tux-mind/libbthread

cd libbthread

autoreconf -i

nano bthread.h
```

under `<bthread.h>` add `#include <pthread.h>`

then run

```
./configure --prefix$PREFIX

make install
```
then install `gcc` because `clang` cannot compile `cgminer-android`

```

curl -LO https://its-pointless.github.io/setup-pointless-repo.sh

pkg i gcc-11 libgccjit-11-dev

```

now you should install OpenCL driver for (Adreno && Arm-Mali)


```
Adreno

ln -s /system/vendor/lib64/libOpenCL.so $PREFIX/lib/libOpenCL.so

ARM-Mali

ln -s /system/vendor/lib64/egl/libmali.so $PREFIX/lib/libOpenCL.so

```

add OPENCL LIB  PATH to .bashrc

```
nano ~/.bashrc

export LD_LIBRARY_PATH=$PREFIX/lib:/vendor/lib64:/vendor/lib64/egl
```




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
