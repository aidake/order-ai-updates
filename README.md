# Order-AI Updates

Order-AI 跨境电商订单分析工具的公开发布仓库。**只放安装包 + 签名 + Tauri Updater manifest**，源码见 private [`aidake/order-ai`](https://github.com/aidake/order-ai)。

## 📥 下载最新版

➡️ **[去最新版 Release 页](https://github.com/aidake/order-ai-updates/releases/latest)**

下载 `Order-AI_<version>_x64_zh-CN.msi` 双击安装即可：

- Windows MSI 安装器（中文向导，约 170MB）
- 自动检测旧版 → 静默卸 → 装新版（WiX UpgradeCode 升级链）
- 用户数据 (`%APPDATA%\Order-AI\`) 卸载不删
- 应用内"检查更新"按钮自动拉本仓 `latest.json` 升级

## 资源说明

每个 Release 包含 3 个 asset：

| 文件 | 用途 |
|---|---|
| `Order-AI_<version>_x64_zh-CN.msi` | Windows 安装包 |
| `Order-AI_<version>_x64_zh-CN.msi.sig` | minisign 签名（防伪造） |
| `latest.json` | Tauri Updater manifest |

仓库根目录的 [`latest.json`](https://raw.githubusercontent.com/aidake/order-ai-updates/main/latest.json) 始终指向最新版（应用内"检查更新"按钮的 endpoint）。

## 在线升级机制

应用启动后，顶栏右上"检查更新"按钮会：

1. 拉 `https://raw.githubusercontent.com/aidake/order-ai-updates/main/latest.json`
2. 比对版本号
3. 有新版 → 弹"升级到 vX.Y.Z"按钮 → 下载 MSI → minisign 签名校验 → 自动重启升级

签名公钥嵌入应用，私钥严管在 CI Secrets — 即使本仓被劫持，没私钥的人无法发布伪造更新。

## 版本日志

详见各 Release 的 release notes，或私库 `docs/V3.*_发布说明_*.md`。

---

⚠️ 本仓只放 release artifacts，**不接受 PR / Issue**。Bug 报告 / 功能请求请去私库（仅 owner 团队可见）。
