---
layout:     post
title:      "谷歌语法速查"
subtitle:   " \"成为合格的冲浪选手\""
date:       2024-03-12 03:07:45
author:     "bs0bj"
header-img: "img/sf_dock03.jpg"
catalog: true
tags:
    - Meta
---

人们来到互联网世界毫无目的的漫游，接收着信息茧房推送的垃圾娱乐流量，安装着大公司垄断的杀毒软件。那些看似是在保护你的事物，往往以保护的缘由限制我们的认识，以保护的形势将奴役我们，使我们对外面的世界恐惧。越来越多的黑客题材的艺术作品出现，其根本的原因是我们都想在互联网世界中掌握主控权，即使我们在现实中已经如此被动。

如果你点开这篇文章，你应该是一名 Cyber-guerrilla 或是对赛博世界感兴趣的新人。我将非常负责的为你写一篇 Cyber-guerrilla 的入门材料以帮助你入门赛博世界。

> 所以第一课我们学些什么呢？
> 
> 这是一个好问题，所以请你去问Google吧。

世界上一流的黑客们几乎都是通过自学而来的。对我来说，我热衷于收集信息世界的散落碎片，在一些提供资源和开源资料的社区成长。我认为成为 Cyber-guerrilla 的第一步就是从算法手中夺取信息检索的主动权。所以你没有听错，我们要学习使用搜索引擎。 无论是国内的搜狗，360，还是来自功能强大的Google, Tor, DuckDuckgo, Shodan。

> 学会这些，将会打开一扇新世界的大门。我们能更高效的检索到我们想要的媒体，并可以从中学习一些社工技巧，揭晓行业内幕，排查私人信息泄漏，通过互联网学会所有你感兴趣的专业，新的科技热点。
> 
> 对我这种深度自学爱好者，真的很有诱惑力

那让我们开始吧

#### 拟定目录

- 搜索引擎 <仅有Google>
- 知识获取媒介

## 搜索引擎

> 搜索效率: Google > 公众号搜索 > 短视频 > 国内搜索引擎

#### NCR

`google.com/ncr`(ncr = no country redirect, 禁止谷歌按照当前 IP 跳转到对应的国家或地区)

## 谷歌搜索语法:

> Google: XXX行业/岗位必逛网站
> 
> Google: best sites for XXX

访问 [Google高级搜索](https://www.google.com/advanced_search) 或者借助 [Funnel Search](https://chromewebstore.google.com/detail/funnel-search/moncnfejkabmlhblomihhdoifkgpgkhh?pli=1) 这个浏览器插件。

### 搜索函数

|功能|语法|示例|
|:--|:--:|:--:|
|限定关键词|英文引号""||
|限定标题|intitle:||
|限定标题多个关键词|intitle:"XX""YY"||
|限定内容关键词|intext:|intext:"XiaoMing""SUSTech"|
|限定网址关键词|inrul:||
|限定网址来源|site:|2024推荐面试 site:Zheda.com|
|限定图片大小|imagesize:|SUSTech iamgesize:2560x1440|
|限定文件类型|filetype:|XX研究报告 filetype:pdf|
|收集网站快照|cache:|cache:xxx.com|

> 以上搜索语法可相互组合

#### 搜索完全匹配的结果  (我就是要搜这些)

- 为字词或短语加上英文引号 `“ ”`
- 例如："tallest building" 
- 字词的顺序也必须匹配，即 `"tallest building"`  ≠ `"building tallest"`

<br/>

#### 指定文件类型

- 例如：年终总结 filetype:ppt、特斯拉 研究报告 filetype: pdf
- `filetype:`后面支持以下格式
  - pdf
  - ps
  - dwf
  - kml/kmz
  - xls
  - ppt
  - doc
  - rtf
  - swf

<br/>

### 运算符

|符号|功能|
|:--:|--|
|+|把google可能忽略的字列如查询范围|
|-|把某个字省略|
|.|单一的通配符|
|*|通配符，可代表多个字母|
|""|精确查询|

<br/>

#### 用英文半角括号 `( )`  改变优先级

- 例子: 电报(教程 OR 指南)

<br/>

#### 组合搜索(或)

- 在各个搜索查询之间加上 `OR` (一定要大写)
- `OR` 可用 `｜` (在 `Enter`  键上方) 替代
- 例如: 海贼王 OR One Piece

<br/>

#### 从搜索结果中排除特定字词

- 在你要排除的字词前加上 `-`
- 我想了解水果中的「苹果」：苹果 -手机 -iPhone（`-`后面没有空格）

<br/>

#### 搜索统配符或未知字词

- 在字词或短语中放置占位符 `*`
- 例如: 最*的电影

<br/>

### 黑魔法

|漏洞类型|语法应用|
|--|--|
|SQL注入页面|site:tw inurl:?id=1...10000 filetype:php|
|排除子域名|site:baidu.com -site: video.baidu.com|
|搜索指定网站子域名|site:xxx.com|
|后台登入界面|site:www.baidu.com intitle:"后台登入"|
|目录遍历|intext:"index of"|
|用户名和密码文件|filetype:txt intext:username and password|
|指定端口网站|inurl:8443 -intext:8443|
|敏感文件|site:tw filetype:inc intext:mysql_connect|
|特定网站|intitle:"apache tomacat" inurl:8080|
|转到父目录/转到父路径|intext:to parent directory|
|asp上传漏洞网页|inurl:upload.asp|
|搜索mdb文件|intext: to parent directory + intext:mdb|
|搜索网站的公共FTP用户|site:xxx.com intext:ftp://*:*|

<br/>

#### 知识获取媒介

- 网页
  - [Google](https://www.google.com/)
  - [搜狗（可搜索公众号和知乎文章）](https://weixin.sogou.com/)
  - 公众号（微信搜一搜）
  - [github](https://github.com/)
  - [stackoverflow](https://stackoverflow.com/)
- PDF
  - 文档报告查询
  - 限定文件格式
  - 限定报告网站域名
- 学术
  - [Google Scholar](https://scholar.google.com/)
  - [Scihub](https://sci-hub.hkvisa.net/)
  - [公开数据搜索引擎](https://datasetsearch.research.google.com/)
- 电子书
  - [Z-library01](https://z-library.se/)
  - [Z-library02](https://z-library.cc/)
- 视频
  - [Bilibili](https://www.bilibili.com/)
  - [Youtube ](https://www.youtube.com/)
    > Google: XXX行业/岗位必逛网站
    > 
    > Google: best sites for XXX

<br/>

## 文献

[Google hacking](https://cxaqhq.github.io/2019/10/07/google-hack-%E8%AF%AD%E6%B3%95/)

[庭说](https://tingtalk.me/search-tips/)

[搜索笔记](https://github.com/JiajuZou/Advanced_Tech/blob/main/Search_Notes.md)

[谷歌SEO](https://www.cooltechdoll.com/google-search-commands/)

[你从未用过的微信「搜一搜」，其实可以很实用](https://sspai.com/post/68058)
