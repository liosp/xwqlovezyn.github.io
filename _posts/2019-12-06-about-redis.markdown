SpringBoot-redis-learning

#### Lettuce

Spring Boot2.0 Ĭ��ʹ��Lettuce��Lettuce ��һ���������̰߳�ȫ�� Redis �ͻ��ˣ�����߳̿��Թ���ͬһ�� RedisConnection������������ netty NIO �������Ч�ع��������ӡ�

#### ʹ�ò���

1.������������
2.��������ļ���
3.���cache�������ࣻ(ʹ��ע�⣺@EnableCaching����������)

#### Redis��װ���ʹ�òȿ�

��װ�ӣ�����password������Ҫ��redis.windows.conf���޸�default password�������������н���ʹ��redis-cli.exe���������룬�������£�

1. F:Redis>redis-cli.exe
2. config set requirepass your-password
3. auth your-password

ע������redis-cli.exe�����޷�Ӧ����--redis server û�����������⿪һ�������н��棬����redisĿ¼��redis-server.exe redis.windows.conf(redis�����ļ���)

ʹ�ÿ���ʱû����������......

