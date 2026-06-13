# JT-S508CL-8S OpenWrt 自动编译项目

[English](README.md) | [简体中文](README_CN.md)

本项目用于自动化编译适用于 **JT-S508CL-8S** (基于 Realtek RTL930x方案) 交换机/路由器的 OpenWrt 固件。项目核心编译脚本与工作流框架 Fork/修改自 [VIKINGYFY](https://github.com/VIKINGYFY)，基于 GitHub Actions 实现云端自动编译，源码采用高度定制的 [ImmortalWrt](https://github.com/immortalwrt/immortalwrt)。

---

## 📷 产品展示

我们在此展示 JT-S508CL-8S 交换机：

| 正面外观 | 主板侧视 | 主板俯视 |
|:---:|:---:|:---:|
| ![正面外观](images/product_front.png) | ![主板侧视](images/product_board_side.png) | ![主板俯视](images/product_board_top.png) |

---

## 🛒 购买渠道

您可以通过以下链接购买 JT-S508CL-8S 交换机：
- **速卖通 (AliExpress - 国际)**: [点击在速卖通购买](https://www.aliexpress.com/item/1005008497821015.html)
- **天猫 / 淘宝 (中国)**: [点击在天猫购买](https://detail.tmall.com/item.htm?id=758911123734&skuId=5230615100877)

---

## 🌟 项目简介

本项目包含一套完整的 CI 工作流，通过定时任务 and 手动触发，自动拉取 ImmortalWrt 源码，最终输出适配特定硬件的高性能固件。

### 💻 支持的硬件平台
- **目标平台**: Realtek (`rtl930x`)
- **适配设备**: JT-FG6700-8TFM / ONT-S508CL-8S

## ⚙️ 固件默认配置

- **默认 IP**: `192.168.10.1`
- **默认用户名**: `root`
- **默认密码**: 无 (空)
- **默认主题**: `luci-theme-argon`

## 💽 烧录教程 (刷机指南)

关于设备的详细烧录与刷机步骤（包含 Shell 访问、供电说明及固件刷写等），请参考 OpenWrt 官方硬件维基中的 Xikestor SKS8300-8x 页面（JT-S508CL-8S 与该方案通用）：

👉 **[点击查看：OpenWrt Wiki - Xikestor SKS8300-8x 烧录与硬件说明](https://openwrt.org/toh/xikestor/sks8300-8x?s[]=shell&s[]=supply)**

## 🚀 编译指南 (如何使用)

1. **Fork 本仓库** 到你的个人 GitHub 账号下。
2. 进入仓库的 **Actions** 页面，点击 `I understand my workflows, go ahead and enable them` 以启用工作流。
3. 在左侧菜单中选择 `RTL` 任务。
4. 点击页面右侧的 `Run workflow` 开始云端编译。
5. 编译结束后，进入该次任务的详情页，在 **Artifacts** 中下载打包好的固件，或直接在项目的 **Releases** 页面获取。

## 📄 许可证与鸣谢

- **技术鸣谢**: 本项目的自动化编译脚本、常见插件集成逻辑及工作流框架源自 [VIKINGYFY](https://github.com/VIKINGYFY) 的开源分享，特此鸣谢。
- **许可证**: 本项目采用 [MIT License](LICENSE) 许可协议。

Copyright (c) 2026 Hu Jun.
