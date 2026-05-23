# Order-AI Updates

Order-AI Windows 桌面安装包与 Tauri Updater 公开更新端点。

本仓库只托管公开发布资产：

- Windows MSI 安装包
- MSI 签名文件
- `latest.json` updater manifest

不在本仓库托管源码、内部文档、样本数据、业务输入、运行输出或用户数据。

## 下载最新版

[打开最新版 Release 页](https://github.com/aidake/order-ai-updates/releases/latest)

下载 `Order-AI_<version>_x64_zh-CN.msi` 后双击安装即可。

## 在线升级

应用内“检查更新”使用以下公开 manifest：

`https://raw.githubusercontent.com/aidake/order-ai-updates/main/latest.json`

Updater 会校验签名后再安装更新。

## Release 资产

每个 Release 只应包含：

| 文件 | 用途 |
|---|---|
| `Order-AI_<version>_x64_zh-CN.msi` | Windows 安装包 |
| `Order-AI_<version>_x64_zh-CN.msi.sig` | 安装包签名 |
| `latest.json` | Tauri Updater manifest |

## 安全边界

本公开仓库不应出现：

- API Key、token、password、secret、私钥或证书私钥
- `.env`、`APIKEY.txt`、本机配置或用户目录路径
- 订单、退款、拒付、日志、缓存、报表、样本 Excel、parquet 或数据库文件
- 源码仓库内部路径、内部文档路径或私有仓库名称

如发现上述内容，应立即下架对应资产并轮换相关凭证。
