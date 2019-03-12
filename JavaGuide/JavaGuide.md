# JavaGuide

## 1. Java

## 2. Spring

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
### 3.2 

## 4. Elasticsearch

## 5. RabbitMQ

## 6. Docker

## 7. Spark

## 8. ZooKeeper

## 9. Mysql

## 10. Oracle

## 11. Linux Shell

## 12. Kubernetes