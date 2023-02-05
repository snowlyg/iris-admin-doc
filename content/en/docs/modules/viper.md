---
title : "Service for config"
description: "Initialize service's config and auto create a config file！"
lead: "Initialize service's config and auto create a config file！"
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

### How To Use

-  [github.com/spf13/viper](https://github.com/spf13/viper) .
-  `func getViperConfig() viper_server.ViperConfig` :
  
```go
package cache

import (
  "fmt"

  "github.com/fsnotify/fsnotify"
  "github.com/snowlyg/iris-admin/g"
  "github.com/snowlyg/iris-admin/server/viper_server"
  "github.com/spf13/viper"
)

var CONFIG Redis

type Redis struct {
  DB       int    `mapstructure:"db" json:"db" yaml:"db"`
  Addr     string `mapstructure:"addr" json:"addr" yaml:"addr"`
  Password string `mapstructure:"password" json:"password" yaml:"password"`
  PoolSize int    `mapstructure:"pool-size" json:"poolSize" yaml:"pool-size"`
}

// getViperConfig 
func getViperConfig() viper_server.ViperConfig {
  configName := "redis"
  db := fmt.Sprintf("%d", CONFIG.DB)
  poolSize := fmt.Sprintf("%d", CONFIG.PoolSize)
  return viper_server.ViperConfig{
    Directory: g.ConfigDir,
    Name:      configName,
    Type:      g.ConfigType,
    Watch: func(vi *viper.Viper) error {
      if err := vi.Unmarshal(&CONFIG); err != nil {
        return fmt.Errorf("Unmarshal json error: %v", err)
      }
      
      vi.SetConfigName(configName)
      vi.WatchConfig()
      vi.OnConfigChange(func(e fsnotify.Event) {
        fmt.Println("config is change:", e.Name)
        if err := vi.Unmarshal(&CONFIG); err != nil {
          fmt.Printf("Unmarshal json error: %v \n", err)
        }
      })
      return nil
    },
    Default: []byte(`
db: ` + db + `
addr: "` + CONFIG.Addr + `"
password: "` + CONFIG.Password + `"
pool-size: ` + poolSize),
  }
}
```