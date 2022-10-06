---
title: Linux
tags:
  - Linux
categories:
  - Linux
abbrlink: 15691
date: 2022-10-04 16:42:05
---

# centos修改yum源为阿里

1. 备份原来 yum 文件

   ```shell
   [root@node01 ~]# mv /etc/yum.repos.d/CentOS-Base.repo /etc/yum.repos.d/CentOS-Base.repo_bak
   ```

2. 下载阿里云的 CentOS-Base.repo 到/etc/yum.repos.d/

   ```shell
   [root@node01 ~]# wget -O /etc/yum.repos.d/CentOS-Base.repo http://mirrors.aliyun.com/repo/Centos-7.repo
   ```

3. 清空 yum 缓存

   ```shell
   [root@node01 ~]# yum clean all
   ```

4. 生成新的阿里云的yum缓存，加速下载预热数据

   ```shell
   [root@node01 ~]# yum makecache
   ```

   
