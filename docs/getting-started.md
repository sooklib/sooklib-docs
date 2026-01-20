# 快速开始

本指南适用于首次部署 Sooklib 的用户，推荐使用 Docker 部署。

## 1. 创建目录

```bash
mkdir sooklib && cd sooklib
```

## 2. 下载 docker-compose.yml

```bash
curl -O https://raw.githubusercontent.com/Haruka041/sooklib/main/docker-compose.yml
```

## 3. 修改配置

重点修改：
- 书库路径（挂载你的小说目录）
- 管理员账号密码
- SECRET_KEY

```bash
vim docker-compose.yml
```

## 4. 启动服务

```bash
docker-compose up -d
```

## 5. 访问 WebUI

浏览器访问：
`http://服务器IP:8080/`

默认管理员账号：
- 用户名：`admin`
- 密码：`admin123`

> 建议首次登录后立即修改密码。

## 6. TXT 在线阅读说明

- 在线阅读仅支持 TXT
- EPUB/PDF/MOBI 等仅提供下载

## 7. Telegram Bot（可选）

需要管理员在 WebUI「系统设置」中配置 Bot Token，详见：
`docs/telegram-bot.md`
