
[Golang面试问题汇总](https://www.yuque.com/go-interview/set/qhe51m)




- 事务消息了解吗,rocketmq的事务消息是怎么实现的?
- kafka是如何保证不丢消息的
- kafka为什么快? 零拷贝说一下,零拷贝有几种实现?
- kafka的IR和高水位是什么意思，说一下
- kafka主要解决什么问题，你们项目里是怎么用的
- kafka如何保证消息的有序性
- kafka如果消息堆积了如何处理



基础篇

- 一条SQL语句在MySQL中如何执行的？
- 说一下数据库的三大范式
- count(1)、count(*) 与 count(列名) 的区别？
- MySQL中int(20)和char(20)以及varchar(20)的区别
- 分组查询需要注意什么条件？

事务篇

- ACID了解吗，MySQL是用什么机制保证的？两阶段提交能讲一下嘛？
- redo log和undo log说一下，什么是WAL技术?
- redo log和bin log的区别
- MySQL的binlog有有几种录入格式？分别有什么区别？
- MySQL的隔离级别有几种，默认的隔离级别是什么，互联网常用的隔离级别是什么？隔离级别与锁的关系
- 什么是幻读，脏读，不可重复读呢？MySQL是怎么处理幻读的？


锁篇

- MySQL中有哪几种锁，列举一下？
- 锁分哪几种，行锁是锁在哪里的？
- 间隙锁了解吗？唯一索引有间隙锁吗？
- 数据库的乐观锁和悲观锁你怎么理解的？select for update有什么含义，
- MVCC是什么，是如何实现的，算法说一下？


索引篇

- MySQL引擎Innodb和Myisam有哪些区别？
- InnoDB引擎的4大特性你能说一下嘛？
- 了解change buffer 的使用场景吗，说一说
- MySQL的innodb的索引是怎么实现的？为什么用B+树，优点是什么，与B树的区别是什么？
- B+树索引的最底层单元是什么？什么决定了B+树的高度？B+树的叶子节点是单向链表还是双向链表?
- 聚集索引与非聚集索引的区别
- 非聚集索引一定会回表查询吗？
- InnoDB引擎中的索引策略
- 索引的创建原则
- 索引什么情况下失效，联合索引什么时候失效，覆盖索引、回表等这些，了解过吗？
- 为什么不用UUID做主键，影响的写入性能还是读取性能？如果业务上能保证唯一性，那么还需要建唯一索引吗？会影响写入性能吗？
- MySQL 自增主键什么情况下顺序会出现断裂？
- 假设一个a+b+c 的组合索引，只用 b+c 可以查到吗?


TroubleShooting&&优化篇

- 慢查询怎么处理？explain的type有几种类型，你常见的有哪几种？
- MySQL的高可用是怎么做的
- MySQL 遇到过死锁问题吗，你是如何解决的？
- 数据库自增主键可能遇到什么问题？自增主键用完了怎么办？
- MySQL数据库CPU飙升的话，需要怎么处理？
- 你们的MySQL数据量有多大，如果某个表有近千万数据，如何分库分表？
- 超大分页怎么处理？
- 你是如何监控你们的数据库的？你们的慢日志都是怎么查询的？
- 分库分表以后如何查询，如何做分布式事务
- MySQL主从同步的过程是什么样的？
- MySQL的主从延迟，你知道怎么解决吗？
- 日常工作中你是怎么优化SQL的？
- Explain执行计划是做什么的？可以说一下嘛？
- 你知道Profile吗？使用场景是什么呢？
- 项目中数据库连接池是怎么用的?为什么需要数据库连接池呢


---

- elasticsearch原理，基于哪个库实现的？mysql的like查询和elasticsearch查询对比，时间复杂度
- kubernetes有哪些组件
- kubernetes调度一个pod的整个流程是怎么样的
- docker的实现原理说一下

---

- 谈谈Mutex的饥饿模式和正常模式
- Mutex锁释放后，等待中的 goroutine 中哪一个会优先获取 Mutex 呢？
- 目前 Mutex 的 state 字段有几个意义，这几个意义分别是由哪些字段表示的？等待一个 Mutex 的 goroutine 数最大是多少？是否能满足现实的需求？
- RWMutex使用过吗，主要用在什么样的场景，有哪几种方法，解决reader-writers的问题有几种实现方式，go中的RWMutex使用哪种方式？
- Mutex和RWMutex使用过程中如何规避死锁问题，go可以检测吗？
- 谈谈WaitGroup的常见用法和使用过程中的常见错误
- cond和once使用过吗，cond的常见用法和使用过程中的常见错误，什么场景下使用cond要比channel更好，once的实现和常见错误
- map 如何实现、原理，sync.map是如何实现的（云账户，最右面试），如何实现线程安全的map？
- Sync.pool的特点及使用方法
- Context的适用场景和基本使用


---

面试题总结

- redis常见问题
- redis的数据类型有哪几种，你们用了哪几种，是怎么用的
- redis string类型的底层数据结构是怎么样的？
- redis为什么快
- redis是怎么实现原子性的（腾讯云问的）
- redis为什么要用单线程，最新的redis 6.0用了多线程，是怎么实现的，你了解吗？
- redis的跳表了解吗，数据结构是怎么样的，查询的时间复杂度是多少
- 你们的redis是哨兵模式还是集群模式，具体是怎么配置的，了解吗？
- redis的分布式锁用过吗，怎么用的？
- redis单实例的QPS是多少，有测过吗？最新的6.0 QPS多少知道吗？
- redis的大 key 多大算大？单个redis实例建议多大内存？
- 写时复制了解吗，在redis哪里用到了？在计算机的哪些场景或者算法里有用到？（腾讯云问的）
- redis的网卡如果被打爆了，怎么办？redis缓存和本地缓存是怎么配合使用的，数据的一致性是如何解决的？（好未来架构师问的）


mysql

- 你们mysql引擎用的什么？mysql innodb的索引是怎么实现的？为什么用B+树，优点是什么，与B树的区别是什么？
- B+树索引的最底层单元是什么？什么决定了B+树的高度？B+树的叶子节点是单向链表还是双向链表?
- 怎么加索引，索引什么情况下失效，联合索引什么时候失效，覆盖索引了解吗？
- 为什么不用uuid做主键，影响的写入性能还是读取性能？如果业务上能保证唯一性，那么还需要建唯一索引吗？会影响写入性能吗？
- mysql的隔离级别有几种，默认的隔离级别是什么，互联网常用的隔离级别是什么？
- ACID了解吗，mysql是用什么机制保证的，redo log和undo log说一下
- MVCC是什么，是如何实现的，算法说一下？
- 幻读是什么意思？mysql是怎么处理幻读的？间隙锁了解吗？唯一索引有间隙锁吗？
- 锁分哪几种，行锁是锁在哪里的？
- mysql 主从同步的过程是什么样的
- mysql的高可用是怎么做的
- 慢查询怎么处理？explain的type有几种类型，你常见的有哪几种？
- 你们的mysql数据量有多大，如何分库分表，分库分表以后如何查询，如何做分布式事务
- 怎么优化mysql
- 了解TiDB吗，TiDB是如何实现的


kafka


- 事务消息了解吗,rocketmq的事务消息是怎么实现的?
- kafka是如何保证不丢消息的
- kafka为什么快? 零拷贝说一下,零拷贝有几种实现?
- kafka的IR和高水位是什么意思，说一下
- kafka主要解决什么问题，你们项目里是怎么用的
- kafka如何保证消息的有序性
- kafka如果消息堆积了如何处理



项目：


- 介绍一下你们的项目
- 你们项目的服务对象是谁，解决了他们的什么问题
- 你们的并发量多大，高并发是如何解决的
- 画一下你们项目的架构图
- 你们项目里的难点，优点，有什么可以改进的地方




- TCP三次握手，四次挥手说一下。为什么需要三次握手，最后一次如果没有行不行，会有什么问题？TIME_WAIT的作用是什么？2MSL是多长？线上大量的close_wait和time_wait该如何解决？
- http2.0的优点说一下。了解QUIC吗？怎么实现的？
- https的握手过程说一下。证书是如何验证的？为什么不用非对称加密通信？
- 浏览器输入一个url到返回，整个过程说一下，都用到了哪些协议？浏览器的渲染过程了解吗？
- 一台服务器最多可以建立多少个TCP链接，为什么？



- 怎么查看端口占用情况，怎么查看进程打开了哪些文件
- 如何查看内存，如何查看磁盘，du是什么意思
- linux的文件系统了解吗，inode了解吗
- 线上服务器问题如何排查。cpu loader average什么意思，cpu利用率什么意思

- 微服务的优点是什么
- 微服务的服务拆分你们是怎么做的
- 微服务的服务治理你们是怎么做的，都包括哪些模块
- RPC具体是怎么实现的，有哪些组件可以说一下吗？RPC的连接池是怎么实现的，数据结构是什么样的，链接如何保活（腾讯云）



- 协程和线程的区别
- goroutine初始栈大小，上下文如何切换，存在哪里
- GMP说一下，P有多少个，G有多少个，M有多少个。系统调用的时候M会如何，网络IO的时候M会怎样。
- Go的GC说一下，扫描从哪里发起？
- Go的内存分配说一下
- Go有哪些坑？for range为什么会有坑？
- Go的map是如何实现的，是并发安全的吗？sync.map是如何实现的？
- CAS知道吗，在Go的哪些地方用到了？
- sync.pool是如何实现的
- channel的优点是什么，如何实现的（腾讯云）
- channel的使用场景。close channel的时候发生了什么？
- Go select是怎么用的，具体如何实现的？
- 如果我希望主协程通知并且等待子协程关闭，应该如何做？context了解吗，怎么用的，如何实现的？
- 写一个生产者消费者模型吧
- Gin的中间件是如何实现的
- Gin的一次请求整个过程是如何调用的
- Gin的基数树知道吗，说一下
- Gin请求里的request buffer可以读几次（美餐）
- goroutine的泄露如何排查？pprof了解吗，说一下


算法题：

- 反转单链表
- 判断链表里是否有环
- 八皇后问题
- 找最大的K个数，有O(N)的算法吗？
- 最大回文子串
- 最近的平方根。比如10的结果是3
- 把两个链表连起来。比如AB两个链表，顺序是A1 B1 A2 B2 A3 B3...


---


[data-structures-questions/src/chapter05/golang.01.md at master · KeKe-Li/data-structures-questions · GitHub](https://github.com/KeKe-Li/data-structures-questions/blob/master/src/chapter05/golang.01.md)



- Golang中除了加Mutex锁以外还有哪些方式安全读写共享变量
- 无缓冲Chan的发送和接收是否同步
- Golang并发机制以及它所使用的CSP并发模型
- Golang中常用的并发模型
- Go中对nil的Slice和空Slice的处理是一致的吗
- 协程和线程和进程的区别
- Golang的内存模型中为什么小对象多了会造成GC压力
- Go中数据竞争问题怎么解决
- 什么是channel，为什么它可以做到线程安全
- Golang垃圾回收算法
- GC的触发条件
- Go的GPM如何调度
- 并发编程概念是什么
- Go语言的栈空间管理是怎么样的
- Goroutine和Channel的作用分别是什么
- 怎么查看Goroutine的数量
- Go中的锁有哪些
- 怎么限制Goroutine的数量
- Channel是同步的还是异步的
- Goroutine和线程的区别
- Go的Struct能不能比较
- Go的defer原理是什么
- Go的select可以用于什么
- Go的Context包的用途是什么
- Go主协程如何等其余协程完再操作
- Go的Slice如何扩容
- Go中的map如何实现顺序读取
- Go中CAS是怎么回事
- Go中的逃逸分析是什么
- Go值接收者和指针接收者的区别
- Go的对象在内存中是怎样分配的
- 栈的内存是怎么分配的
- 堆内存管理怎么分配的
- Go中的defer函数使用下面的两种情况下结果是什么
- 在Go函数中为什么会发生内存泄露
- Go中new和make的区别
- G0的作用
- Go中的锁如何实现
- Go中的channel的实现
- Go中的map的实现
- Go中的http包的实现原理
- Goroutine发生了泄漏如何检测
- Go函数返回局部变量的指针是否安全
- Go中两个Nil可能不相等吗
- Goroutine和KernelThread之间是什么关系
- 为何GPM调度要有P
- 如何在goroutine执行一半就退出协程




- Mysql索引用的是什么算法
- Mysql事务的基本要素
- Mysql的存储引擎
- Mysql事务隔离级别
- Mysql高可用方案有哪些
- Mysql中utf8和utf8mb4区别
- Mysql中乐观锁和悲观锁区别
- Mysql索引主要是哪些
- Mysql联合索引最左匹配原则
- 聚簇索引和非聚簇索引区别
- 如何查询一个字段是否命中了索引
- Mysql中查询数据什么情况下不会命中索引
- Mysql中的MVCC是什么
- Mvcc和Redolog和Undolog以及Binlog有什么不同
- Mysql读写分离以及主从同步
- InnoDB的关键特性
- Mysql如何保证一致性和持久性
- 为什么选择B+树作为索引结构
- InnoDB的行锁模式
- 哈希(hash)比树(tree)更快，索引结构为什么要设计成树型
- 为什么索引的key长度不能太长
- Mysql的数据如何恢复到任意时间点
- Mysql为什么加了索引可以加快查询
- Explain命令有什么用
- Mysql查询条件有两个独立的索引a和b同时，Mysql使用谁




Redis基础

- Redis的数据结构及使用场景
- Redis持久化的几种方式
- Redis的LRU具体实现
- 单线程的Redis为什么快
- Redis的数据过期策略
- 如何解决Redis缓存雪崩问题
- 如何解决Redis缓存穿透问题
- Redis并发竞争key如何解决
- Redis的主从模式和哨兵模式和集群模式区别
- Redis有序集合zset底层怎么实现的
- 跳表的查询过程是怎么样的，查询和插入的时间复杂度
- redis如何分片



网络协议基础

- TCP和UDP有什么区别
- TCP中三次握手和四次挥手
- TCP的LISTEN状态是什么
- 常见的HTTP状态码有哪些
- 301和302有什么区别
- 504和500有什么区别
- HTTPS和HTTP有什么区别
- Quic有什么优点相比Http2
- Grpc的优缺点
- Get和Post区别
- Unicode和ASCII以及Utf8的区别
- Cookie与Session异同
- Client如何实现长连接
- Http1和Http2和Grpc之间的区别是什么
- Tcp中的拆包和粘包是怎么回事
- TFO的原理是什么
- TIME_WAIT的作用
- 网络的性能指标有哪些




Linux基础

- 异步和非阻塞的区别
- 虚拟内存作用是什么
- Linux查看端口占用和cpu负载
- Linux如何发送信号给一个进程
- 如何避免死锁
- 孤儿进程和僵尸进程区别
- 滑动窗口的概念以及应用
- Epoll和Select的区别
- 进程之间为什么要进行通信呢
- 输入PingIP后敲回车,发包前会发生什么
- 进程和进程间的通信方式区别和不同
- 如何查看二进制可执行文件引用的动态链接库



Algorithm和Structrues

- 哪些排序算法是稳定的
- 给定一个二叉树,判断其是否是一个有效的二叉搜索树
- 排序算法
- 如何通过递归反转单链表
- 链表和数组相比有什么优缺点
- 通常一般会用到哪些数据结构



云原生

- prometheus架构中有哪些组件以及各个组件有什么用
- k8s创建pod过程
- k8s创建deployment过程


中间件原理

- Hash冲突有什么解决办法
- 微服务架构是什么样子的
- 分布式锁实现
- 负载均衡原理是什么
- 互斥锁和读写锁和死锁问题是怎么解决
- Etcd中的Raft一致性算法原理
- Git的merge跟rebase的区别
- 如何对一个20GB的文件进行排序
- LVS原理是什么
- 为什么需要消息队列
- 高并发系统的设计与实现
- Kafka的文件存储机制
- Kafka如何保证可靠性
- Kafka是如何实现高吞吐率的
- 分布式事务有哪几种
- CAP怎么选



---

[Golang 面试题集合](https://www.yuque.com/go-interview/set/ibediq)

Golang 常见面试题目解析

- 交替打印数字和字母
- 判断字符串中字符是否全都不同
- 翻转字符串
- 判断两个给定的字符串排序后是否一致
- 字符串替换问题
- 机器人坐标计算
- 语法题目一
- 语法题目二
- goroutine和channel使用一
- 实现阻塞读的并发安全Map
- 高并发下的锁与map读写问题
- 定时与 panic 恢复
- 为 sync.WaitGroup 中Wait函数支持 WaitTimeout 功能.


Golang 理论
- Go语言的GPM调度器是什么？
- Goroutine调度策略
- goroutine调度器概述
Redis基础
- Redis 基础数据结构
- Redis中的底层数据结构
- Redis持久化的原理及优化
- Redis中内存淘汰算法实现
- Redis主从复制原理
MySQL相关
- MySQL数据库经典面试题解析
- MySQL InnoDB MVCC 机制的原理及实现
- 为什么MySQL使用B+树做索引？
面试必备算法
- 字符串之实现 Sunday 匹配
- 字符串泄漏之反转字符串(301)
- 字符串中的第一个唯一字符
- 字符串之验证回文串
- 滑动窗口最大值
- 最长公共前缀
- 两个数组的交集
- 最接近的三数之和
排序算法
- 冒泡排序
- 选择排序



---

[2020 腾讯社招Golang后端面试经验分享 - Go语言中文网 - Golang中文社区](https://studygolang.com/articles/28079)



- go的调度
- go struct能不能比较
- go defer（for defer）
- select可以用于什么
- context包的用途
- client如何实现长连接
- 主协程如何等其余协程完再操作
- slice，len，cap，共享，扩容
- map如何顺序读取
- 实现set
- 实现消息队列（多生产者，多消费者）
- 大文件排序
- 基本排序，哪些是稳定的
- http get跟head
- http 401,403
- http keep-alive
- http能不能一次连接多次请求，不等后端返回
- tcp与udp区别，udp优点，适用场景
- time-wait的作用
- 数据库如何建索引
- 孤儿进程，僵尸进程
- 死锁条件，如何避免
- linux命令，查看端口占用，cpu负载，内存占用，如何发送信号给一个进程
- git文件版本，使用顺序，merge跟rebase


技术二面 项目相关
通过腾讯会议，腾讯的两个大佬一起面试


- 项目实现爬虫的流程
- 爬虫如何做的鉴权吗
- 怎么实现的分布式爬虫
- 电商系统图片多会造成带宽过高，如何解决
- micro服务发现
- mysql底层有哪几种实现方式
- channel底层实现
- java nio和go 区别
- 读写锁底层是怎么实现的
- go-micro 微服务架构怎么实现水平部署的，代码怎么实现
- micro怎么用
- 怎么做服务发现的
- mysql索引为什么要用B+树？
- mysql语句性能评测？
- 服务发现有哪些机制
- raft算法是那种一致性算法
- raft有什么特点
- 当go服务部署到线上了，发现有内存泄露，该怎么处理




---

[GitHub - luckygopher/go-interview: go面试总结](https://github.com/luckygopher/go-interview)




---

[interview-go/question/q011.md at master · lifei6671/interview-go · GitHub](https://github.com/lifei6671/interview-go/blob/master/question/q011.md)

