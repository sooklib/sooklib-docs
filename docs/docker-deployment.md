# Docker 部署

Sooklib 使用容器部署最稳定，支持 GHCR 与 DockerHub 镜像。

## 镜像地址
- GHCR：`ghcr.io/haruka041/sooklib`
- DockerHub：`docker.io/haruka041/sooklib`

## docker-compose 示例

```yaml
version: '3.8'

services:
  sooklib:
    image: ghcr.io/haruka041/sooklib:latest
    container_name: sooklib
    ports:
      - "8080:8080"
    volumes:
      - /path/to/your/novels:/data/novels:ro
      - ./data:/app/data
      - ./covers:/app/covers
      - ./config:/app/config
    environment:
      - TZ=Asia/Shanghai
      - LOG_LEVEL=INFO
      - ADMIN_USERNAME=admin
      - ADMIN_PASSWORD=admin123
      - SECRET_KEY=your-secret-key-change-this-to-random-string
      - APP_CHANNEL=beta
      - UPDATE_URL=https://raw.githubusercontent.com/Haruka041/sooklib-docs/main/update.json
    restart: unless-stopped
```

## 常用命令

```bash
# 启动
docker-compose up -d

# 查看日志
docker-compose logs -f

# 停止
docker-compose down
```

## 版本选择

- 测试版：`sooklib:beta`
- 正式版：`sooklib:v1.2.3` 或 `sooklib:latest`

建议测试环境使用 `beta`，生产环境使用 `latest` 或固定版本号。
