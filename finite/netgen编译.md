#使用cmake编译netgen
**环境**:ubuntu22.04

**Cmake版本**:3.22.1

#还是直接用官网的编译方法

## 安装依赖
```bash 
sudo apt-get update && sudo apt-get -y install python3 python3-distutils python3-tk libpython3-dev libxmu-dev tk-dev tcl-dev cmake git g++ libglu1-mesa-dev liblapacke-dev
```

## 获取源码
```bash
export BASEDIR=~/ngsuite
mkdir -p $BASEDIR
cd $BASEDIR
git clone https://github.com/NGSolve/ngsolve.git ngsolve-src
```
## 还有一些源码的验证
```bash
cd $BASEDIR/ngsolve-src
git submodule update --init --recursive
```

## cmake
```bash 
cd $BASEDIR/ngsolve-build
cmake -DCMAKE_INSTALL_PREFIX=${BASEDIR}/ngsolve-install ${BASEDIR}/ngsolve-src
```

## build
```bash
make
make install
```

####下面这个方法不太行
---


## 下载编译tcl/tk
**tcl**:工具控制语言

**tk**:tcl图形工具箱

etc:所以如果需要图形化的netge就需要这两个包

[tcl\tk下载地址](http://www.tcl.tk/software/tcltk/download.html)

```bash
tar -zxvf tcl.tar.gz(tk.tar.gz)
cd tcl(tk)/unix
./configure
make
make test
sudo make install
```


## 下载编译zlib库
**zlib**:解压缩需要用的库
[zlib官网](www.zlib.net)
下载后解压编译
```bash
tar -xvzf zlib.tar.gz
cd zlib
./configure
make 
make install
```

## 导入tcl/tk 以及zlib库
根据自己的目录导入
```bash
export TCL_INCLUDE_PATH=/usr/local/include
export TK_INCLUDE_PATH=/usr/local/include
export ZLIB_INCLUDE_DIR=/usr/local/include
export ZLIB_LIBRARY=/usr/local/lib
```

## 安装opencl包

```bash
sudo apt install ocl-icd-opencl-dev
```

## 编译
```bash
mkdir build && cd build
cmake ..
make 
```

