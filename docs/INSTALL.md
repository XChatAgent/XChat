# 安装与升级

## 安装包

```text
XChat-1.3.16-setup.exe
```

安装包内置 WireGuard Windows 驱动安装包，不需要单独下载。

## 安装步骤

1. 双击安装程序。
2. 选择 XChat 程序安装目录。
   - 第一次默认：`C:\Program Files\XChat\Client`
   - 之后会记住上一次目录。
3. 点击“下一步”进入安装进度页。
4. 安装过程中会自动：
   - 复制客户端程序
   - 安装并启动 `XChatAgent` 服务
   - 静默安装 WireGuard（如果尚未安装）
   - 创建 WireGuard 目录联接
5. 安装完成后勾选“启动 XChat”。

## 安装目录

程序目录由用户选择，例如：

```text
D:\XChat
```

以下目录固定：

```text
C:\Program Files\XChat\ChatAgent
C:\Program Files\XChat\WireGuardPkg
C:\Program Files\XChat\WireGuard
```

`C:\Program Files\XChat\WireGuard` 是指向实际 WireGuard 安装目录的目录联接，
只是为了兼容固定路径，不改变 WireGuard 的实际安装位置。

## 用户数据

用户数据与程序目录分离：

```text
%LOCALAPPDATA%\XChat
```

包括日志、缓存、会话和配置等。升级或卸载程序不会主动删除该目录。

旧版本数据会自动从以下目录合并：

```text
%LOCALAPPDATA%\ClaudeCode\XChat
%LOCALAPPDATA%\ClaudeCode\VpnClient
```

## 升级

直接运行新版本安装包：

1. 安装程序会关闭正在运行的 XChat。
2. 停止旧的后台服务。
3. 覆盖程序文件。
4. 重新安装并启动服务。
5. 保留用户数据和安装目录。

升级不需要先卸载旧版本。

## 卸载

通过 Windows“设置 → 应用”或开始菜单卸载 XChat。

卸载会：

- 删除程序文件
- 删除快捷方式
- 停止并删除 `XChatAgent` 服务
- 删除 WireGuard 目录联接
- 删除安装包释放的 WireGuard 安装文件

不会删除：

```text
%LOCALAPPDATA%\XChat
C:\Program Files\WireGuard
```

## 管理员权限

以下操作需要管理员权限：

- 安装/升级后台服务
- 安装 WireGuard
- 创建/删除目录联接

普通用户启动客户端时，隧道由 `XChatAgent` 服务管理。
