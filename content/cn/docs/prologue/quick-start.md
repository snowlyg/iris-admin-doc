---
title: "快速开始"
description: "关于如何启动一个新的IRIS-ADMIN项目。"
lead: "关于如何启动一个新的IRIS-ADMIN项目。"
date: 2020-11-16T13:59:39+01:00
lastmod: 2020-11-16T13:59:39+01:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 110
toc: true
---

### 要求

IRIS-ADMIN 项目基于go语言开发,需要提前安装好go语言环境.

- 根据你的需要下载安装好 [golang](https://go.dev/doc/install) 环境,并设置好系统环境变量.

### 下载依赖

```sh
  go get -u github.com/snowlyg/iris-admin@latest
```

### 构建一个新的项目

- 在你系统的 GOPATH 路径下新建一个目录 `site`.
- 然后在 `site` 目录下执行 `go mod init` 命令初始化依赖管理文件.
- 接着执行 `go get -u github.com/snowlyg/iris-admin@latest` 获取 IRIS-ADMIN 项目依赖.
- 继续在 `site` 目录新建 `main.go` 文件,在文件内输入:
  
```go
package main

import (
  "path/filepath"
  "github.com/snowlyg/iris-admin/server/web"
  "github.com/snowlyg/iris-admin/server/web/web_gin"
)

func main() {
  // 初始化 gin web 项目
  wi := web_gin.Init()
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

IRIS-ADMIN 将会默认坚挺本地 `http://localhost:8085/v0/versions` 地址. 在浏览器中输入次地址就可以看到 `IRIS-ADMIN is running!!!` 的输出字样.

### 其他命令

IRIS-ADMIN 内置了一些常用的数据迁移管理命令 [命令 →]({{< relref "commands" >}})
