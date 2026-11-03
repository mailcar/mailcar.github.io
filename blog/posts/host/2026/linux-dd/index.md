---
title: "主机DD在用Linux脚本分享"
slug: "linux-dd"
description: "在购入新的主机、VPS，每次使用之前，我都会习惯性地执行一次DD命令，这样做的好处，一方面可以将系统更换为我熟悉的Debian另一方面可以移除VPS供应商系统内置的使用情况监控，顺便修改SSH连接端口。"
date: "2026-07-12"
categories:
  - "host"
tags:
  - "host"
  - "Linux"
  - "脚本"
  - "VPS"
cover: "./img/linux-dd.png"
top: 0
comments: true
---

在购入新的主机、VPS，每次使用之前，我都会习惯性地执行一次DD命令。

这样做的好处：一方面可以将系统更换为我熟悉的**Debian**另一方面可以移除VPS供应商系统内置的`使用情况监控`，顺便修改SSH连接端口。

## 一、前期准备

**下载前记得更新源，安装wget组件，以下命令仅对应原系统**:

### Debian系(Debian/Kali/Ubuntu)

    apt updateapt install wget -y

### 红帽系(CentOS/AlmaLinux/RockyLinux/Fedora等)

    dnf install wget -y

### AlpineLinux(需安装wget bash组件，并把系统默认的shell从ash改成bash)

    apk updateapk install wget bashsed -i 's/root:\/bin\/ash/root:\/bin\/bash/g' /etc/passwd

## 二、下载脚本

### 常规Github下载：

    wget --no-check-certificate -qO InstallNET.sh 'https://raw.githubusercontent.com/leitbogioro/Tools/master/Linux_reinstall/InstallNET.sh' && chmod a+x InstallNET.sh

### 国内Gitee下载：

    wget --no-check-certificate -qO InstallNET.sh 'https://gitee.com/mb9e8j2/Tools/raw/master/Linux_reinstall/InstallNET.sh' && chmod a+x InstallNET.sh

## 三、运行DD脚本

### 脚本格式

    bash InstallNET.sh -系统版本 -项目 "数值"

也可以添加其它参数，如raid、bbr、硬盘格式等等，详情可看[[介绍文档](https://github.com/leitbogioro/Tools "介绍文档")]

### 常用版本

    bash InstallNET.sh -debian 12 -pwd 'mailinc.de' -port "16369" --bbr

`示意：DDdebian 12系统，ssh密码设置mans.cc ，ssh端口改为 16369 ，使bbr+fq；`

`完成后按提示，运行 reboot 重启系统即可(首次启动会比较慢)。`

## 测试效果

该脚本已经成功在**DMIT**、**搬瓦工**、**斯巴达**、**甲骨文**、**NC**、**RN**等VPS上完成DD；

包括ipv6在内的所有功能均正常，感谢项目作者的无私奉献。

**原文地址**

https://www.xiaoge.org/archives/dd-linux-system

**项目地址**

https://www.nodeseek.com/post-9383-1

https://github.com/leitbogioro/Tools

![END](/boduan.gif)</center>