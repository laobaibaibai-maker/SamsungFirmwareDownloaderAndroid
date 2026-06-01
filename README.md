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
Android: SamsungFirmwareDownloaderAndroid-v0.1.2.apk
Windows: SamsungFirmwareDownloaderWindows-v1.1.exe
```

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
