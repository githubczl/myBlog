---
title: Manjaro-Rime
published: 2025-08-03
description: ''
image: ''
tags: [manjaro,rime]
category: 'manjaro'
draft: false 
lang: ''
---
# Manjaro-ime
1. 安装fcitx自带的拼音输入法和中文拓展，在终端输入以下命令：
```bash
sudo pacman -S fcitx5-im fcitx5-chinese-addons
```
2. 安装fcitx5-rime输入法，在终端输入以下命令：
```bash
sudo pacman -S fcitx5-rime
```
3. 设置环境变量，在你的~/.xprofile文件或者~/.profile文件中添加以下内容：
```bash
export GTK_IM_MODULE=fcitx
export QT_IM_MODULE=fcitx
export XMODIFIERS=@im=fcitx
```
4. 启动FictX5，在终端输入以下命令：
```bash
fcitx5 &
```
5. 配置FcitX5，在终端输入以下命令：
```bash
fcitx5-configtool
```
6. 在FcitX5配置工具中，选择输入法，并选择Rime输入法。
7. 配置雾凇输入法，先安装Ruby,更换下载的Ruby的镜像源
```bash
sudo nano /etc/pacman.d/mirrorlist
```
8. 
9. 添加其他镜像，例如官方镜像或者其他镜像
```bash


```
10. 保存并退出
11. 再次执行安装命令
11. 下载/克隆latest最新的稳定版到本地
```bash

```
12. 进入项目目录
```bash

```
13. 执行部署脚本
```bash

```
14. 此时重启电脑即可完成部署。
