# 配置说明

Sooklib 支持 `config/config.yaml` 与环境变量配置。

## 环境变量

| 变量 | 说明 | 默认值 |
| --- | --- | --- |
| ADMIN_USERNAME | 管理员用户名 | admin |
| ADMIN_PASSWORD | 管理员密码 | admin123 |
| SECRET_KEY | JWT 密钥 | 必须修改 |
| LOG_LEVEL | 日志级别 | INFO |
| TZ | 时区 | Asia/Shanghai |
| APP_VERSION | 当前版本号 | 1.0.0 |
| APP_CHANNEL | 更新通道 | beta |
| UPDATE_URL | update.json 地址 | https://raw.githubusercontent.com/Haruka041/sooklib-docs/main/update.json |

## config.yaml 常用字段

```yaml
server:
  host: 0.0.0.0
  port: 8080

directories:
  data: /app/data
  covers: /app/covers
  temp: /tmp/sooklib

scanner:
  interval: 3600
  recursive: true
  supported_formats:
    - .txt
    - .epub
    - .mobi
    - .azw3
```

## 更新通道

- `APP_CHANNEL=beta`：优先测试版
- `APP_CHANNEL=stable`：仅正式版

详见 `docs/update-channel.md`。
