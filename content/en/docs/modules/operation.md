---
title : "Operation logs"
description: "Create opration logs for restful api！"
lead: "Create opration logs for restful api！"
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

- default config name is `operation.yaml` .
- you can use `except` and  `include` to set which route you want to create or not create opreation log.
- operation.yaml

```yaml
except:
  method: post;put
  uri: api/v1/upload;api/v1/upload
include:
  method: get
  uri: api/v1/menus
```

### Add middleware by Use()

-  `index.Use(operation.OperationRecord())` 
### Example

-  [iris-admin-rbac →](https://github.com/snowlyg/iris-admin-rbac)