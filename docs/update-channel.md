# 更新与版本通道

Sooklib 使用 `update.json` 维护版本信息，客户端定期检查更新。

## 通道说明
- **stable**：正式版，标签格式 `v1.2.3`
- **beta**：测试版，标签格式 `beta-<commit>`

## update.json 示例

```json
{
  "stable": {
    "version": "v1.2.3",
    "url": "https://github.com/Haruka041/sooklib/releases/tag/v1.2.3",
    "notes": "稳定版更新说明",
    "published_at": "2026-01-20"
  },
  "beta": {
    "version": "beta-acde123",
    "url": "https://github.com/Haruka041/sooklib",
    "notes": "测试版更新说明",
    "published_at": "2026-01-20"
  }
}
```

## 版本检测
- 后端：`/api/version`, `/api/update/check`
- 管理后台：系统设置页展示更新提示

## 常见问题
- **为什么收不到更新提示？**
  - 检查 `UPDATE_URL` 是否可访问
  - 检查 `APP_CHANNEL` 是否设置为 `stable` 或 `beta`
