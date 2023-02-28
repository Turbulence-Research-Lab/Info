---
title:  "如何在信息门户上添加新内容"
# image : "/assets/images/post/post-1.jpg"
author: "Admin"
date: 2022-10-21 11:12:58 +0600
description : "管理和维护网站"
tags: [网站管理]
---

本网站采用Github Page自带的Jekyll服务。理论上可以直接在本网站[代码仓库](https://github.com/Turbulence-Research-Lab/info)中进行文件添加或者修改，待网站自动执行Jekyll服务，网站的内容也就随之更新。但是，由于Github Page出于安全性考虑，Jekyll-tagging 插件的功能被禁用，即网站中自动分类栏目失效。为了更加完整地运行和使用网站，需要编译生成tag目录，再上传同步到github上。具体方案有两种，一种是利用github codespace(推荐), 另一种同步到本地：

# 利用GitHub codespace

## 管理员
- 对于管理员，可以直接在群组info上直接修改，无需通过PR操作
![](/info/media/imag/2022-10-21-update-website/update_website_1.png)
- 进入codespace, 检查配置，可在终端中允许
```
bash _run.sh
```
- 修改对应的内容，比如在_posts下添加或修改文件，在media下添加或修改图片
- 如果需要添加新的tag,需要在_data/parameters.yml中添加对应的tag分类目录，参考已有格式即可。
- 保存修改后,运行_run.sh 生产tag分类目录
```
bash _run.sh
```
- 提交代码（两种途径）
    1. 终端
        1. 添加所有修改过的文件
        ```
        git add .
        ```
        2. 提交修改记录
        ```
        git commit -m "修改内容描述"
        ```
        3. 将当地修改推送到Github远程仓库
        ```
        git push
        ```
    2. vscode GUI界面 
        1. commit
        ![](/info/media/imag/2022-10-21-update-website/update_website_2.png)
        2. 

# 本地同步

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
bash _run.sh
```
4. 在浏览器中查看[http://127.0.0.1:5555/info](http://127.0.0.1:5555/info)即可。

## 修改内容
### 添加post
在_posts目录中参考以往案例，添加新的md文档。

### 添加导航

在_data/parameters.yml中添加和维护

## 编译运行
这里存在两个shell脚本:

_run.sh 删除旧的tag目录，并生成新的tag目录，并将新的tag目录复制到当前根目录

_runtest.sh 删除旧的tag目录。

由于Github不支持tag，我们提前运行
```
bash _run.sh
```
退出后，在当前根目录下会出现tag目录(注：jekyll编译生成的静态网页在_site目录中，其中根目录中名字前带有下划线“_”的文件和文件夹均未在_site中生成.)

## 同步本地仓库到Github远程仓库
1. 添加所有修改过的文件
```
git add .
```
2. 提交修改记录
```
git commit -m "修改内容描述"
```
3. 将当地修改推送到Github远程仓库
```
git push
```

如果在同步过程中出现网络原因，建议使用ssh。 ssh的配置流程可见[通过 SSH 连接到 GitHub](https://docs.github.com/cn/authentication/connecting-to-github-with-ssh)。
