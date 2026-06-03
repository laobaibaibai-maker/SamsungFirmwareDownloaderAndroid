# 三星固件下载工具发布页

这是“三星固件下载工具”的公开发布页。

本仓库仅用于：

- 发布 Android APK
- 发布 Windows EXE
- 提供 Android / Windows 在线更新检测入口
- 展示使用说明
- 展示免责声明

本仓库不包含应用源码、构建脚本、签名密钥或内部实现文件。

## 下载

请前往 GitHub Releases 下载最新版：

https://github.com/laobaibaibai-maker/SamsungFirmwareDownloaderAndroid/releases/latest

当前发布内容：

```text
Android: SamsungFirmwareDownloaderAndroid-v0.1.3.apk
Windows: SamsungFirmwareDownloaderWindows-v1.1.exe
```

## Android v0.1.3 更新日志

> Android v0.1.3 已发布到 GitHub Releases。

- 新增固件更新提醒：支持在后台定时监控指定型号和地区。
- 固件提醒支持开关、型号、地区、自定义检测间隔和上次检测时间显示。
- 检查应用更新按键布局优化。
- 新增启动时自动检查应用更新：每天最多自动检查一次，只有发现新版才弹窗提醒。
- 检测到新固件时，App 前台显示应用内弹窗；App 后台继续显示系统状态栏通知。
- 输入框历史记录改为浏览器式弹窗：点击型号/地区输入框时显示对应历史。
- 历史弹窗支持主题适配、窄宽度显示、清空历史、单条删除。
- 修复历史记录清空和单条 `×` 删除失效问题。
- 优化启动页与 App 图标。
- 优化首页首卡布局：主题入口移动到标题右上角，状态信息单独显示。
- 优化多线程设置布局：开关缩小并与“多线程下载”标题水平对齐。
- 优化固件下载写入性能，减少频繁 flush 带来的速度损耗。
- 新增固件 8 线程分段下载，服务器不支持 Range 时自动回退单线程。
- 支持多线程开关和 2 / 4 / 6 / 8 线程数选择。
- 修复多线程暂停/继续后分段缓存恢复逻辑，继续下载按 part 文件累计恢复。
- 修复暂停/取消时 `Socket closed` 被误判为多线程失败回退的问题。
- 优化多线程下载速度统计，继续下载时只统计本轮新增数据，避免速度虚高。
- Debug 包默认使用正式签名，方便覆盖安装正式版调试。
- 优化部分固件下载兼容：BinaryInform 文件名字段兼容 `BINARY_FILE_NAME`、`BINARY_FILENAME`、`FILE_NAME`、`FILENAME`，并支持从 `MODEL_PATH` 兜底解析文件名。
- 当三星只返回固件版本但未提供下载包信息时，改为明确提示“未提供下载包”，不再误导为缺少固件名。
- 修复取消下载时第一次残留文件清理可能失败的问题：取消后等待下载线程退出、文件句柄释放后再统一清理。
- 取消下载或任务失败后自动重置下载/解密进度和状态。

## Android 在线更新说明

Android 应用内“检查应用更新”会访问本仓库的 GitHub Releases 信息：

```text
https://api.github.com/repos/laobaibaibai-maker/SamsungFirmwareDownloaderAndroid/releases/latest
```

当发现新版本时，应用会引导用户打开下载链接并手动安装 APK。

Android 系统不允许普通应用静默安装 APK，用户需要在系统安装界面确认安装。

## Windows 在线更新说明

Windows 程序内“检查应用更新”会优先访问本仓库根目录的更新清单：

```text
https://raw.githubusercontent.com/laobaibaibai-maker/SamsungFirmwareDownloaderAndroid/main/update-windows.json
```

当发现新版本时，程序会引导用户打开下载链接并手动下载 EXE。

## 适用范围

本工具仅用于查询和下载公开可获取的三星官方固件资源。

请勿将本工具用于任何违法、侵权、绕过授权或破坏设备安全机制的用途。

## 免责声明

使用前请阅读：

[DISCLAIMER.md](DISCLAIMER.md)
