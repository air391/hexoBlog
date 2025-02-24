---
title: 半导体光电器件
date: 2025-02-24 18:55:09
tags:
- SiPM
- APD
- 工作电压
- 文档
---

## 为什么APD工作电压比SiPM高

滨松官方给出了PD、APD、MPPC、PMT的[性能参数对比](http://share.hamamatsu.com.cn/specialDetail/2094.html)，见下图。该图中可以注意到APD工作电压高于MPPC，这有些违反直觉。因为APD工作在雪崩电压之下，而MPPC工作在雪崩电压之上，所以APD工作电压低于MPPC。


![参数对比图](http://share.hamamatsu.com.cn/UploadFiles/User/2023/3/14/20230314045141339.jpg)

APD与MPPC的本质区别在于APD中的电场仅能让电子雪崩而不足以让空穴雪崩，而MPPC中电场足以让电子与空穴同时雪崩。
对不同器件具体工艺不同，雪崩电压也不同，[滨松官方FAQ](http://share.hamamatsu.com.cn/specialDetail/1091.html#JCQ3)提到

| 从PN结的结构来说，MPPC中的SPAD和普通的APD是一样的。但是，MPPC中的SPAD掺杂浓度比普通的APD高很多，所以很小的电压即可实现SPAD在盖革模式下工作

至于为什么APD与MPPC中单个SPAD掺杂浓度不同则有待调查。

## SPAD是什么

下图中解释了PD、APD、SiPM(MPPC)的工作区间。
![PN结工作电压](https://content.cld.iop.org/journals/0031-9155/65/17/17TR01/revision2/pmbab7b2df1_hr.jpg)

而SPAD(Single Photon Avalanche Diode)是一个工作在盖革模式下的APD，可以理解为SiPM的一个Cell，滨松给出的说明为

|Hamamatsu’s SPAD (Single Photon Avalanche Diode) is an element with a structure of a single pixel that combines a Geiger mode APD and a quenching resistor into one set. It is an optical semiconductor element that enables photon counting. 

[论SiPM vs SPAD在激光雷达应用场景上优劣势](https://www.instrument.com.cn/netshow/SH102193/news_741743.htm)

## 相关资料

- [PMT、MPPC、APD、PD原理与参数对比](http://share.hamamatsu.com.cn/specialDetail/2094.html)
- [硅光电倍增管（MPPC/SiPM）性能参数详解（一）](http://share.hamamatsu.com.cn/specialDetail/2018.html)
- [APD彩页参数解释](http://share.hamamatsu.com.cn/specialDetail/1973.html)
- [The silicon photomultiplier: fundamentals and applications of a modern solid-state photon detector](https://iopscience.iop.org/article/10.1088/1361-6560/ab7b2d)
- [论SiPM vs SPAD在激光雷达应用场景上优劣势](https://www.instrument.com.cn/netshow/SH102193/news_741743.htm)