---
title : "数据库服务 "
description: "数据库操作服务！"
lead: "数据库操作服务！"
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

### 使用方法

- 数据服务 [目前仅支持 mysql]
- 使用 `gorm.io/gorm` 第三方包实现
- 通过单列 `database.Instance()` 操作数据
例如:
  
```go
database.Instance().Model(&User{}).Where("name = ?","name").Find(&user)
..
```

### 参考

- 权鉴管理模块 [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)