# JavaGuide

## 1. Java

### 1.1 什么是静态代理、动态代理，它们的区别是什么？

### 1.2 HashMap为什么不能用于高并发？

### 1.3 创建线程池的ThreadPoolExecutor的构造方法的参数说明一下。

### 1.4 JDK Executors提供的几个线程池了解吗，使用JDK提供的线程池会有什么问题？

- `FixedThreadPool` 
- `SingleThreadPool`
- `CachedThreadPool`
- `ScheduledThreadPool`

存在的问题

1. `FixedThreadPool`和`SingleThreadPool`
允许的请求队列长度为Integer.MAX_VALUE，可能会堆积大量的请求，从而导致OOM。
2. `CachedThreadPool`和`ScheduledThreadPool`
允许的创建线程数量为Integer.MAX_VALUE，可能会创建大量的线程，从而导致OOM。

### 2.1 Spring事务@Transactional注解，什么情况下会不起作用，不回滚？

1. 数据库引擎要支持事务，如果是MySQL，注意表要使用支持事务的引擎，比如InnoDB。
MyISAM引擎不支持事务。
2. 方法必须是public，是否事务不起作用。所以检查方法是不是public的。
3. 默认情况下，Spring会对unchecked异常进行事务回滚，如果是checked异常则不回滚。
如果想checked异常也回滚，注解上面写明异常类型即可。
`@Transactional(rollbackFor=Exception.class)`
4. 是否开启了对注解的解析。
5. Spring是否扫描到你的这个包。
6. 异常是不是都被catch了。


## 3. Redis

### 3.1 keys命令

`keys pattern`，时间复杂度：O(N)，N为数据库中key的数量。
查找所有符合给定模式`pattern`的key，比如说：

- `keys *` 匹配数据库中所有`key`。
- `keys h?llo` 匹配`hello`，`hallo`和`hxllo`等。
- `keys h*llo` 匹配`hllo`和`heeeeello`等。
- `keys h[ae]llo` 匹配`hello`和`hallo`,但不匹配`hillo`。

keys的速度非常快，但是在一个大的数据库中使用它仍然可能造成性能问题。
比如一个数据库中包括很多的key，使用keys命令将阻塞请求，造成其他命令无法执行，
影响redis的性能。

如何解决这个问题? 使用scan命令。

### 3.2 Scan命令

### 3.3 Redis事务的原理

## 4. Elasticsearch

### 4.1 Elasticsearch如何进行大数据量数据迁移?

## 5. RabbitMQ

### 5.1 如何确保消息不丢失?

### 5.2 如何确保消息不重复消费?

## 6. Docker

## 7. Spark

## 8. ZooKeeper

## 9. Mysql

## 10. Oracle

## 11. Linux Shell

### 11.1 查看进程的命令是什么?

`ps`命令，常用的是`ps -ef | grep 关键字`。

### 11.2 查看端口的命令是什么?

`netstat`命令，查看端口信息。

## 12. Kubernetes