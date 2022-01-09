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

### 配置

调用 `casbin.Instance()` 单列会自动生成 `rbac_model.conf` 文件到项目配置目录.

- rbac_model.conf
  
```conf
[request_definition]
  r = sub, obj, act

  [policy_definition]
  p = sub, obj, act

  [role_definition]
  g = _, _

  [policy_effect]
  e = some(where (p.eft == allow))

  [matchers]
  m = g(r.sub, p.sub) && keyMatch2(r.obj, p.obj) && (r.act == p.act || p.act == "*")
```

### 使用方法

- 使用 [casbin](github.com/casbin/casbin/v2) 第三方包实现
- 并通过 `index.Use(casbin.Casbin())` 使用中间件,实现接口权限认证
- 通过单列 `casbin.Instance()` 操作数据

### 参考

- 权鉴管理模块 [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)