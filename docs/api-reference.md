# API 参考（Swagger）

Sooklib 后端基于 FastAPI，自带 Swagger 文档界面，适用于查看与调试所有接口。

## 入口地址

默认地址（以实际域名/IP 为准）：

- Swagger UI：`http://<host>:8080/docs`
- ReDoc：`http://<host>:8080/redoc`

> 如果你用了反向代理或自定义端口，请替换 `<host>:<port>`。

## 鉴权方式

### 1. JWT Bearer（Web / Admin API）

登录后，使用 `Authorization` Header：

```
Authorization: Bearer <access_token>
```

### 2. Token Query（部分下载/转换接口）

部分资源接口支持 `?token=<access_token>`（用于下载或嵌入式加载）。

### 3. OPDS（阅读器）

OPDS 使用 HTTP Basic Auth：

```
用户名：Sooklib 用户名
密码：Sooklib 密码
```

## 常见接口分区说明

Swagger 中主要模块如下（以路径前缀区分）：

- `/api/auth/*`：登录、注册、刷新 Token
- `/api/admin/*`：后台管理（用户、书库、扫描、标签、规则等）
- `/api/books/*`：书籍详情、版本、下载、阅读信息
- `/api/reader/*`：TXT 在线阅读相关
- `/api/opds/*`：OPDS 目录与下载
- `/api/ai/*`：AI 推荐与对话找书
- `/api/admin/ai/*`：AI 管理配置与规则
- `/api/backup/*`：备份管理

> 完整接口请以 Swagger 文档为准。

## 常用示例

### 登录

```
POST /api/auth/login
{
  "username": "admin",
  "password": "admin123"
}
```

### 获取书库列表

```
GET /api/libraries
Authorization: Bearer <token>
```

### 搜索书籍

```
GET /api/search?q=关键词
Authorization: Bearer <token>
```

### TXT 在线阅读（章节）

```
GET /api/reader/chapters/{book_id}
Authorization: Bearer <token>
```

## 调试建议

- 统一使用 Swagger 界面测试，避免手写参数错误。
- 若接口返回 401/403，请确认 Token 是否过期。
- 500 错误建议查看后端日志（容器日志或 `app/logs`）。

