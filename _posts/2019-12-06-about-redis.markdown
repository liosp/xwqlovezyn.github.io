SpringBoot-redis-learning

#### Lettuce

Spring Boot2.0 默认使用Lettuce，Lettuce 是一个可伸缩线程安全的 Redis 客户端，多个线程可以共享同一个 RedisConnection，它利用优秀 netty NIO 框架来高效地管理多个连接。

#### 使用步骤

1.引入依赖包；
2.添加配置文件；
3.添加cache的配置类；(使用注解：@EnableCaching来开启缓存)

#### Redis安装与简单使用踩坑

安装坑：关于password，不需要在redis.windows.conf中修改default password，可以在命令行界面使用redis-cli.exe来设置密码，流程如下：

1. F:Redis>redis-cli.exe
2. config set requirepass your-password
3. auth your-password

注：关于redis-cli.exe运行无反应问题--redis server 没有启动，另外开一个命令行界面，进入redis目录，redis-server.exe redis.windows.conf(redis配置文件名)

使用坑暂时没遇见，待续......

