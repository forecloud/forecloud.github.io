---
title: nginx入门
date: 2018-8-22 14:55:26
categories: [nginx]
tags: [nginx入门]
---
说明:
    基于centos6.10 minimal操作
* 首先,到[nginx官网](https://nginx.org/)找到[download](https://nginx.org/en/download.html),接着找到Stable version,右击你所用平台的版本,复制[链接](https://nginx.org/download/nginx-1.14.0.tar.gz)
* 回到centos依次执行以下命令:
 ### nginx安装
```
# 安装下载工具与编译工具
yum -y install wget
yum install gcc gcc-c++ ncurses-devel perl
# 下载\解压
cd /usr/local/src && mkdir zip && cd zip
wget https://nginx.org/download/nginx-1.14.0.tar.gz
tar zxvf nginx-1.14.0.tar.gz -C ..
cd ../nginx-1.14.0/
./configure --prefix=/usr/local/nginx       # 编译
# 出现error:the HTTP rewrite module requires the PCRE library.执行以下命令
yum install pcre pcre-devel                 # 安装pcre二进制文件与头文件
# 出现error: the HTTP gzip module requires the zlib library.执行以下命令
yum install zlib zlib-devel                 # 安装zlib二进制文件与头文件
# 终于一切顺利,执行以下语句,进行编译
make && make install
ll /usr/local                               # 查看/usr/local目录是否有了nginx目录
```
 ### nginx 根目录介绍
 ````
 conf   配置文件  
 html   网页文件
 logs   日志文件
 sbin   执行文件
````
 ### nginx 启动
 ````
 cd /usr/local/nginx && ./sbin/nginx        # 启动
 ps -ef | grep nginx                        # 查看nginx进程
 ````
 * 启动异常:address already in use[端口被占用]
```` 
netstat -antp                               #查看端口,PID,软件名
kill -9 pid                                 #杀死进程
pkill -9 pid                                #
```` 

通过ip:80访问nginx

### nginx信号
查看[官方文档](https://www.nginx.com/resources/wiki/start/topics/tutorials/commandline/)
````

````