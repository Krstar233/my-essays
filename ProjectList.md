---
title: 我的项目列表
date: 2021-3-8 16:30:20
---

- 这篇文章记录了我自大学以来能找到做过的部分大大小小的项目。

- [项目目录](#)
	- [在线课程平台](#在线课程平台)
	- [个人博客项目](#个人博客项目)
	- [冰酒管理系统](#冰酒管理系统)
	- [货物管理系统](#货物管理系统)
	- [指纹识别系统](#指纹识别系统)
	- [贪吃蛇游戏--Unity](#贪吃蛇游戏（Unity）)
	- [小方块快跑--Unity](#小方块快跑（Unity）)
	- [四则运算器--Qt](#四则运算器（Qt）)
	- [五子棋游戏--Qt](#五子棋游戏（Qt）)
	- [打地鼠游戏--Qt](#打地鼠游戏（Qt）)
	- [控制台游戏--俄罗斯方块](#控制台游戏----俄罗斯方块)
	- [控制台游戏--贪吃蛇](#控制台游戏----贪吃蛇)
---
### 在线课程平台
- [项目链接](https://github.com/Krstar233/OnlineEducation)
- 项目简介：在线课程平台，分成了前台页面和后台管理页面两部分
- 做这个项目的目的主要是为了熟悉主流后端开发的开发流程和熟悉springboot，选用了微服务的架构，模仿网上的课程，并结合自己的想法进行修改和独立开发。

- ***在线Demo演示***：【[点击进入后台管理页面](http://krits.fun:3002/#/teacher/table) 用户名：admin 密码：admin】【[点击进入前台页面](http://krits.fun:3001)（施工中...）】

- 后台管理页面
[![6QDIVH.png](https://s3.ax1x.com/2021/03/08/6QDIVH.png)](https://imgtu.com/i/6QDIVH)

- 前台页面
[![6QDzZQ.png](https://s3.ax1x.com/2021/03/08/6QDzZQ.png)](https://imgtu.com/i/6QDzZQ)
[![6QrtdH.png](https://s3.ax1x.com/2021/03/08/6QrtdH.png)](https://imgtu.com/i/6QrtdH)

- 项目使用到的技术：
	- 前端：后台管理页面使用了基于Vue的[管理模板](https://github.com/PanJiaChen/vue-admin-template)；前台页面也套用了一个基于nuxt的模板进行开发；使用element-ui绘制和编排表单样式；
	- 后端：使用springboot、mybatis-plus持久化、nginx反向代理分发请求、Swagger生成接口文档、阿里云oss对象存储、阿里云视频点播服务、maven管理项目、redis缓存等；
---

### 个人博客项目
- [项目链接](https://github.com/Krstar233/KritsBlog)
- 项目简介：个人博客网站，在这里你可以看到我发表的博客、学习笔记、随笔和日常生活等。
- 做这个项目的目的首先是为了解决我现在使用的博客框架Hexo的一些痛点，比如不能自定义个性化的功能模块等。其次，从零开始搭建博客系统是的前端和后端是一件很有乐趣和挑战的事情。
- 项目使用到的技术：
	- 前端：使用基于Vue的element-ui框架，向后台的异步请求使用axios
	- 后端：基于springboot和mybatis框架搭建的，为前端提供接口
	- 数据库：使用mysql
- 目前已完成：
	- 数据库的初步设计
	- 博客数据的增删改查接口
	- 前台页面的基本布局

页面初步效果展示：
![主页](https://s3.ax1x.com/2021/03/08/6QYhDI.png)

---

### 冰酒管理系统
- [项目链接](https://github.com/Krstar233/IceWineManageSystem)
- 项目简介：团队作业，选题是为一个小个体冰酒商户设计的后台管理系统，可以管理冰酒库存、价格，管理客户和订单等. 前后端分离，前端使用了jQuery和layui库，后端使用php读取mysql数据库。
- 我负责的模块：系统前端页面、冰酒管理模块的功能和数据库设计、接口文档的编写等
- 【[操作手册](https://github.com/Krstar233/IceWineManageSystem/blob/main/demo/%E7%B3%BB%E7%BB%9F%E4%BD%BF%E7%94%A8%E8%AF%B4%E6%98%8E%E4%B9%A6.pdf)】
- 冰酒查询
[![6ZIwxx.png](https://s3.ax1x.com/2021/03/04/6ZIwxx.png)](https://imgtu.com/i/6ZIwxx)
- 冰酒出入库
[![6ZIrqO.png](https://s3.ax1x.com/2021/03/04/6ZIrqO.png)](https://imgtu.com/i/6ZIrqO)
---

### 货物管理系统
- [项目链接](https://github.com/Krstar233/MGMS)
- 项目简介：为了写这个项目我自学了前端的html，css，JavaScript等，还了解了ajax请求怎么回事，以及后端的php操作。这个项目的代码除了使用jQuery之外其他都是自己写的，所以页面有点丑x
- 登录页面
![登录页面](https://s3.ax1x.com/2021/03/08/6QdhA1.png)
- 功能模块选择
![功能模块选择](https://s3.ax1x.com/2021/03/08/6QwavD.png)
- 货物管理模块
![货物管理模块](https://s3.ax1x.com/2021/03/08/6QwbGV.png)

---

### 指纹识别系统
- [项目链接](https://github.com/Krstar233/teamwork/tree/master/fingerprint)
- 项目简介：我和另一名队友选了指纹识别的选题，然后逐渐找资料、看论文从0开始搭建了这个比较简单的指纹识别程序，基于相似三角形匹配算法。
- 【[报告](https://github.com/Krstar233/teamwork/blob/master/fingerprint/%E6%8C%87%E7%BA%B9%E8%AF%86%E5%88%AB%E7%A8%8B%E5%BA%8F%E8%AF%BE%E7%A8%8B%E6%8A%A5%E5%91%8A.pdf)】

- 预处理

![6QsM7Q.png](https://s3.ax1x.com/2021/03/08/6QsM7Q.png)

- 实验结果

![6Qso9I.png](https://s3.ax1x.com/2021/03/08/6Qso9I.png)
![6QsOHg.png](https://s3.ax1x.com/2021/03/08/6QsOHg.png)

--- 

### 贪吃蛇游戏（Unity）
- [项目链接](https://gitee.com/krits/krits-code-workplace/tree/master/Old-Code/%E7%BB%83%E6%89%8B%E9%A1%B9%E7%9B%AE/Unity%E9%A1%B9%E7%9B%AE/%E8%B4%AA%E5%90%83%E8%9B%87%20v1.0.2)
- 大一的时候，想学Unity做点游戏，然后在网上搜集资料，于是做了这个贪吃蛇

- 游戏主页：
![游戏主页](https://s3.ax1x.com/2021/03/08/6Qfee0.png)

- 游戏运行界面：
![游戏界面](https://s3.ax1x.com/2021/03/08/6QWBq0.png)

---

### 小方块快跑（Unity）
- 也是Unity项目，但是弃坑了，这里纪念下
[![6lSrcR.png](https://s3.ax1x.com/2021/03/08/6lSrcR.png)](https://imgtu.com/i/6lSrcR)

---

### 四则运算器（Qt）
- 大一刚学了点Qt写的这个程序，可以输入四则表达式，计算出结果，很简单的程序

[![6ldIRf.png](https://s3.ax1x.com/2021/03/08/6ldIRf.png)](https://imgtu.com/i/6ldIRf)

---

### 五子棋游戏（Qt） 
- Qt写的五子棋游戏，但是暂时只能自己和自己玩，所以很鸡肋
[![6lDhnS.png](https://s3.ax1x.com/2021/03/08/6lDhnS.png)](https://imgtu.com/i/6lDhnS)

---

### 打地鼠游戏（Qt） 
- Qt写的打地鼠游戏，只找到了一个可执行的exe文件
[![6l0M90.png](https://s3.ax1x.com/2021/03/08/6l0M90.png)](https://imgtu.com/i/6l0M90)
---


### 控制台游戏 -- 俄罗斯方块
- 大一国庆假期无聊写的

![6lCEc9.png](https://s3.ax1x.com/2021/03/08/6lCEc9.png)]

---

### 控制台游戏 -- 贪吃蛇
- 刚学了点C语言的时候，开始想做项目，就写了这个贪吃蛇，源码很简单，就一页文件

[![6lifl4.png](https://s3.ax1x.com/2021/03/08/6lifl4.png)](https://imgtu.com/i/6lifl4)