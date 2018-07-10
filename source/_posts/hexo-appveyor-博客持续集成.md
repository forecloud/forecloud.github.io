---
title: hexo+appveyor 博客持续集成
date: 2018-07-10 16:08:30
categories: [博客]
tags: [hexo,github pages,appveyor]
---

很早之前就听说过持续集成这个概念,但是一直没有实际操作过,这两天在搭建hexo博客时,幸运地让我再次遇见了它.并且发觉,这次搭建博客就是一个不错的入门机会.最终,在花费了两天的时间之后,终于把脉络打通了.

##### 操作基础:基于hexo,github pages完成博客搭建

主要参考了Google到的文章,本文主题是持续集成,所以不做搭建过程描述.

##### 持续集成的思想

在实现建站的过程中,除了代码的编写,还有实施部署,持续集成(Continuous integration，简称CI)解决的问题在于:它让人们更专注于源码,而将源码编译,部署环境搭建等相对固定的重复性动作通过持续集成进行简化.就本博客的持续集成实现过程来说,只有首次实现持续集成时,才会涉及到环境部署这些内容的操作,而在此之后,我们需要做的,就只有好好的维护源码,对于写博客来说就只有写好博文,然后push到github.后续的操作,持续集成会自行帮你完成.

对于搭建hexo博客来说,CI帮你做的简化是这样的:

​    当你写完了文章,准备发布到github上,于是你需要:hexo clean & hexo g & hexo d;

​    而使用了CI之后,你仅需要:git push;

在本文中,CI是通过appveyor提供的服务来完成.叙述过程中会先进行主要过程的描述,文章结尾会对操作过程中的其他问题进行补充描述

##### 第一步:到 [appveyor ](https://ci.appveyor.com)配置需要实现持续集成的项目

推荐使用github账号直接登入,操作起来会很方便.

完成登录后找到[new project](https://ci.appveyor.com/projects/new)按钮,选择github,然后在右侧的列表中选择你的博客仓库,比如我的是:[forecloud.github.io](https://github.com/forecloud/forecloud.github.io)点击后面的add即可.再回到Project页就可以看到你的项目了,项目名右侧找到设置按钮,进入设置页面

{% asset_img slug 20180710175622.png General %}

{% asset_img slug 20180710170446.png General %}

{% asset_img slug 20180710171055.png General %}

settings部分需要配置的有两块General,Environment

我的仓库设置了两个分支,master和source;master存放生成在public文件夹的静态文件;source存放博客源码.General中设置Default branch,Branches to build两项;都设置成源码分支source

{% asset_img slug 20180710174527.png General %}

settings部分需要配置的是四个变量:

GIT_USER_EMAIL:邮箱

GIT_USER_NAME:用户名

STATIC_SITE_REPO:Content Repo地址

TARGET_BRANCH:默认是master

(前两个是appveyor自动部署时,将部署文件提交到master分支时要用到,后两个是告诉appveyor你的部署仓库的地址)

{% asset_img slug 20180710175622.png Environment %}

##### 第二步:

##### 第三步:

##### 操作过程中遇到的其他问题

1.git分支创建,分支切换

2.

参考引用:

[如何更好地对hexo博客管理](http://feg.netease.com/archives/634.html){提供了整体思路}

[appveyor官方文档](https://www.appveyor.com/docs/build-configuration/#configuring-build){建议英文靠谱的同学直接阅读}

[使用AppVeyor持续集成本博客](https://liluoao.github.io/2018/use-appveyor-ci.html){参考了appveyor.yml文件的最后几行配置git commit开始}