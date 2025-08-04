---
title: Docker-install-Centos7
published: 2025-08-02
description: ''
image: ''
tags: [docker,centos]
category: 'docker'
draft: false 
lang: ''
---
# Docker-install-Centos7
1. 更换 CentOS 的 yum 源为阿里云
- 备份原有的 yum 源配置文件：
```bash
cd /etc/yum.repos.d/
mv CentOS-Base.repo CentOS-Base.repo.backup
```
- 下载阿里云的 yum 源配置文件：
```bash
wget -O CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
```
- 清理缓存并生成新的缓存：
```bash
yum clean all
yum makecache
```
2. 安装 Docker必要的安装包
```bash
yum install -y yum-utils device-mapper-persistent-data lvm2
```
3. 设置Docker-ce的阿里云镜像源
```bash
yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
```
4. 更新yum包索引
```bash
yum makecache fast
```
5. 安装Docker-ce
```bash
yum install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
6. 启动Docker并设置开机自启
```bash
systemctl start docker

systemctl enable docker
```
7. 验证Docker是否安装成功
```bash
docker run hello-world
```
8. 配置Docker镜像加速
- 创建Docker配置文件：
```bash
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://j75n3v3u.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
```
9. 测试docker安装
```bash
docker run hello-world
```
- 预期输出
```bash
Hello from Docker!
This message shows that your installation appears to be working correctly.
To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 。。。。。
 9. The Docker daemon pulled the "hello-world" image from the Docker Hub.
 （镜像）
 ```
10. 检查镜像和容器
```bash
docker images
docker ps -a
```



