---
layout: post

title: Some basic concept of Redis
date: 2019-12-09 13:32:24.000000000 +09:00
---

#### What's Redis?

开源，使用C语言编写，支持网络交互，可以基于内存也可持久化的Key-Value数据库（非关系型数据库）;

#### Advantages of Redis

<1> 速度快：数据存在内存中，类似于HashMap(查找和操作的时间复杂度都是O(1)) ;  
<2> 支持丰富的数据类型：string,set,sorted set,hash;  
<3> 支持事务，操作都是原子性(对数据的更改要么全部执行，要么全不执行);  
<4>  丰富的特性：缓存，消息，按key设置过期时间;  

#### Where to use?

<1> 缓存  
        对于一些要返回给前端数据的缓存，当有大量sql操作时，把数据存入Redis中，直接从内存中获取数据数据，速度会增快很多；  
        web端用户，用于登录缓存session数据，登录信息存储到Redis中；
<2> 队列  
    redis中提供了list接口，有lpush操作和rpop操作，具有原子性；  
<3> 数据存储
    redis有良好的硬盘持久化机制，数据可以定期持久化到硬盘中，保证了redis数据的完整性和安全性；  
<4> redis锁实现防刷机制  
    用来处理并发问题。redis数据类型中有一个set类型，在存储数据时是无序的，且value不能重复；

#### Basic data-type of Redis
    
	Key-value：value支持五种数据类型--string,List,set,hash,sore set;
