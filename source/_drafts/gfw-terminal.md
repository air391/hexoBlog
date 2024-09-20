---
title: gfw-terminal
tags: gfw
categories: 命令行
---

## tun 模式

tun模式安装，参见[clash教程](https://docs.cfw.lbyczf.com/contents/tun.html#windows)

*在 clash 里面的 UWP 里面选中子系统*，参见[链接](https://www.v2ex.com/t/677083)

解决以下所有问题

## git

## openssl

[参考](https://www.cnblogs.com/lvhuayan/p/14538106.html)

`git config --global http.sslVerify "false"`

## time out

[参考](https://z.arlmy.me/posts/hexo/Hexo_DeployMeetsGFW/)

1. 开启clash allow lan,记录地址 `192.168.0.198`
2. 记录端口 `7890`
3. `git config --global http.proxy http://192.168.0.198:7890`
4. `git config --global https.proxy http://192.168.0.198:7890`
5. git 使用即可

注意：使用后关闭allow lan，可能被校园网警告
