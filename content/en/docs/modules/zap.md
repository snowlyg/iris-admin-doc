---
title : "Log"
description: "Log record"
lead: "Log record"
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

- Use [go.uber.org/zap](https://pkg.go.dev/go.uber.org/zap
- Global use `zap_server.ZAPLOG` for log record:
  
```go
  zap_server.ZAPLOG.Info(err.Error())
  zap_server.ZAPLOG.Debug(err.Error())
  zap_server.ZAPLOG.Error(err.Error())
  ...
```
