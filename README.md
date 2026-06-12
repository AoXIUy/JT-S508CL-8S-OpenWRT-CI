# JT-S508CL-8S OpenWrt 自动编译项目

本项目用于自动化编译适用于 **JT-S508CL-8S** (基于 Realtek RTL930x / SKS8300-8x 方案) 交换机/路由器的 OpenWrt 固件。基于 GitHub Actions 实现云端自动编译，源码采用高度定制的 [ImmortalWrt](https://github.com/immortalwrt/immortalwrt)。

## 🌟 项目简介

本项目包含一套完整的 CI 工作流，通过定时任务和手动触发，自动拉取 ImmortalWrt 源码，并集成了一系列常用插件（如网络代理、内网穿透、存储管理及多种自定义主题），最终输出适配特定硬件的高性能固件。

### 💻 支持的硬件平台
- **目标平台**: Realtek (`rtl930x`)
- **适配设备**: JT-FG6700-8TFM /ONT-S508CL-8S/ Xikestor SKS8300-8x

## ⚙️ 固件默认配置

- **默认 IP**: `192.168.10.1`
- **默认用户名**: `root`
- **默认密码**: 无 (空)
- **默认主题**: `luci-theme-argon` (已进行专门的配色优化)
- **WIFI 名称**: `ImmoralWRT`
- **WIFI 密码**: `12345678`

## 📦 核心特性与插件

本项目通过全局配置和自动抓取脚本预装了丰富的实用组件，省去繁琐的本地配置：

* **核心系统扩展**: 集成 `btrfs`, `nvme` 驱动支持，添加 `iperf3`, `tcpdump`, `wireguard`, `usbutils` 等强大的网络和硬件调试工具。
* **网络代理工具**: 内置 `HomeProxy`, `OpenClash`, `PassWall`, `MosDNS`，并在编译期预置了 HomeProxy 的国内/国外路由分流规则。
* **内网穿透与 VPN**: 支持 `Tailscale`, `ZeroTier`, `EasyTier`, `DDNS-GO` 等。
* **存储与下载**: `qBittorrent`, `DiskManager`, `Mini-DiskManager` (菜单位置已调整优化)。
* **定制化 UI**: 集成了深度优化的 `Argon`、修改了下拉菜单式样的 `Aurora` 及 `Kucat` 主题。

## 🚀 编译指南 (如何使用)

1.  **Fork 本仓库** 到你的个人 GitHub 账号下。
2.  进入仓库的 **Actions** 页面，点击 `I understand my workflows, go ahead and enable them` 以启用工作流。
3.  在左侧菜单中选择 `QCA-ALL` 任务。
4.  点击页面右侧的 `Run workflow`：
    * 支持在输入框内手动添加所需的额外插件包名。
    * 支持勾选 "仅输出配置文件，不编译固件" 选项用于本地检查配置。
5.  点击绿色的 `Run workflow` 开始云端编译。
6.  编译结束后，进入该次任务的详情页，在 **Artifacts** 中下载打包好的固件，或直接在项目的 **Releases** 页面获取。

### 🧹 自动清理机制
为了避免占用 GitHub 过多存储额度，项目自带 `Auto-Clean` 工作流（每天北京时间早上 05:00 执行），会自动清理陈旧的 Releases 固件包和 Workflows 运行记录。

## 🛠️ 高级自定义配置

如需进行进一步的定制，可修改以下文件：

* **基础环境变量**: 修改默认 IP、主机名或密码，请编辑 `.github/workflows/RTL.yml`。
* **增删基础包**: 在 `Config/GENERAL.txt` (全局配置) 中以 `CONFIG_PACKAGE_xxx=y` 或 `=n` 的形式增减组件。
* **添加第三方插件**: 编辑 `Scripts/Packages.sh`，利用封装好的 `UPDATE_PACKAGE` 指令直接从其他 GitHub 仓库拉取最新插件源码。
* **定制编译逻辑**: 通过 `Scripts/Handles.sh` 自动修复依赖冲突、修改系统文件、定制主题 UI 或调整插件的系统启动顺序（如 `qca-nss-drv`）。

## 📄 许可证

本项目采用 [MIT License](LICENSE) 许可协议。
Copyright (c) 2026 Hu Jun.
