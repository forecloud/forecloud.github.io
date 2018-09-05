---
title: 随笔记
date: 2018-07-09 09:07:56
categories: [脚本]
tags: [cmd,批处理]
---
查看端口占用:
查看所有进程:netstat –ano
查看指定进程:netstat -ano|findstr "8080"

查进程号对应进程名称:tasklist|findstr 3112
根据进程名称杀死进程:taskkill /f /t /im /javaw.exe