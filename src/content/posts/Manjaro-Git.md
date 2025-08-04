---
title: Manjaro-Git
published: 2025-08-03
description: ''
image: ''
tags: [manjaro,git]
category: 'manjaro'
draft: false 
lang: ''
---
# Manjaro-Git
1. 安装Git
```bash
pacman -S git
```
2. 配置Git
- 创建用户名和邮箱：
```bash
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
- 设置默认编辑器：
```bash
git config --global core.editor vim
- 创建SSH密钥：
```bash
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
3. 配置代理
```bash
git config --global http.proxy http://127.0.0.1:7890
git config --global https.proxy http://127.0.0.1:7890
4. 查看自己的git配置
```bash
git config --list
5