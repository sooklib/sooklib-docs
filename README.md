# Sooklib 文档中心

Sooklib 是一个以书库为核心的自托管书城/书库系统，强调管理、发现与持续阅读体验。
在线阅读仅支持 TXT 并做深度优化，其它格式仅提供下载阅读。

本仓库仅包含文档与更新信息（`update.json`），不包含源代码。

## 文档入口

- 快速开始：`docs/getting-started.md`
- Docker 部署：`docs/docker-deployment.md`
- 配置说明：`docs/configuration.md`
- 运维指南：`docs/ops-guide.md`
- API 参考（Swagger）：`docs/api-reference.md`
- 用户手册：`docs/user-manual.md`
- Telegram Bot：`docs/telegram-bot.md`
- AI 功能：`docs/ai-features.md`
- 更新通道：`docs/update-channel.md`

## 更新机制

Sooklib 通过 `update.json` 检测版本更新：

- `stable`：正式版（`v1.2.3`）
- `beta`：测试版（`beta-<commit>`）

详见：`docs/update-channel.md`

## 镜像与版本

- **GHCR**：`ghcr.io/sooklib/sooklib`
- **DockerHub**：`docker.io/haruka041/sooklib`

## 文档结构

- `docs/`：所有用户与运维文档
- `update.json`：版本更新检测配置（CI 自动更新）

## 反馈与支持

如需帮助或反馈问题，请到主仓库提交 Issue：
https://github.com/sooklib/sooklib
