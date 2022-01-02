---
title: "Commands"
description: "IRIS-ADMIN comes with commands for manage database."
lead: "IRIS-ADMIN comes with commands formanage database."
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

{{< alert icon="💡" text="You can use it easy, like this: `iris-admin init`. [iris-admin-example](https://github.com/snowlyg/iris-admin-example/blob/main/gin/cmd/migrate/main.go) It has some helpful commands for build your program. Example  init , migrate , rollback and so on." />}}

{{< alert icon="👉" text="`--seed` or `-s` is a global flag to seed datas into database, default is `true`." />}}
### init
Init is a command for initialize your program:

```bash
go run cmd/migrate/main.go init [--seed] 
```

### migrate

Migrate is a command for migrate your database:

```bash
go run cmd/migrate/main.go migrate [--seed]
```

### rollback

Rollback migrate:

```bash
go run cmd/migrate/main.go rollback [--to]
```

### refresh

Rollback and migrate:

```bash
go run cmd/migrate/main.go refresh [--seed]
```

### 填充

Seed data:

```bash
go run cmd/migrate/main.go seed
```
