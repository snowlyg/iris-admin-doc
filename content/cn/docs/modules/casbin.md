---
title : "权限控制"
description: "权限控制管理服务！"
lead: "权限控制管理服务！"
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

- 使用 [casbin](github.com/casbin/casbin/v2) 第三方包实现
- 并通过 `index.Use(casbin.Casbin())` 使用中间件,实现接口权限认证

### 参考

- 权鉴管理模块 [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)