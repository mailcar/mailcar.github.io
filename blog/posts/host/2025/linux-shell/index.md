---
title: "常用Linux脚本"
slug: "linux-shell"
description: "斥巨资购买了主机，是不是要看下IP纯净度，测试下三网解锁情况，连接速度如何，稳定与否，接下来要进行的面板安装、脚本测试、程序安装......自己常用的一些脚本，持续记录更新，以备使用"
date: "2026-09-10"
categories:
  - "host"
tags:
  - "host"
  - "Linux"
  - "脚本"
  - "VPS"
cover: "./img/linux-shell.png"
top: 0
comments: true
---

## 一、主机性能测评

#### 1、切换root权限

    sudo -i

#### 2、查看主机CPU型号

    lscpu

#### 3、查看系统负载状态

    curl -sL yabs.sh | bash -s -- -5i#####

#### 4、IP质量测试

    bash <(curl -Ls https://Check.Place) -I

#### 5、IP解锁测试

    bash <(curl -sL Media.Check.Place)   

` 选择“0”，测试国际解锁状态`

#### 6、测试三网情况

    bash <(curl -sL Net.Check.Place) 

#### 7、融合怪-主机测速

    export noninteractive=true && curl -L https://raw.githubusercontent.com/oneclickvirt/ecs/master/goecs.sh -o goecs.sh && chmod +x goecs.sh && bash goecs.sh env && bash goecs.sh install && goecs

#### 8、融合怪-主机信息查询

    export noninteractive=true && curl -L https://cdn.spiritlhl.net/https://raw.githubusercontent.com/oneclickvirt/ecs/master/goecs.sh -o goecs.sh && chmod +x goecs.sh && bash goecs.sh env && bash goecs.sh install && goecs -menu=false -comm=false -email=false -security=false

## 二、安装测试

#### 1、查看面板入口

    1pctl user-info

#### 2、手动安装Docker

    bash <(curl -sSL https://linuxmirrors.cn/docker.sh)  

#### 3、查看防火状态状态

    sudo ufw status

#### 4、重启防火墙

    sudo ufw reload

![END](/boduan.gif)</center>
