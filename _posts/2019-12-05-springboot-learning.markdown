---
layout: post

title: 今日学习杂记-SpringBoot
date: 2019-12-04 17:32:24.000000000 +09:00
---

####SpringApplication

SpringApplication封装了一套Spring应用的启动流程。

####Filter

在Spring中用于录调用日志，排除有XSS威胁的字符，实现权限验证等功能。实现分为两个步骤：
1.实现filter[javax.servlet.Filter]接口，实现Filter接口；
2.添加@configuration注释，将自定义Filter加入过滤链；

####JpaRepository

SpringData中JPA技术访问数据库的核心！dao 只要继承 JpaRepository 类就可以，几乎可以不用写方法，还有一个特别有尿性的功能非常赞，就是可以根据方法名来自动的生成 SQL，比如findByUserName 会自动生成一个以 userName 为参数的查询方法，比如 findAlll 自动会查询表里面的所有数据，比如自动分页等等。

####WebJar

将前端资源以包的形式有Maven进行依赖管理。

####HA主从同步

主从同步引入的主要目的就是消息堆积的内容默认超过物理内存的40%，则消息读取则由从服务器来接管，实现消息的读写分离，避免主服务IO抖动严重。
注：RockerMQ主从同步机制！
