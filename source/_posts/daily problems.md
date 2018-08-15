---
title: 'daily problems'
date: 2018-08-14 14:41:23
categories: [日常问题]
tags: []
---

1.触发器

2.存储过程

3.

4.只要开始了,就不算晚;只要坚持了,就不会毫无意义;只有因逃避而放弃,毫无意义



mysql安装(基于ubuntu)

1.查找tomcat所在目录

find / -name tomcat

2.修改mysql5.7初始化密码:sudo vim /etc/mysql/debian.cnf

下面介绍三种方式对MySQL进行启动/停止/重启操作：

#### mysql操作:

启动mysql：
方式一：sudo /etc/init.d/mysql start 
方式二：sudo start mysql
方式三：sudo service mysql start
停止mysql：
方式一：sudo /etc/init.d/mysql stop 
方式二：sudo stop mysql
方式san：sudo service mysql stop
重启mysql：
方式一：sudo/etc/init.d/mysql restart
方式二：sudo restart mysql
方式三：sudo service mysql restart

参考:

​	https://blog.csdn.net/xiangwanpeng/article/details/54562362

​	https://www.cnblogs.com/anseey/archive/2013/04/28/3049785.html

​	https://www.jianshu.com/p/3111290b87f4

​	改字符集: https://blog.csdn.net/qq_32144341/article/details/51318390

​	完全卸载: https://blog.csdn.net/w3045872817/article/details/77334886

​	远程连接: https://www.cnblogs.com/ryanlamp/p/5555086.html