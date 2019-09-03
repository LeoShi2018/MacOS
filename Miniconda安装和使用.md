## Miniconda 安装和使用

### 1. Miniconda安装

````
curl https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh -O Miniconda3-latest-MacOSX-x86_64.sh
------------------------------
bogon:~ LeoShi$ bash Miniconda3-latest-MacOSX-x86_64.sh 
------------------------------
PREFIX=/Users/LeoShi/miniconda3
````

#### 1.1 查看安装后的状态
````
(base) LeoShideMacBook-Pro:envs LeoShi$ which python
---------------------------
/Users/LeoShi/miniconda3/bin/python
---------------------------
(base) LeoShideMacBook-Pro:envs LeoShi$ python -V   
------------------------------   
Python 3.7.4
````

#### 1.2 升级conda
````
(base) LeoShideMacBook-Pro:envs LeoShi$ conda update --all
------------------------------
Collecting package metadata (current_repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /Users/LeoShi/miniconda3


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    chardet-3.0.4              |        py37_1003         173 KB
    conda-4.7.11               |           py37_0         3.0 MB
    python-libarchive-c-2.8    |          py37_13          23 KB
    ------------------------------------------------------------
                                           Total:         3.2 MB
.......
Downloading and Extracting Packages
chardet-3.0.4        | 173 KB    | ###################################################################### | 100% 
conda-4.7.11         | 3.0 MB    | ###################################################################### | 100% 
python-libarchive-c- | 23 KB     | ###################################################################### | 100% 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
````

### 2. Miniconda的使用

#### 2.1 创建虚拟环境

> conda create -n 虚拟环境名称 软件包=版本

````
(base) LeoShideMacBook-Pro:envs LeoShi$ conda create -n env_talib python=3.5 -y
------------------------------
Downloading and Extracting Packages
setuptools-40.2.0    | 490 KB    | ###################################################################### | 100% 
certifi-2018.8.24    | 137 KB    | ###################################################################### | 100% 
pip-10.0.1           | 1.6 MB    | ###################################################################### | 100% 
wheel-0.31.1         | 65 KB     | ###################################################################### | 100% 
openssl-1.0.2s       | 1.9 MB    | ###################################################################### | 100% 
python-3.5.6         | 12.2 MB   | ###################################################################### | 100% 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
#
# To activate this environment, use
#
-----激活虚拟环境命令-------------------------
#     $ conda activate env_talib
#
# To deactivate an active environment, use
#
-----退出虚拟环境-------------------------
#     $ conda deactivate
````

#### 2.2 激活虚拟环境

> conda activate 虚拟环境名称

````
(base) LeoShideMacBook-Pro:envs LeoShi$ conda activate env_talib
-----(env_talib) 就是当前虚拟环境的状态-------------------------
(env_talib) LeoShideMacBook-Pro:envs LeoShi$
````

#### 2.3 conda安装软件

> conda install 软件包

````
(env_talib) LeoShideMacBook-Pro:envs LeoShi$ conda install -c quantopian ta-lib
------------------------------
Collecting package metadata (current_repodata.json): done
Solving environment: failed with initial frozen solve. Retrying with flexible solve.
Solving environment: failed with repodata from current_repodata.json, will retry with next repodata source.
Collecting package metadata (repodata.json): done
Solving environment: done

## Package Plan ##

  environment location: /Users/LeoShi/miniconda3/envs/env_talib

  added / updated specs:
    - ta-lib


The following packages will be downloaded:

    package                    |            build
    ---------------------------|-----------------
    blas-1.0                   |              mkl           6 KB
    intel-openmp-2019.4        |              233         887 KB
    libgfortran-3.0.1          |       h93005f0_2         426 KB
    mkl-2019.4                 |              233       101.9 MB
    numpy-1.14.2               |   py35ha9ae307_0         3.2 MB
    ta-lib-0.4.9               |      np114py35_0         1.1 MB  quantopian
    ------------------------------------------------------------
                                           Total:       107.5 MB

The following NEW packages will be INSTALLED:

  blas               pkgs/main/osx-64::blas-1.0-mkl
  intel-openmp       pkgs/main/osx-64::intel-openmp-2019.4-233
  libgfortran        pkgs/main/osx-64::libgfortran-3.0.1-h93005f0_2
  mkl                pkgs/main/osx-64::mkl-2019.4-233
  numpy              pkgs/main/osx-64::numpy-1.14.2-py35ha9ae307_0
  ta-lib             quantopian/osx-64::ta-lib-0.4.9-np114py35_0


Proceed ([y]/n)? y
Downloading and Extracting Packages
blas-1.0             | 6 KB      | ###################################################################### | 100% 
intel-openmp-2019.4  | 887 KB    | ###################################################################### | 100% 
mkl-2019.4           | 101.9 MB  | ###################################################################### | 100% 
libgfortran-3.0.1    | 426 KB    | ###################################################################### | 100% 
ta-lib-0.4.9         | 1.1 MB    | ###################################################################### | 100% 
numpy-1.14.2         | 3.2 MB    | ###################################################################### | 100% 
Preparing transaction: done
Verifying transaction: done
Executing transaction: done
````

#### 2.4 清除临时数据

> conda clean -p

````
(env_talib) LeoShideMacBook-Pro:envs LeoShi$ conda clean -p -y
````

#### 2.5 导出环境列表供其他人使用

> conda env export > 文件路径/名称

````
(env_talib) LeoShideMacBook-Pro:envs LeoShi$ conda env export > env_talib.yml
------------------------------
(env_talib) LeoShideMacBook-Pro:envs LeoShi$ cat env_talib.yml 
name: env_talib
channels:
  - quantopian
  - defaults
dependencies:
  - blas=1.0=mkl
  - ca-certificates=2019.5.15=1
  - certifi=2018.8.24=py35_1
  - intel-openmp=2019.4=233
  - libcxx=4.0.1=hcfea43d_1
  - libcxxabi=4.0.1=hcfea43d_1
  - libedit=3.1.20181209=hb402a30_0
  - libffi=3.2.1=h475c297_4
  - libgfortran=3.0.1=h93005f0_2
  - mkl=2019.4=233
  - ncurses=6.1=h0a44026_1
  - numpy=1.14.2=py35ha9ae307_0
  - openssl=1.0.2s=h1de35cc_0
  - pip=10.0.1=py35_0
  - python=3.5.6=hc167b69_0
  - readline=7.0=h1de35cc_5
  - setuptools=40.2.0=py35_0
  - sqlite=3.29.0=ha441bb4_0
  - ta-lib=0.4.9=np114py35_0
  - tk=8.6.8=ha441bb4_0
  - wheel=0.31.1=py35_0
  - xz=5.2.4=h1de35cc_4
  - zlib=1.2.11=h1de35cc_3
prefix: /Users/LeoShi/miniconda3/envs/env_talib
````




## END

