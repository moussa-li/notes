#超算上的netgen编译
##加载需要的编译器

```bash
module load compiler/cmake/3.23.3 #用cmake编译
module load compiler/intel/2021.3.0 #intel编译库
module load python/3.8.10 #加载python
module load compiler/gcc/9.3.0 #加载gcc-9.3.0
```

##赋值环境变量

```bash
export PYTHON_INCLUDE_DIRS=/public/software/apps/python/3.8.10/include/python3.8
export PYTHON_LIBRARIES=/public/software/apps/python/3.8.10/lib/python3.8
export LD_LIBRARY_PATH=/work/home/moussa/intel-oneapi/opt/intel/oneapi/compiler/2022.1.0/linux/compiler/lib/intel64_lin
export BASEDIR=~/netgen
```

##创建netgen目录

```bash
mkdir netgen && cd netgen
mkdir src build install
```
并将源码文件放入src

##cmake编译

```bash
cd build
cmake -DCMAKE_INSTALL_PREFIX=${BASEDIR}/install -DPYTHON_INCLUDE_DIR=$(python -c "from distutils.sysconfig import get_python_inc; print(get_python_inc())")  -DPYTHON_LIBRARY=$(python -c "import distutils.sysconfig as sysconfig; print(sysconfig.get_config_var('LIBDIR'))")  ${BASEDIR}/src
```

##make编译并安装

```bash
make 
make install 
```



