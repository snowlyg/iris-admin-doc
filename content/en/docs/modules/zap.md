---
title : "服务日志"
description: "服务日志记录！"
lead: "服务日志记录！"
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

- 使用 [go.uber.org/zap](https://pkg.go.dev/go.uber.org/zap) 第三方包实现
- 通过全局变量 `zap_server.ZAPLOG` 记录对应级别的日志:
  
```go
  zap_server.ZAPLOG.Info(err.Error())
  zap_server.ZAPLOG.Debug(err.Error())
  zap_server.ZAPLOG.Error(err.Error())
  ...
```
