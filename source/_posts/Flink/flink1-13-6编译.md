---
title: flink1.13.6 编译
tags:
  - Flink
categories:
  - Flink
abbrlink: 55161
date: 2022-10-03 23:35:42
---

# Flink-1.13.6编译打包

```shell
git clone https://github.com/apache/flink.git
cd flink/ &&git checkout release-1.13.6
mvn clean install -DskipTests -Dfast -Dhadoop.version=3.2.2
```

