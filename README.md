# Sooklib 文档中心

Sooklib 是一个以「书库」为核心的自托管书城/书库系统，强调管理、发现与持续阅读体验。

本仓库仅包含文档与更新信息（`update.json`），不包含源代码。

## 项目定位
- 书库为核心，对标 Emby 的书城/书库体验
- 在线阅读仅支持 TXT（针对 TXT 深度优化）
- 其他格式仅提供下载
- 体验优先：找书、元数据提取/筛选、搜索与 UI 交互
- AI 方向：推荐书籍、对话式找书、辅助扫库与标签

## 功能概览
- 书籍扫描、元数据提取与去重
- 多路径书库、后台扫描与进度追踪
- 高级搜索、筛选与标签体系
- TXT 在线阅读（稳定性优先）
- 权限控制与多用户管理
- 封面管理、书签、收藏、阅读统计
- Telegram Bot：搜索、详情、收藏、继续阅读、TXT 章节阅读

## 部署方式
建议使用 Docker 镜像部署：
- GHCR：`ghcr.io/haruka041/sooklib`
- DockerHub：`docker.io/haruka041/sooklib`

快速部署与配置请参考：
- `docs/getting-started.md`
- `docs/docker-deployment.md`
- `docs/configuration.md`

## 更新机制
Sooklib 通过 `update.json` 检测版本更新：
- `stable`：正式版（`v1.2.3`）
- `beta`：测试版（`beta-<commit>`）

详见：`docs/update-channel.md`

## 文档导航
- 快速开始：`docs/getting-started.md`
- Docker 部署：`docs/docker-deployment.md`
- 配置说明：`docs/configuration.md`
- 使用指南：`docs/library-usage.md`
- Telegram Bot：`docs/telegram-bot.md`
- AI 功能：`docs/ai-features.md`
- 更新与通道：`docs/update-channel.md`

## 反馈与支持
如果你有问题或建议，请到主仓库提交 Issue：
`https://github.com/Haruka041/sooklib`
