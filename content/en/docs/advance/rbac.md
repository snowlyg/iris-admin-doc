---
title : "RBAC"
description: "Import RBAC model to program"
lead: "Import RBAC model to program"
date: 2020-10-06T08:48:45+00:00
lastmod: 2020-10-06T08:48:45+00:00
draft: false
images: []
menu:
  docs:
    parent: "advance"
weight: 110
toc: true
---

### How To Use


-  `go get -u github.com/snowlyg/iris-admin-rbac@latest` .
  
```go
package main

import (
  "path/filepath"
  "github.com/snowlyg/iris-admin/server/web"
  "github.com/snowlyg/iris-admin/server/web/web_gin"
  rbac "github.com/snowlyg/iris-admin-rbac/gin"
)

func main() {
  wi := web_gin.Init()
  v1 := wi.GetRouterGroup("/api/v1")
  {
    rbac.Party(v1)
  }
  web.Start(wi)
}
```

### Go Mod Tidy

```bash
 go mod tidy
```

### Quickly Start

```bash
go run main.go
```

IRIS-ADMIN will listen on `http://localhost:8085` . put this url to browser you will see `IRIS-ADMIN is running!!!` .

### Doc

IRIS-ADMIN-RBAC doc:

- [admin](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/admin/test)
- [api](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/api/test)
- [authority](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/authority/test)
- [public](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/public/test)
