## Ubuntu MongoDb 配置 & 使用

### 安装

```Bash
sudo apt-get install mongodb-server mongodb -y
```

### 启动

* 创建目录，用于存放 MongoDB 数据 & 日志：

```Bash
sudo mkdir -p /data/mongodb
sudo mkdir -p /data/logs/mongodb
```

* 启动 mongodb

```Bash
sudo mongod --fork --dbpath /data/mongodb --logpath /data/logs/mongodb/webapp.log
```

* 检测是否启动成功

```Bash
netstat -ltp | grep 27017
```

### 添加 MongoDB 用户

* 登录本地 mongo 服务

```Bash
sudo mongo
```

* 创建用户

```Bash
use webapp;
db.createUser({user: 'webapp', pwd: 'webapp-pwd', roles: ['dbAdmin', 'readWrite']});
```



