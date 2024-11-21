---
title: cern_root下拉菜单在wsl2位置随机变动
date: 2023-04-05 15:38:53
tags:
- cern-root
- wsl2
categories: cern-root
---

## 原因

参考地址[root forum](https://root-forum.cern.ch/t/root-on-windows-11-wsl2-wslg/48348/7)， [微软](https://learn.microsoft.com/en-us/answers/questions/704294/drop-down-menu-appears-incorrectly-when-working-on)，为wslg的bug截至2023年4月5日，`wsl --update`，暂未修复。

## 解决方法

使用x server， 以下来自chatgpt

你可以按照以下步骤使用 VcXsrv 来显示图形界面：

1. 在 Windows 上安装 VcXsrv。你可以从官网 [https://sourceforge.net/projects/vcxsrv/](https://sourceforge.net/projects/vcxsrv/) 下载 VcXsrv 安装包并安装。
2. 在 WSL2 中设置 `DISPLAY` 环境变量。在终端中输入以下命令：`export DISPLAY=$(grep -m 1 nameserver /etc/resolv.conf | awk '{print $2}'):0`。这将把 `DISPLAY` 环境变量设置为 Windows 上运行的 X11 服务器的 IP 地址和端口号。

### 注意事项

前述端口号要与x server 显示的相符合
