1. SESSION 与 COOKIE 的关系
>> 1. cookie 数据是存放在第三方应用的浏览 器上的，session 数据放在服务器上
>> 2. session 会在一定时间内保存在服务器上。当访问增多，会占用服务器的性能 
>> 3. 在php.ini 中设置 session.gc.maxlifetime = 1440 session的存活时间
2. SESSION ID 生成规则
3. SESSION 分布式存储
4. Redis 缓存（列表、锁）
5. 数据库 JOIN 的几种方式
6. MySQL 常用引擎的区别
7. MySQL 索引以及 EXPLIAN
8. PHP 多进程
9. Composer 使用、Nginx、PHP-FPM 优化、LNMP 环境搭建
10. redis 如何防止高并发
    >> 客户端 建立连接池，同时对客户端读写redis操作采取内部锁synchronized
    
    >> 服务器角度，利用setnx变向实现锁机制