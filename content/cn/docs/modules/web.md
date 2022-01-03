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
    parent: "modules"
weight: 110
toc: true
---

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

### 参考

简单实用例子 [iris-admin-example →](https://github.com/snowlyg/iris-admin-example)
