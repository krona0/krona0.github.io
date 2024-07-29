---
layout:     post
title:      "Cyber-guerrilla | 互联世界"
subtitle:   " \"Clash使用教程，打破信息束缚\""
date:       2024-06-26 15:33:23
author:     "bs0bj"
header-img: "img/in-post/post-clash-help/clash.png"
catalog: true
tags:
    - Meta
---
## 学习这篇教程可以为我带来什么
1. 可以不受限于地区政治访问全球互联网
2. 可以加密自己的互联网身份，放置被定位追踪
3. 基础的电脑知识 TCP/IP
5. 解锁更多高质量的资源、网站、博客、技术获取渠道
6. 比他人更早知道区域政治，多角度的媒体，方便排查新闻造假。

## 代理工具🔧
在使用代理中我们有不同的工具可以选择，我喜欢把它形容成不同的流派。每种流派都有独属于他的个性，八仙过海各显神通。在最开始我们先来认识最主要的几位“神仙”。

> Clash流(X or for windows/linux/android) <br/>
> Shadowsocks流(R,D) <br/>
> V2ray流(A,N) <br/>
> SocksShell <br/>
> Trojan <br/>
> 在IOS系统中还有(Shadowrocket)。 <br/>

在延时中我们使用 Clash 流派中最易使用的Clash for windows。学习 for windows 版本的图形化界面对 Windows/Ubuntu/Mac 系统上使用 Clash 会有很大的帮助。

> 这里的 Clash for Windows 并非是仅仅在 windows 系统上才能使用 。这里的windows更像是图形化界面的意思，同理在 linux 上也能安装 Clash for Windows。<br/>
> 还有一个大陆网民的民间说法是，Clash for windows 的缩写是 {GFW}。

## Clash介绍😼
Clash是一个跨平台的基于规则的代理工具, 在网络和应用层运行。用白话讲就是一个整合了大部分网络代理功能的强大工具。

