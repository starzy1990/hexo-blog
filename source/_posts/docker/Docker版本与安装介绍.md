---
title: Docker版本与安装介绍
tags:
  - docker
categories:
  - docker
abbrlink: 41166
date: 2022-10-03 23:24:30
---

# Docker版本

- Docker-CE：docker 社区版本，由社区维护和提供技术支持，为免费版本，适合个人开发人员和小团队使用
- Docker-EE：docker 企业版本，为收费版本，有售后团队和技术团队提供技术支持，专为企业开发和IT团队而设计
- 此外Docker 的发布版本分别为 Stable 和 Edage 版，区别在于前者是按季度发布的稳定版本（发布慢），后者是按月发布的边缘版（发布快）
- 通常情况下，Docker-CE 足以满足我们的需求。



# Centos7 安装 Docker 

1. 安装必要的一下系统工具

   ```shell
   [root@docker ~]# yum install -y yum-utils device-mapper-persistent-data lvm2
   ```

2. 安装必要的一下系统工具

   ```shell
   [root@docker ~]# yum-config-manager --add-repo http://mirrors.aliyun.com/docker-ce/linux/centos/docker-ce.repo
   ```

3. 检查  /etc/yum-repos.d/docker-ce.repo 中的 URL 地址是不是都是阿里云的，如果不是，那么把download-stage.docker.com全部替换成mirrors.aliyun.com/docker-ce/

   vim /etc/yum.repos.d/docker-ce.repo

4. 更新并安装Docker-CE

   ```shell
   [root@docker ~]# yum makecache fast
   [root@docker ~]# yum -y install docker-ce
   ```

5. 开启Docker服务

   ```shell
   [root@docker ~]# systemctl start docker
   ```

# Ubuntu 安装 Docker-CE





# Docker 加速器配置

1. 安装／升级Docker客户端

   推荐安装1.10.0以上版本的Docker客户端，参考文档[docker-ce](https://yq.aliyun.com/articles/110806)

2. 配置镜像加速器

   针对Docker客户端版本大于 1.10.0 的用户

   您可以通过修改daemon配置文件/etc/docker/daemon.json来使用加速器

   ```shell
   [root@docker ~]# mkdir -p /etc/docker
   [root@docker ~]# sudo tee /etc/docker/daemon.json <<-'EOF'
   > {
   >   "registry-mirrors": ["https://ztk30wcn.mirror.aliyuncs.com"]
   > }
   > EOF
   
   [root@docker ~]# systemctl daemon-reload
   [root@docker ~]# systemctl restart docker
   ```

   

