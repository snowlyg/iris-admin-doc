---
title : "Database"
description: "Import database to program"
lead: "Import database to program"
date: 2020-10-06T08:48:45+00:00
lastmod: 2020-10-06T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "modules"
weight: 110
toc: true
---

### Config

When use `database.Instance()` first time `mysql.yaml` config file will be create.

- mysql.yaml


```yaml
config: charset=utf8mb4&parseTime=True&loc=Local
db-name: 
log-mode: false
log-zap: error
max-idle-conns: 0
max-open-conns: 0
password: 
path: 127.0.0.1:3306
username: root
```

### How To Use

- Only support mysql now
-  `gorm.io/gorm` 
-  `database.Instance()` 
  
```go
database.Instance().Model(&User{}).Where("name = ?","name").Find(&user)
..
```

### Example

- [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)