# 签名文件说明

## 文件说明

| 文件 | 作用 | 是否提交 |
|------|------|---------|
| `release-key.jks` | 签名密钥库 | ❌（已加入 .gitignore） |
| `signing.properties` | 本地签名配置 | ❌（已加入 .gitignore） |
| `signing.properties.example` | 签名配置模板 | ✅ |

## 首次使用

1. 复制模板：
   ```bash
   cp signing/signing.properties.example signing/signing.properties
   ```

2. 确保 `signing/release-key.jks` 存在

3. 构建 Release APK：
   ```bash
   ./gradlew assembleRelease
   ```

## 安全提醒

- **永远不要提交** `release-key.jks` 和 `signing.properties` 到 git
- 如果需要更换签名密钥，重新生成 jks 并更新 `signing.properties`
- CI 环境使用 GitHub Secrets 传递签名信息，不依赖本地签名文件