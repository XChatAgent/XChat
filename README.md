# XChat

XChat 是一个 Windows 桌面客户端，提供服务端账号登录、WireGuard 隧道连接、
智能分流和 DNS 防泄漏等功能。

当前客户端版本：**1.3.16**

## 下载

安装程序位于：

```text
release/XChat-1.3.16-setup.exe
```

校验文件：

```text
release/SHA256SUMS.txt
```

SHA-256：

```text
fd923f455c219fac0ef37bcd6d9b832995243314e969ee93c9ce74cc05349f6b
```

## 安装

1. 运行 `XChat-1.3.16-setup.exe`
2. 选择程序安装目录（可沿用上次目录）
3. 等待安装完成
4. 在完成页勾选“启动 XChat”

安装后：

```text
程序目录：用户选择，例如 D:\XChat
后台服务：C:\Program Files\XChat\ChatAgent
WireGuard：C:\Program Files\XChat\WireGuard
用户数据：%LOCALAPPDATA%\XChat
```

后台服务 `XChatAgent` 需要管理员权限安装，安装程序会自动处理。

## 登录

打开 XChat，输入管理员提供的：

- 服务器地址
- 用户名
- 密码

认证成功后，客户端会自动获取隧道配置并连接。

## 文档

- [安装与升级](docs/INSTALL.md)
- [客户端使用说明](docs/USER_GUIDE.md)
- [常见问题](docs/FAQ.md)
- [更新记录](CHANGELOG.md)

## 系统要求

- Windows 10/11 x64
- 管理员权限（首次安装、更新后台服务）
- 可访问认证服务器和 WireGuard 端点的网络

## 安全说明

- 登录通道使用 TLS。
- 客户端会固定 TLS 证书指纹，证书变化时会拒绝连接。
- 用户数据保存在 `%LOCALAPPDATA%\XChat`，卸载程序不会主动删除。
- 服务器地址、测试账号和密码请由管理员单独提供，不要提交到公开仓库。
