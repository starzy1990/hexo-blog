---
title: azkaban4.0编译安装
categories: []
tags:
  - azkaban
abbrlink: 4777
date: 2022-10-03 22:37:51
---

参考：https://blog.csdn.net/chenxi5404/article/details/120512109

https://blog.csdn.net/NKDark0214/article/details/122601181?spm=1001.2101.3001.6650.2&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EESLANDING%7Edefault-2-122601181-blog-120512109.pc_relevant_multi_platform_whitelistv4eslandingrelevant2&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EESLANDING%7Edefault-2-122601181-blog-120512109.pc_relevant_multi_platform_whitelistv4eslandingrelevant2&utm_relevant_index=5

# 修改gradle配置文件

```shell
sed -i.bak \
"s/linkedin.bintray.com\/maven/linkedin.jfrog.io\/artifactory\/open-source\//" \
azkaban-4.0.0/build.gradle \
&& rm -f azkaban-4.0.0/build.gradle.bak
```



部署参考：https://blog.csdn.net/qq_38075749/article/details/121539432



安装部署参考：https://www.cnblogs.com/sam0/p/15951120.html



curl -G "127.0.0.1:12321/executor?action=activate" && echo
