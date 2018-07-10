---
title: datatable使用记录
date: 2018-07-09 10:08:35
categories: [插件]
tags: [开发,js,datatable,datatable]
---
## 1.报错:Invalid JSON response

###### 完整报错:

```js
DataTables warning: table id=datatable2 - Invalid JSON response. For more information about this error, please see http://datatables.net/tn/1
```
###### 解决过程:

1.google发现了[datable报错文档](https://datatables.net/manual/tech-notes/1) 当然,英文的,Google翻译一波后发现并没有什么卵用,但是它提醒我应该多看看控制台

2.查看浏览器控制台,看是否报错,响应是否正常

3.查看后台日志信息,看是否报错

###### 结果:

原来是我后期修改代码时,新增了字段,但是没有将字段新增到正式系统库,代码更新后,就出现了这个报错,但由于正式服务器我没有操作权限,所以无法查看后台报错,于是查看浏览器,发现datatable发出的两条ajax请求都是响应500,明显是后台发生了报错,所以就去找大佬查看服务器日志了,才发现少了个字段.......尴尬

###### 反思:

我有个不好的开发习惯,发现报错之后总喜欢马上就去google,完全没有正常的排错思路,寻找可能的原因,这样的第一反应很糟糕,要改.另外,表字段变更及时同步其他数据库,减少那些低级错误造成的困扰.