add OPENCL LIB PATH to .bashrc

```
nano ~/.bashrc

export LD_LIBRARY_PATH=$PREFIX/lib:/vendor/lib64:/vendor/lib64/egl
```

press `control+x` then type `y` exit from termux && re-open termux

now check opencl

```
git clone https://github.com/Oblomov/clinfo
cd clinfo
make
./clinfo.real

```


then install gcc because clang cannot compile `sgminer-android`

```

curl -LO https://its-pointless.github.io/setup-pointless-repo.sh

bash setup-pointless-repo.sh

pkg i gcc-10 libgccjit-10-dev libgomp-10 bthread

```

now you should install OpenCL driver for (Adreno && Arm-Mali)

```
Adreno

ln -s /system/vendor/lib64/libOpenCL.so $PREFIX/lib/libOpenCL.so

ARM-Mali

ln -s /system/vendor/lib64/egl/libmali.so $PREFIX/lib/libOpenCL.so
```
#### edit this line, after add save && exit
```
nano $PREFIX/include/bthread.h
```
#### add this line 
```
#include <pthread.h>
```



LDFLAGS="-L$PREFIX/lib -lbthread -lpthread -lOpenCL -fcommon" ./configure --disable-adl --disable-adl-checks --disable-git-version 
```

now you can see in your screen `OPENCL FOUND && GPU MINING SUPPORT ENABLED`




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
ln -s /system/vendor/lib/egl/libGLES_mali.so $PREFIX/lib

ln -s /system/vendor/lib64/egl/libGLES_mali.so $PREFIX/lib


ln -s /system/lib64/libGLES_mali.so 
$PREFIX/lib/libGES_mali.so

ln -s /system/lib/libGLES_mali.so 
$PREFIX/lib/libGES_mali.so

ln -s /system/vendor/lib/libGLES_mali.so $PREFIX/lib

ln -s /system/vendor/lib64/libGLES_mali.so $PREFIX/lib
Adreno

ln -s /system/lib/libGLESv1_CM.so.so $PREFIX/lib

ln -s /system/lib/libGLESv3.so.so $PREFIX/lib

ln -s /system/lib/libGLESv2.so.so $PREFIX/lib

ln -s /system/lib64/libGLESv1_CM.so.so $PREFIX/lib/

ln -s /system/lib64/libGLESv2.so.so $PREFIX/lib/

ln -s /system/lib64/libGLESv3.so.so $PREFIX/lib/

ln -s /system/vendor/lib64/libOpenCL.so $PREFIX/lib/

ln -s /system/vendor/lib/libOpenCL.so $PREFIX/lib/

ARM-Mali

ln -s /system/vendor/lib/arm.graphics-V1-ndk_platform.so $PREFIX/lib/

ln -s /system/vendor/lib64/arm.graphics-V1-ndk_platform.so $PREFIX/lib/


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