>目前 Clash 包含两个版本: 
> - Clash核心: 发布于 [github.com/Dreamacro/clash](https://opensource.clash.wiki/Dreamacro/clash) 的开源版本
> - Clash Premium: 具有 TUN和其他附加功能 的高级版本。

目前有许多搭载 GUI 客户端的版本，Clash for windows 就是其中之一。

**技术概述(Premium)**[^1]
- 入站连接支持: HTTP, HTTPS, SOCKS5 服务端, TUN 设备*
- 出站连接支持: Shadowsocks(R), VMess, Trojan, Snell, SOCKS5, HTTP(S), Wireguard*
- 基于规则的路由: 动态脚本、域名、IP地址、进程名称和更多*
- Fake-IP DNS: 尽量减少 DNS 污染的影响, 提高网络性能
- 透明代理: 使用自动路由表/规则管理 Redirect TCP 和 TProxy TCP/UDP*
- Proxy Groups 策略组: 自动化的可用性测试 (fallback)、负载均衡 (load balance) 或 延迟测试 (url-test)
- 远程 Providers: 动态加载远程代理列表
- RESTful API: 通过一个全面的 API 就地更新配置

## 互联世界🌍

我们讲了这么多学术级废话，终于可以开始我们实操环节了。
在令人兴奋的 操作环节开始之前，我们还需要做好为达成互联的前置调节：我们的工具、达成连接需要用到的技能、加载在工具中的原材料配置文件(取决于我们最终是否可以连接的关键)。
### 准备阶段
#### 环境
intel CPU的Windows电脑
#### 下载
按CPU的类型获取 Clash for windwos [下载链接](https://downloads.clash.wiki/clash_for_windows_pkg/)
#### 认识界面
![p](https://krona0.github.io/img/in-post/post-search-google)

- General(通用设置)
	- Port、Socks Port；分别为HTTP、SOCKS代理端口，点击终端图案可以打开一个配置了代理的命令行窗口，点击端口数字可以复制该命令；
	- `Allow LAN`：启用局域网共享代理功能；
    
	- `Log Level`：日志等级；
    
	- `Home Directory`：点击下方路径直达 `C:\Users\用户名\.config\clash` 文件夹；
    
	- `GeoIP Database`：点击下方日期可更新 GeoIP 数据库；
    
	- `UWP Loopback` ：可以用来使 UWP 应用解除回环代理限制；
    
	- `Tap Device` ：安装 cfw-tap 网卡，可用于处理不遵循系统代理的软件（实际启动 tap 模式需要更改配置文件）；
    
	- `General YML`：编辑 `config.yml` 文件，可用于配置部分 General 页面内容；
    
	- `Dark Theme`：控制暗色模式；
    
	- `System Proxy`：启用系统代理；
    
	- `Start with Windows`：设置开机自启；
- Proxies(代理)：选择代理方式（Global – 全局、Rule – 规则、Direct – 直连）及策略组节点选择
- Profiles(配置管理)
	- 用来下载远端配置文件和创建本地副本，且可在多个配置文件间切换；
    
	- 对配置进行节点、策略组和规则的管理（添加节点、策略组和规则在各自编辑界面选择 `Add`, 调整策略组顺序、节点顺序及策略组节点使用拖拽的方式）；
- Logs(日志)：显示当前请求命中规则类型和策略；
- Connections(连接)：显示当前的 TCP 连接，可对某个具体连接执行关闭操作；
- Settings(设置)：软件详细设置；
- Feedback(反馈)：显示软件、作者相关信息。

#### 节点
节点即软件中的**服务器**。在使用之前我们需要获取添加一个Clash for Windows节点即服务端才能使用代理上网功能。

这类节点一般可以在互联网上免费获取，其安全性并不高，还会有泄漏隐私的风险。

当然也可以购买VPS服务器自己 DIY 节点，听起来很酷。可这十分的麻烦，而且维护时间成本很高，在一些政治敏感地区大大加大了维护难度。

付费节点是一个好选择，支付一笔每个月 10-20¥ 不等的费用就可以畅通无阻。省下了很多不必要的维护时间，而且订阅十分方便，随着产业链的成熟许多节点都十分的稳定。目前我使用过最便宜的是一个月8¥ ，有心者可以探索到更多惊喜，github上还有不少的1¥机场✈️。

**免费节点分享(Updating)**
<br/>[自行搜索吧](www.google.com)

**付费节点分享(Updating)**
<br/>[橘子云](https://jzy66222.xyz/)
[轻云](https://qingyunjia.cc)
## 点火! 启动！🚀

### 添加配置文件
![p](https://krona0.github.io/img/in-post/post-search-google)
点击 Profiles (配置管理)
导入入 Url 链接🔗


### 启用代理
![p](https://krona0.github.io/img/in-post/post-search-google)
打开 System Proxy (启用系统代理)

### 设置开机自启
![p](https://krona0.github.io/img/in-post/post-search-google)
打开 Start with Windows (开机自启动)

### 更新配置文件
Clash 的配置文件为 YAML，编写配置文件YAML会在进阶版本中详细赘述。

![p](https://krona0.github.io/img/in-post/post-search-google)

##### 切换代理(Proxies)模式
Clash 的三种工作模式: 
> - Global (全局): 所有请求直接发往**代理服务器**
> - Rule (规则): 所有请求**根据配置文件规则进行分流**
> - Direct (直连): 所有请求**直接发往目的地**


#### 进阶内容
##### TUN模式
对于不遵循系统代理的软件，TUN 模式可以接管其流量并交由 CFW 处理，在 Windows 中，TUN 模式性能比 TAP 模式好

>近期大部分浏览器默认已经开启“**安全 DNS**”功能，此功能会影响 TUN 模式劫持 DNS 请求导致反推域名失败，请在浏览器设置中关闭此功能以保证 TUN 模式正常运行

**##Windows 下开启TUN**
启动 TUN 模式需要进行如下操作：
1. 点击`General`中`Service Mode`右边`Manage`，在打开窗口中安装服务模式，安装完成应用会自动重启，Service Mode 右边地球图标变为 🟢 即安装成功
2. 点击`General`中`TUN Mode`右边开关启动 TUN 模式


## 答疑解惑
#### 什么是VPN
VPN 是一种可以让您随时随地安全访问互联网的工具，其工作原理就是在您的设备和 VPN 提供商之间建立一条安全“通道”，主要在两方面保护您的隐私：

> 1. 掩藏您的 IP 地址，以保护您的个人身份和位置。
> 2. 加密您与 VPN 提供商之间的流量，杜绝本地网络上的任何人进行解密或修改。

> tips : 在连接公共wifi，可以使用 VPN 保证安全




***
参考文献
- [^1] [Clash知识库-> https://clash.wiki/](https://clash.wiki/)
- [^2] [最新 Clash for Windows 使用教程快速入门](https://clashgithub.com/clashforwindows.html)
- [^3][什么是VPN](https://www.mozilla.org/zh-CN/products/vpn/resource-center/what-is-a-vpn/)
- [Clash for Windows Download ->](https://downloads.clash.wiki/clash_for_windows_pkg/)
