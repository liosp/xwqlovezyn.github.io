---
layout: post

title: Springboot搭建个人网站(一)
date: 2019-12-12 18:02:24.000000000 +09:00
---
### Motivation
&emsp;最近在学习Springboot框架，考虑到通过实战可以更有效吸收学习到的内容，而且可以将之前学习的一些内容融入进去。计划用springboot开发一个博客系统，参考JayTange(https://github.com/JayTange/Jantent)<br>&emsp;项目中用到的技术和框架：<br>&emsp;<1> 项目构建：maven；<br>&emsp;<2> web框架：springboot；<br>&emsp;<3>数据库ORM:mybatis;<br>&emsp;<4> 数据库连接池：Druid;<5> 分页插件：PageHelper;<br>&emsp;<6> 数据库:Mysql;<br>&emsp;<7>缓存NOSQL：redis;<br>&emsp;<8>前端模块:thymeleaf;<9>文章展示:使用commonmark,将markdown转成html页面;<br>
&emsp;上述部分，对Druid,PageHelper,commonmark没有了解，先了解一下相关概念。
### Druid
&emsp;高效的数据查询系统，主要解决对大量的基于时序的数据进行聚合查询。数据可以做到实时摄入，实时查询，但是数据几乎不可变；<br>&emsp;Druid采用的架构：<br>&emsp;<1> shared-nothing架构：分布式计算架构，在这种架构中，没有节点共享存储和硬盘。<br>&emsp;<2> Lambda架构：为了满足实时大数据关键特性的架构，高容错，低时延和可扩展等待。<br>&emsp;主要思想：将大数据系统构建为多个层次，三层架构batch layer，speed layer，serving layer:<br>&emsp;批处理层将大数据变小，有效利用资源；批处理的结果往往需要等待全部数据处理完后更新serving layer，这会影响实时性，这就是实时处理层存在的意义，speed layer不会同时读取所有新数据，它会在有新数据产生时，就接受新数据，更新realtime view；Batch Layer通过对master dataset执行查询获得了batch view，而 Serving Layer就要负责对batch view进行操作，从而为最终的实时查询提供支撑。更多Druid相关概念(https://blog.csdn.net/qq_27466827/article/details/82777112)
### PageHelper
&emsp;Mybatis中实现分页功能的组件：PageHelper首先将前端传递的参数保存到page这个对象中，接着将page的副本存放入ThreadLoacl中，这样可以保证分页的时候，参数互不影响，接着利用了mybatis提供的拦截器，取得ThreadLocal的值，重新拼装分页SQL，完成分页。细节(https://www.cnblogs.com/billmiao/p/9872158.html)
### Commonmark
&emsp;通过Markdown语法编辑文章，然后将编辑好的MD文件转化为Html页面上传到网站。
