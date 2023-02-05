---
title : "RBAC"
description: "Import RBAC module to program"
lead: "Import RBAC module to program"
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

Auto create `web.yaml` config file .

- web.yaml
  
```yaml
captcha: # 
  img-height: 80
  img-width: 240
  key-long: 4
except: # except routes which don't need to create promissions 
  method: ""
  uri: ""
limit: # require limit 
  burst: 5
  disable: true
  limit: 0
max-size: 1024 # Max size of upload file 
system:
  addr: 127.0.0.1:8085 
  db-type: mysql # type of database,only support mysql now
  level: release # support: debug , test release
  time-format: "2006-01-02 15:04:05" # time format
  tls: false # https 

```

### How to Use

- [github.com/kataras/iris/v12](https://github.com/kataras/iris)
- [gin-gonic/gin](https://github.com/gin-gonic/gin)
-  `type WebFunc interface {}`  interface
  
```go
// WebFunc 
// - GetTestClient 
// - GetTestLogin 
// - AddWebStatic 
// - AddUploadStatic 
// - Run 
type WebFunc interface {
  GetTestClient(t *testing.T) *httptest.Client
  GetTestLogin(t *testing.T, url string, res httptest.Responses, datas ...interface{}) *httptest.Client
  AddWebStatic(perfix string)
  AddUploadStatic()
  InitRouter() error
  Run()
}
```

### Simple to start
  
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
}
```

### Example

- [iris-admin-example →](https://github.com/snowlyg/iris-admin-example)
