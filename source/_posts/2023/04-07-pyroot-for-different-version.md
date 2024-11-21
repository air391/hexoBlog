---
title: 使用python3.11无法调用ROOT
date: 2023-04-07 19:40:25
tags:
- cern-root
- cmake
- pyroot
categories: cern-root
---
## 问题描述

早期使用旧版本root，pyroot仅支持到python3.8，更新python3.11后始终不能导入ROOT，报错如下：

```python
ImportError: Failed to import libcppyy3_11. Please check that ROOT has been built for Python 3.11
```

提示没有python3.11的支持。

## 解决方案

使用最新版本的源码进行编译，并指定python3版本

### 源码版本

截至2023年4月7日，使用`git clone --branch latest-stable --depth=1 https://github.com/root-project/root.git root_src`拉取得到的版本似乎为root6.26，对python3.11的编译支持仍有问题，详情见[root formun 讨论](https://root-forum.cern.ch/t/code-h-etc-have-been-moved-in-python-3-11/50895)，本讨论中似乎提到可以通过拉取master branch完成编译，但本人未进行尝试。
通过在[root release](https://root.cern/install/all_releases/)界面下载6.28/02的源码可以完成编译。顺带一提，截至6.28/02该版本的预编译版本，所提供的pyroot也只支持到python3.8。

### python指定

当电脑上同时有多个版本的python时，以本机3.8与3.11并存为例，如果在使用cmake时不指定python3版本，可能会通过`find_package(Python3 COMPONENTS Interpreter Development NumPy)`默认找到较低版本，即python3.8并为该版本产生pyroot，这一顺序决定顺序可能与cmake find_package的工作模式有关，通过[官网源码编译介绍](https://root.cern/install/build_from_source/#cmake--314)，添加`-DPython3_EXECUTABLE=<python3interpreter>`命令行参数完成编译。

## 踩坑实录

在上述解决方案的探索中，也算是踩了一些坑，可以写出来记录一下。
首先是在指定python3版本中，在使用6.26的源码进行编译时，我尝试将传入virtualenv中的python3.11路径进行编译，然而结果在cmake中是Python3_Interpreter_FOUND为真，而Python3_VERSION却是空的，导致出错，因而使用`/usr/bin/python3.11`路径进行编译，完成后在虚拟环境中依然可用。
此外如果指定python3版本总是无法找到正确版本的话，可以考虑手动修改cmakelist文件。无论是6.26还是6.28root的cmakelist寻找python支持的部分都在`<src-dir>/cmake/modules/SearchRootCoreDeps.cmake`中完成，并通过`include(SearchRootCoreDeps)`加入到cmakelist中，故而可以考虑修改`find_package(Python3 COMPONENTS Interpreter Development NumPy)`为`find_package(Python3 3.11 COMPONENTS Interpreter Development NumPy)`指定版本。当然更合理的方式可能是通过命令行参数设置cmake搜索的rootdir，不过该方法本人没有进行尝试故不过多介绍。