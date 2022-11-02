---
title:  "FFTW3在Linux下的安装与配置"
# image : "/assets/images/post/post-1.jpg"
author: "Admin"
date: 2022-11-2 11:12:58 +0600
description : "fftw"
tags: [软件安装, 服务器]
---

## 安装

FFTW3 最新版下载网站[fftw.org](fftw.org)

以FFTW 3.3.10版本为例

###  解压

```shell
tar -zxvf fftw-3.3.10.tar.gz
```

```
cd fftw-3.3.10
```


### 安装
- 默认安装， 默认安装到/usr/local/bin

```shell
./configure
make -j64 ##多线程编译，取决有多少核
sudo make install
```

如果要自定义安装路径

```shell
./configure --prefix=/opt/fftw
make -j64
sudo make install
```

### 卸载

```shell
sudo make uninstall
```

其他./configure 选项见[https://www.fftw.org/fftw3_doc/Installation-on-Unix.html](https://www.fftw.org/fftw3_doc/Installation-on-Unix.html)

或者

```
./configure --help
```

### 配置
在编译时添加以下编译选项即可

```
-I/opt/fftw/include -L/opt/fftw/lib -lfftw3 -lm 
```



