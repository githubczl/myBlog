---
title: Docker-install-Centos7-2.0
published: 2025-08-03
description: ''
image: ''
tags: [docker,centos]
category: 'docker'
draft: false 
lang: ''
---
# Docker-install-Centos7-2.0
1. 首先要安装一个yum工具
```bash
cd /etc/yum.repos.d
mv CentOS-Base.repo CentOS-Base.repo.backup 2>/dev/null
curl -o CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
yum clean all
yum makecache
yum repolist
sudo yum install -y yum-utils device-mapper-persistent-data lvm2
```
2. 安装docker
```bash
yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
3. 启动docker并设置开机启动
```bash
# 启动Docker
systemctl start docker

# 停止Docker
systemctl stop docker

# 重启
systemctl restart docker

# 设置开机自启
systemctl enable docker

# 执行docker ps命令，如果不报错，说明安装启动成功
docker ps
```
4. 配置docker镜像加速
```bash
# 创建目录
mkdir -p /etc/docker

# 复制内容
tee /etc/docker/daemon.json <<-'EOF'
{
    "registry-mirrors": [
        "http://hub-mirror.c.163.com",
        "https://mirrors.tuna.tsinghua.edu.cn",
        "http://mirrors.sohu.com",
        "https://ustc-edu-cn.mirror.aliyuncs.com",
        "https://ccr.ccs.tencentyun.com",
        "https://docker.m.daocloud.io",
        "https://docker.awsl9527.cn"
    ]
}
EOF

# 重新加载配置
systemctl daemon-reload

# 重启Docker
systemctl restart docker
```

