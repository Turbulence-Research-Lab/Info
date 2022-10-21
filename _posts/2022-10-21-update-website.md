---
title:  "如何在信息门户上添加新内容"
# image : "/assets/images/post/post-1.jpg"
author: "Admin"
date: 2022-10-21 11:12:58 +0600
description : "配置新工作站"
tags: [网站管理]
---

本网站采用Github Page自带的Jekyll服务。理论上可以直接在本网站[代码仓库](https://github.com/Turbulence-Research-Lab/info)中进行文件添加或者修改，待网站自动执行Jekyll服务，网站的内容也就随之更新。但是，由于Github Page出于安全性考虑，Jekyll-tagging 插件的功能被禁用，即网站中自动分类栏目失效。为了更加完整地运行和使用网站，建议先通过本地编译生成tag目录，再上传同步到github上。具体流程如下：

## 安装和配置Jekyll

可参考Jekyll官网下载和配置， [Jekyll中文官网](https://www.jekyll.com.cn/)

### Ubuntu
1. 在terminal中输入
```bash
sudo apt-get install ruby-full build-essential zlib1g-dev
```
2. 在~/.bashrc中添加gem的安装路径。
可在terminal中输入：
```
echo '# Install Ruby Gems to ~/gems' >> ~/.bashrc
echo 'export GEM_HOME="$HOME/gems"' >> ~/.bashrc
echo 'export PATH="$HOME/gems/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```
3. 利用gem安装Jekyll:

```
gem install jekyll bundler
```

### Windows
建议使用WSL子系统，WSL配置过程见[ubuntu子系统配置](https://zhuanlan.zhihu.com/p/76032647)，Jekyll安装和配置过程如上节。

## 从Github上同步仓库到本地
1. 从github远程仓库下载
```
git clone https://github.com/Turbulence-Research-Lab/info.git
```
如果网络不好，可用ssh下载，但需要自行配置ssh
```
git clone git@github.com:Turbulence-Research-Lab/info.git
```
2. 进入info目录
```
cd info
```
3. 运行
```
bundle exec jekyll serve
```
4. 在浏览器中查看[http://127.0.0.1:5555/info](http://127.0.0.1:5555/info)即可。


