---
title: superset安装部署
categories: []
tags:
  - superset
abbrlink: 49558
date: 2022-10-03 22:23:33
---

# 准备环境

安装python3.9+



参考：https://learn-bigdata.incubator.edurt.io/docs/Superset/Action/get-started/

https://blog.csdn.net/zhang7761/article/details/108883189

https://www.bbsmax.com/A/1O5EZva3d7/



更新python-setuptools

```shell
yum upgrade python-setuptools
```



# 安装superset



```shell
pip install -i https://pypi.doubanio.com/simple/ apache-superset

BABEL_DEFAULT_LOCALE = "zh"


superset run -p 8088 -h 172.20.20.4 --with-threads --reload --debugger

export FLASK_APP=superset
nohup superset run -h 0.0.0.0 -p 8088 --with-threads --reload >> /data/app/superset/superset.log 2>&1 &


# Superset specific config
ROW_LIMIT = 5000

SUPERSET_WEBSERVER_PORT = 8088

# Flask App Builder configuration
# Your App secret key
SECRET_KEY = '\2\1thisismyscretkey\1\2\e\y\y\h'

# The SQLAlchemy connection string to your database backend
# This connection defines the path to the database that stores your
# superset metadata (slices, connections, tables, dashboards, ...).
# Note that the connection information to connect to the datasources
# you want to explore are managed directly in the web UI
SQLALCHEMY_DATABASE_URI = 'mysql+pymysql://root:123456@172.20.30.4:3306/superset?charset=utf8'
```

