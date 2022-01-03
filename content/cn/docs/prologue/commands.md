---
title: "命令行"
description: "IRIS-ADMIN带有用于常见任务的命令。"
lead: "带有用于常见任务的命令。"
date: 2020-10-13T15:21:01+02:00
lastmod: 2020-10-13T15:21:01+02:00
draft: false
images: []
menu:
  docs:
    parent: "prologue"
weight: 130
toc: true
---

{{< alert icon="💡" text="可以在 [iris-admin-example](https://github.com/snowlyg/iris-admin-example/blob/main/gin/cmd/migrate/main.go) 里面找到命令行的使用说明" />}}

{{< alert icon="👉" text="迁移和初始化命令都默认会填充基础数据,如果不需要填充数据需要设置 --seed=false。" />}}

### 初始化

初始化项目配置和数据库,并填充基础数据:

```bash
go run cmd/migrate/main.go init [--seed] 
```

### 迁移

迁移数据库数据表:

```bash
go run cmd/migrate/main.go migrate [--seed]
```

### 回滚迁移

回滚迁移:

```bash
go run cmd/migrate/main.go rollback [--to]
```

### 重置

回滚迁移并从新执行迁移:

```bash
go run cmd/migrate/main.go refresh [--seed]
```

### 填充

填充数据:

```bash
go run cmd/migrate/main.go seed
```
