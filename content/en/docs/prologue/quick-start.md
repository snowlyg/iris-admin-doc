---
title: "Quick Start"
description: "One page summary of how to start a new IRIS-ADMIN project."
lead: "One page summary of how to start a new IRIS-ADMIN project."
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

## Requirements

IRIS-ADMIN is golang project:

- Download and install  [golang](https://go.dev/doc/install) (it includes go) for your platform.

### Get package

```sh
  go get -u github.com/snowlyg/iris-admin@latest
```

## Create a directory and  Change directories

```bash
mkdir site
cd site
```

### Create a new file on `site`

- `main.go` :
```go
package main

import (
	"path/filepath"
	"github.com/snowlyg/iris-admin/server/web"
	"github.com/snowlyg/iris-admin/server/web/web_gin"
)

func main() {
	wi := web_gin.Init()
	web.Start(wi)

```


### Install dependencies

```bash
 go mod tidy
```

### Start development server

```bash
go run main.go
```

IRIS-ADMIN will start the Hugo development webserver accessible by default at `http://localhost:8085/v0/versions`. Saved changes will live reload in the browser.

## Other commands

IRIS-ADMIN comes with commands for common tasks. [Commands →]({{< relref "commands" >}})
