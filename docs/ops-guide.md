# 部署与运维指南

本指南聚焦 Sooklib 的日常运维，包括部署、更新、备份、日志与常见问题。

## 1. 推荐部署方式

建议使用 Docker / Docker Compose：

- 镜像：`ghcr.io/sooklib/sooklib`
- DockerHub：`haruka041/sooklib`

详细部署步骤见：`docs/docker-deployment.md`

## 2. 更新策略

Sooklib 支持 **beta**（测试版）与 **stable**（正式版）：

- `beta`：跟随主分支更新
- `v1.2.3`：正式版标签

更新方式：

1. 修改 `docker-compose.yml` 中镜像标签
2. `docker-compose pull && docker-compose up -d`

## 3. 数据库与迁移

当版本升级涉及数据库变更时：

```
docker exec -it sooklib alembic upgrade head
```

> 若容器启动失败，可临时关闭重启策略，使用同镜像 + 数据卷运行迁移。

## 4. 备份与恢复

### 本地备份

后台管理 → 备份管理：

- 创建备份
- 下载备份
- 恢复备份

### WebDAV 云备份

可配置 WebDAV 地址、用户名、密码：

- 自动上传备份到云端
- 支持定时任务

## 5. 日志与排错

### 查看容器日志

```
docker logs -f sooklib
```

### 常见问题

- **接口 500**：查看后端日志
- **AI 调用失败**：检查 API Key 是否有效
- **扫描卡住**：检查书库路径与权限

## 6. 配置建议

常用环境变量：

- `ADMIN_USERNAME`
- `ADMIN_PASSWORD`
- `SECRET_KEY`
- `LOG_LEVEL`
- `TZ`

详见：`docs/configuration.md`

