---
title: Java SE 第一章
date: 2018-07-21 20:10:30
categories: [JavaSE]
tags: [JavaSE,cmd,环境变量]
---

###### 常用DOS命令:

win+r 打开运行,cmd

D: 切换盘符:比如进入D盘,直接输入盘符,按回车

dir:显示所有

md:创建文件夹

rd:删除文件夹[删除空目录\删除非空目录]{}

cd:进入文件夹[单级进入\单级回退\多级进入\多级回退]{cd day01  cd ..  cd day01\avi  cd \}

del:删除文件[单个删除\多个删除]{del a.txt  del *.txt}

exit:退出cmd

cls:清除屏幕

notepad:打开记事本

rd /s 文件夹名 [需要确认才能删除]

rd /s /q 文件夹名 [直接删除] 

##### Java语言的特点:

开源/跨平台/简单性/解释性/面向对象/高性能/分布式处理/多线程/健壮性/动态/结构中立/安全性

Java语言是跨平台的,JVM充当翻译角色,针对不同平台有相应实现的JVM

JVM:Java虚拟机

JRE:Java运行环境[JVM+核心类库]

JDK:Java开发工具包[JRE+开发工具(编译工具:javac.exe 打包工具:jar.exe)]

##### JDK下载:

http://www.oracle.com

##### Hello World[记事本编写]

```java
class HelloWorld{
	public static void main (String [] args){
    	System.out.println("Hello World");
	}
}
```
#####  编译执行

编译:javac HelloWorld.java

执行:java HelloWorld

##### 配置环境变量:

环境变量作用:任意目录可运行java工具包的命令

win10:按win键 --> 搜索环境变量回车 --> 点击环境变量[alt+n] --> 点击系统变量下的新建[alt+w] --> 变量名:JAVA_HOME 变量值:填写jdk目录路径并保存[如:D:\Develop\Java\Jdk\jdk1.8.0_121] --> 选中系统变量中Path,点击编辑[alt+i] --> 点击新建[alt+n] --> 填入:%JAVA_HOME%\bin --> 确定

测试是否生效:任意目录打开cmd输入:java -version [若显示版本号则说明配置成功]

