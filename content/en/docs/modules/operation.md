---
title : "系统操作日志"
description: "根据接口自动生成操作日志！"
lead: "根据接口自动生成操作日志！"
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

### 配置

自动生成 `operation.yaml` 文件到项目配置目录.
- 可以设置过滤路径到 `except`,设置需要包括的路径到 `include`.
- operation.yaml


```yaml
except:
  method: post;put
  uri: api/v1/upload;api/v1/upload
include:
  method: get
  uri: api/v1/menus
```

### 使用方法

- 并通过 `index.Use(operation.OperationRecord())` 使用中间件,实现接口自动生成操作日志

### 参考

- 权鉴管理模块 [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)