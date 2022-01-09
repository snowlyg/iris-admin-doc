---
title : "WEB服务"
description: "快速集成WEB框架！"
lead: "快速集成WEB框架！"
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

自动生成 `web.json` 文件到项目配置目录.

- web.json
  
```json
{
  "captcha": //验证码设置
 { "img-height": 80,
  "img-width": 240,
  "key-long": 4
  },
"except": //权限过滤设置,集成权鉴模块会自动生成系统权限.次设置可以过滤不需要设置为权限的路由
  {
  "method": "",
  "uri": ""
  },
"limit": //接口频率看
  {
    "burst": 5,
  "disable": true,
  "limit": 0
  },
"max-size": 1024, //文件上传大小限制
"system":
 { 
   "addr": "127.0.0.1:8085", //监听地址
  "db-type": "mysql", //数据库类型,仅支持 mysql
  "level": "release", //服务模式 debug , test release
  "time-format": "2006-01-02 15:04:05", //时间格式
  "tls": false //https 是否开启
  }
}
```

### 使用方法

- [github.com/kataras/iris/v12](https://github.com/kataras/iris) 第三方包实现
- [gin-gonic/gin](https://github.com/gin-gonic/gin) 第三方包实现
- Web框架服务需要实现 `type WebFunc interface {}`  接口
  
```go
// WebFunc 框架服务接口
// - GetTestClient 测试客户端
// - GetTestLogin 测试登录
// - AddWebStatic 添加静态页面
// - AddUploadStatic 上传文件路径
// - Run 启动
type WebFunc interface {
  GetTestClient(t *testing.T) *httptest.Client
  GetTestLogin(t *testing.T, url string, res httptest.Responses, datas ...interface{}) *httptest.Client
  AddWebStatic(perfix string)
  AddUploadStatic()
  InitRouter() error
  Run()
}
```

### 简单实用
  
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

### 参考

简单实用例子 [iris-admin-example →](https://github.com/snowlyg/iris-admin-example)
