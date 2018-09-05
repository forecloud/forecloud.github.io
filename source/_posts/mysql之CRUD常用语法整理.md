---
title: mysql之CRUD常用语法整理
date: 2018-08-29 19:14:18
categories: [mysql]
tags: [常用语法,mysql]
---
1.通过关联关系删除指定表数据
````
delete a from dt_material a inner join dt_item b on a.item_code=b.item_code where b.id = 12;
delete a,b from dt_material a inner join dt_item b on a.item_code=b.item_code where b.id = 12;
delete a,b,c from a inner join b on a.join_code = b.join_code inner join c on b.store_id = c.store_id
where a.join_code='123456';
````
