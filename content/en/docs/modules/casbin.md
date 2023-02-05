---
title : "Casbin"
description: "Import casbin to program"
lead: "Import casbin to program"
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

When first time use `casbin.Instance()` ,the `rbac_model.conf` config file will be create.

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

### How To Use

- [casbin](github.com/casbin/casbin/v2) 
- `index.Use(casbin.Casbin())` 
- `casbin.Instance()` 

### Example

- [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)