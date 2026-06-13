# JT-S508CL-8S OpenWrt Auto-Build Project

[English](README.md) | [简体中文](README_CN.md)

This project is designed to automatically compile OpenWrt firmware for the **JT-S508CL-8S** L3 managed fiber switch/router (based on the Realtek RTL930x solution). The core compilation scripts and workflow framework are Forked/Modified from [VIKINGYFY](https://github.com/VIKINGYFY), leveraging GitHub Actions for cloud-based automated compilation. The source code is based on the highly customized [ImmortalWrt](https://github.com/immortalwrt/immortalwrt).

---

## 📷 Product Showcase

We showcase the JT-S508CL-8S switch here:

| Front View | Board Side View | Board Top-down View |
|:---:|:---:|:---:|
| ![Front View](images/product_front.png) | ![Board Side View](images/product_board_side.png) | ![Board Top-down View](images/product_board_top.png) |

---

## 🛒 Where to Buy

You can purchase the JT-S508CL-8S switch through the following links:
- **AliExpress (International)**: [Buy on AliExpress](https://www.aliexpress.com/item/1005008497821015.html)
- **Tmall / Taobao (China)**: [Buy on Tmall (天猫购买链接)](https://detail.tmall.com/item.htm?id=758911123734&skuId=5230615100877)

---

## 🌟 Introduction

This repository contains a complete CI workflow that pulls the ImmortalWrt source code automatically (via scheduled tasks or manual triggers) and outputs high-performance firmware tailored for the specific hardware.

### 💻 Supported Hardware Platforms
- **Target Platform**: Realtek (`rtl930x`)
- **Adapted Devices**: JT-FG6700-8TFM / ONT-S508CL-8S

## ⚙️ Default Firmware Settings

- **Default IP Address**: `192.168.10.1`
- **Default Username**: `root`
- **Default Password**: None (Empty)
- **Default Theme**: `luci-theme-argon`

## 💽 Flashing Guide

For detailed flashing steps (including Shell access, power supply description, and firmware writing, etc.), please refer to the Xikestor SKS8300-8x page in the OpenWrt Official Hardware Wiki (JT-S508CL-8S shares the same scheme):

👉 **[Click to View: OpenWrt Wiki - Xikestor SKS8300-8x Flashing and Hardware Instructions](https://openwrt.org/toh/xikestor/sks8300-8x?s[]=shell&s[]=supply)**

## 🚀 Compilation Guide (How to Use)

1. **Fork this repository** to your personal GitHub account.
2. Go to the **Actions** page of your forked repository, and click `I understand my workflows, go ahead and enable them` to enable the workflows.
3. Select the `RTL` task in the left menu.
4. Click `Run workflow` on the right side of the page to start compiling in the cloud.
5. Once the compilation is complete, go to the task details page and download the packed firmware under **Artifacts**, or retrieve it directly from the project's **Releases** page.

## 📄 License & Acknowledgements

- **Acknowledgements**: The automated build scripts, plugin integration logic, and workflow framework of this project originate from [VIKINGYFY](https://github.com/VIKINGYFY)'s open-source sharing. Special thanks to them!
- **License**: This project is licensed under the [MIT License](LICENSE).

Copyright (c) 2026 Hu Jun.
