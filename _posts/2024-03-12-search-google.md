---
layout:     post
title:      "Cyber-guerrilla | 互联网个人主权"
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

**谷歌语法使用案例:**
![](https://krona0.github.io/img/in-post/post-search-google/00.png)

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

### 运算符

|符号|功能|
|:--:|--|
|+|把google可能忽略的字列如查询范围|
|-|把某个字省略|
|.|单一的通配符|
|*|通配符，可代表多个字母|
|""|精确查询|

#### 用英文半角括号 `( )`  改变优先级

- 例子: 电报(教程 OR 指南)

#### 组合搜索(或)

- 在各个搜索查询之间加上 `OR` (一定要大写)
- `OR` 可用 `｜` (在 `Enter`  键上方) 替代
- 例如: 海贼王 OR One Piece

#### 从搜索结果中排除特定字词

- 在你要排除的字词前加上 `-`
- 我想了解水果中的「苹果」：苹果 -手机 -iPhone（`-`后面没有空格）

#### 搜索统配符或未知字词

- 在字词或短语中放置占位符 `*`
- 例如: 最*的电影

### 黑魔法

|漏洞类型|语法应用|
|--|--|
|SQL注入页面|site:tw inurl:?id=1...10000 filetype:php|
|排除子域名|site:baidu.com -site: video.baidu.com|
|搜索指定网站子域名|site:xxx.com|
|后台登入界面|site:xxx.com inurl:login\|admin\|manage\|member\|admin_login\|login_admin\|system\|login\|user|
|目录遍历|intext:"index of"|
|用户名和密码文件|filetype:txt intext:username and password|
|指定端口网站|inurl:8443 -intext:8443|
|敏感文件|site:tw filetype:inc intext:mysql_connect|
|特定网站|intitle:"apache tomacat" inurl:8080|
|转到父目录/转到父路径|intext:to parent directory|
|asp上传漏洞网页|inurl:upload.asp|
|搜索mdb文件|intext: to parent directory + intext:mdb|
|搜索网站的公共FTP用户|site:xxx.com intext:ftp://*:*|

### 知识获取媒介

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

### 信息素养(Information literacy)

#### 什么才是真的？

这种“真”的存在只属于相信，比如我相信一段关系，但我与对方彼此信任的关系无法套用给第三方。有时候一些事情的真可以存在于两个人之间，如果事件成立就可以在两人之间使用(比如双方的nick-name)，也可以是群体的，或者独立一点就是个人的。事物有多真就取决于多少人相信，你可以把你的想法编写给任何人，并说服他们；当然你也可以相信他人给你录入的想法。
这个观点我个人认为，适用人与人，人与社会的关系之中
> 当你对这个这个事物提不出一个问题，他人的问题没有一个你是解答不了的时候，这就是真的。<br/>
> 你说服了自己，而后说服了别人，最终说服了世界

#### 主动提问

提问是自主学习中十分重要的一环。并不是所有人都能通过阅读一本书吸收全部的知识点，更有不幸者读完书籍时犹如囫囵吞枣一般，并开始怀疑自己的理解能力。不过不用担心，这是普遍现象。进军不同领域都会出现知识空隙，这时我们就需要通过提问去解决问题。

有时候我们想要的答案无法从互联网中获取，第三方平台的崛起，那些信息库将很难从搜索引擎中获取。我们可以通过在第三方平台提问获取答案。
> - 可以在诸多大佬的 blog 中收集他们的邮箱，碰到关键的问题可以发邮件提问(欢迎记录下我的blog邮箱:ln0wlanmon@proton.me)
> - 第三方平台虽然会私有自己的信息库，控制舆论倾向。但这并不代表里面没有有价值的用户，或者热心提供帮助的人。这里推荐:
>   <br/>
>   [知乎](https://www.zhihu.com/)
>   <br/>
>   [Quora](https://www.quora.com/)

期望回答者为自己的无知负责，是不可取的行为。在逛论坛的时会遇到许多人希望通过一篇答复就解决领域内的困难，可往往收到的答复是零碎的只言片语。
我建议放弃这类把自己命运交给他人的期望。试着搜集下他们的答复，并找出关键词去谷歌收集更多相关的信息学习吧。
> 例子提供参考方向，并非标准答案
> 问题: 怎么样减肥才是最有效的？
> <br/>
> 回答者1: 那是因为营养过剩引起的，一、控制饮食....二、有效运动..... (关键词 运动、饮食)
> <br/>
> 回答者2: ....胰岛素分泌紊乱....控制血糖        (关键词 胰岛素 控血糖)
> <br/>
> 回答者3: 推荐一款减肥药....                    (忽略营销术语，获取名字，凭证信息)
> <br/>
> 开始谷歌关键词间的关系(胰岛素与体重之间的关系 、控制血糖的方法\(给出饮食运动方案，不同饮食运动对血糖的影响\)、获取减肥药名字 Google国药数据库编码，查成份、Google减肥药的一些原理...)

#### 标明来源

> <引自 Dr_Ting>
> 如果讨论的事实本身是错的，得出的结论也就站不住脚。
> 
> - 没有信源：只注明「有关专家表明」而不给出信源。请勿传播此类无法考证的文章。
> - 一个信源：查看此信源是否可靠。多看来自知名英文媒体，但也要辩证看待。
> - 多个信源：对于涉及重大公共利益的新闻，若要认定这个事实，至少需要两个独立的消息源互为验证（交叉验证）。注意，第一个信源提供的第二个信源，不构成独立信源。否则，只是消息或观点，而不是事实。

#### 不含情绪，使用逻辑
新闻只提供事实，没有情绪，所以，远离标题党和充满感叹号的文章，珍惜有限的生命时间。
> 包含关系
> 不要以点代面（以偏概全）去阐述观点，那是思维偷懒的表现：
> - 因为：他欺骗了
> - 然而：他是男人
> - 所以：男人都是骗子
>
> 超集的定义才适用于子集：
> - 因为：张三是中国人
> - 然而：中国位于地球
> - 所以：张三是地球人

参考
--

1. google hack 语法 - BADBOY Blog [https://cxaqhq.github.io/](https://cxaqhq.github.io/2019/10/07/google-hack-%E8%AF%AD%E6%B3%95/)
2. 想要更高效地找到信息，你需要掌握这些搜索技巧  - 庭说 [https://tingtalk.me/search-tips/](https://tingtalk.me/search-tips/)
3. 最详细的GOOGLE搜索指令大全-善用谷歌搜索引擎，办公效率翻倍 - 黑科技娃娃 Blog [https://www.cooltechdoll.com/google-search-commands/](https://www.cooltechdoll.com/google-search-commands/)
4. 你从未用过的微信「搜一搜」，其实可以很实用 - 少数派 [https://sspai.com/post/68058](https://sspai.com/post/68058)

