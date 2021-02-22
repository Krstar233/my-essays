---
title: 使用Hexo+code-server快捷发布个人博客
date: 2020-10-08 22:41:17
tags:
- 环境搭建
---
### 准备工作
- 一个空闲的服务器（演示环境：Ubuntu 18.04）
- web容器，Apache2/Nginx
- Hexo [官方网站](https://hexo.io/zh-cn/)
- code-server [GitHub链接](https://github.com/cdr/code-server)

### Apache2安装
输入指令：
```
$ sudo apt-get update
$ sudo apt-get install apache2
```

### Hexo安装
- 安装前提
    
    [Node.js](http://nodejs.org/) (Node.js 版本需不低于 10.13，建议使用 Node.js 12.0 及以上版本)
    
    [Git](http://git-scm.com/)

使用npm安装Hexo
```
$ npm install -g hexo-cli
```

### 使用Hexo建站
安装 Hexo 完成后，请执行下列命令，Hexo 将会在指定文件夹中新建所需要的文件。
```
$ hexo init <folder>
$ cd <folder>
$ npm install
```
详细请参考[Hexo官方文档](https://hexo.io/zh-cn/docs/)

### code-server安装
- 选择最新版本的release包下载，然后解压到本地 [下载链接](https://github.com/cdr/code-server/releases)

解压release包，然后进入解压目录，在解压目录输入以下指令启动code-server:
```
$ ./code-server
```
Ctrl+C终止服务器，然后输入指令，修改配置信息：
```
$ vim ~/.config/code-server/config.yaml
```
config.yaml的内容:
```
bind-addr: 0.0.0.0:8888（端口号是随便写的，默认是8000，但是ip要是0.0.0.0）
auth: password
password: [你的密码]
cert: false
```
再次启动code-server:
```
$ ./code-server
```
在浏览器输入地址[http://localhost:8888](http://localhost:8888)，可以看到code-server的登录界面：
![](https://s1.ax1x.com/2020/10/09/0B8WUf.md.png)
输入密码，登录进入可以看到code-server的界面，类似vscode的网页版，在这里你可以在线查看编辑服务器的各类文件，还可以在线安装插件：
![](https://s1.ax1x.com/2020/10/09/0B8X5T.md.png)

### 使用code-server快捷编辑和发布博客：
在code-server的页面中打开博客根目录，在终端中输入指令新建一篇博客：
```
$ hexo new "测试博客"
```
博客文件存放在在博客网站的根目录下：./source/_posts中
![](https://s1.ax1x.com/2020/10/09/0BJtk6.png)

同时，code-server还可以在线编辑和浏览其中的markdown文件：
![](https://s1.ax1x.com/2020/10/09/0BJcAP.md.png)

- 编写脚本，快速发布博客

    在博客网站的根目录下，新建和编辑脚本文件：
    ```
    cd <博客网站根目录>
    vim ./publish.sh
    ```
    publish.sh内容:
    ```
    #!/bin/bash
    sudo rm -r /var/www/html/*
    hexo g
    sudo mv ./public/* /var/www/html/
    ```
- 在博客根目录，输入以下指令即可发布文章：
    ```
    $ sh ./publish.sh
    ```
访问[http://localhost](http://localhost)进入博客网站可以查看新发布的博客。

这样，每次撰写完博客之后，在博客根目录运行这个脚本，就可以直接在博客网站上发布了。

---
另外，本篇文章只是简要的叙述了使用Hexo+code-server进行快捷发布博客的流程，而具体更多Hexo的玩法还需要详细参考Hexo的官方文档。