---
title : "RBAC"
description: "集成RBAC模块到项目,生成基础的权限管理接口功能！"
lead: "集成RBAC模块到项目,生成基础的权限管理接口功能！"
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

### 添加 RBAC 模块到项目


- 在项目中 `go get -u github.com/snowlyg/iris-admin-rbac@latest` 获取 IRIS-ADMIN-RBAC 项目依赖.
- 继续在 `site` 目录新建 `main.go` 文件,在文件内输入:
  
```go
package main

import (
  "path/filepath"
  "github.com/snowlyg/iris-admin/server/web"
  "github.com/snowlyg/iris-admin/server/web/web_gin"
  rbac "github.com/snowlyg/iris-admin-rbac/gin"
)

func main() {
  // 初始化 gin web 项目
  wi := web_gin.Init()
  v1 := wi.GetRouterGroup("/api/v1")
  {
    rbac.Party(v1)
  }
  // 启动项目
  web.Start(wi)
}
```

### 同步依赖包数据

```bash
 go mod tidy
```

### 启动项目

```bash
go run main.go
```

IRIS-ADMIN 将会默认坚挺本地 `http://localhost:8085` 地址. 在浏览器中输入次地址就可以看到 `IRIS-ADMIN is running!!!` 的输出字样.

### 接口文档

IRIS-ADMIN-RBAC 接口文档请查看:

- [admin](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/admin/test)
- [api](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/api/test)
- [authority](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/authority/test)
- [public](https://github.com/snowlyg/iris-admin-rbac/tree/main/gin/public/test)
