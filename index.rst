.. Redis使用教程 documentation master file, created by
   sphinx-quickstart on Thu Mar 24 20:00:03 2016.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

发售信息
----------

本书初稿已经完成，
目前书稿正在审校当中，
**预计将于 2019 年 9 月末正式发售**\ 。

在本书正式发售之前，
本网站将会陆续公开更多相关信息，
对此感兴趣的朋友请定期浏览本网站，
又或者关注作者的\ `微博 <http://weibo.com/huangz1990>`_\ 或\ `twitter <https://twitter.com/huangz1990>`_\ 。

目录
--------

- 前言

- 引言

  - Redis 简介
  - 内容编排
  - 目标读者
  - 预备工作
  - 执行命令
  - 配置服务器
  - 示例代码
  - 版本说明
  - 读者服务器网站
  - 启程！

**第一部分：数据结构与应用**

- 字符串（String）

  - SET：为字符串键设置值
  - GET：获取字符串键的值
  - GETSET：获取旧值并设置新值
  - 示例：缓存
  - 示例：锁
  - MSET：一次为多个字符串键设置值
  - MGET：一次获取多个字符串键的值
  - MSETNX：只在键不存在的情况下，一次为多个字符串键设置值
  - 示例：储存文章信息
  - STRLEN：获取字符串值的字节长度
  - 字符串值的索引
  - GETRANGE：获取字符串值指定索引范围上的内容
  - SETRANGE：对字符串值的指定索引范围进行设置
  - 示例：给文章储存程序加上文章长度计数功能和文章预览功能
  - APPEND：追加新内容到值的末尾
  - 示例：储存日志
  - 使用字符串键储存数字值
  - INCRBY、DECRBY：对整数值执行加法操作和减法操作
  - INCR、DECR：对整数值执行加一操作和减一操作
  - INCRBYFLOAT：对数字值执行浮点数加法操作
  - 示例：ID 生成器
  - 示例：计数器
  - 示例：限速器
  - 重点回顾

  |

- 散列（Hash）

  - 散列简介
  - HSET：为字段设置值
  - HSETNX：只在字段不存在的情况下为它设置值
  - HGET：获取字段的值
  - 示例：实现短网址生成程序
  - HINCRBY：对字段储存的整数值执行加法或减法操作
  - HINCRBYFLOAT：对字段储存的数字值执行浮点数加法或减法操作
  - 示例：使用散列键重新实现计数器
  - HSTRLEN：获取字段值的字节长度
  - HEXISTS：检查字段是否存在
  - HDEL：删除字段
  - HLEN：获取散列包含的字段数量
  - 示例：实现用户登录会话
  - HMSET：一次为多个字段设置值
  - HMGET：一次获取多个字段的值
  - HKEYS、HVALS、HGETALL：获取所有字段、所有值或者所有字段和值
  - 示例：储存图数据
  - 示例：使用散列键重新实现文章储存程序
  - 散列与字符串
  - 重点回顾

  |

- 列表（List）

  - LPUSH：将元素推入到列表左端
  - RPUSH：将元素推入到列表右端
  - LPUSHX、RPUSHX：只对已存在的列表执行推入操作
  - LPOP：弹出列表最左端的元素
  - RPOP：弹出列表最右端的元素
  - RPOPLPUSH：将右端弹出的元素推入到左端
  - 示例：先进先出队列
  - LLEN：获取列表的长度
  - LINDEX：获取指定索引上的元素
  - LRANGE：获取指定索引范围上的元素
  - 示例：分页
  - LSET：为指定索引设置新元素
  - LINSERT：将元素插入到列表
  - LTRIM：修剪列表
  - LREM：从列表中移除指定元素
  - 示例：待办事项列表
  - BLPOP：阻塞式左端弹出操作
  - BRPOP：阻塞式右端弹出操作
  - BRPOPLPUSH：阻塞式弹出并推入操作
  - 示例：带有阻塞功能的消息队列
  - 重点回顾

  |

- 集合（Set）

  - SADD：将元素添加到集合
  - SREM：从集合中移除元素
  - SMOVE：将元素从一个集合移动到另一个集合
  - SMEMBERS：获取集合包含的所有元素
  - SCARD：获取集合包含的元素数量
  - SISMEMBER：检查给定元素是否存在于集合
  - 示例：唯一计数器
  - 示例：打标签
  - 示例：点赞
  - 示例：投票
  - 示例：社交关系
  - SRANDMEMBER：随机地获取集合中的元素
  - SPOP：随机地从集合里面移除指定数量的元素
  - 示例：抽奖
  - SINTER、SINTERSTORE：对集合执行交集计算
  - SUNION、SUNIONSTORE：对集合执行并集计算
  - SDIFF、SDIFFSTORE：对集合执行差集计算
  - 示例：共同关注与推荐关注
  - 示例：使用反向索引构建商品筛选器
  - 重点回顾

  |

- 有序集合（Sorted Set）

  - ZADD：添加或更新成员
  - ZREM：移除指定的成员
  - ZSCORE：获取成员的分值
  - ZINCRBY：对成员的分值执行自增或自减操作
  - ZCARD：获取有序集合的大小
  - ZRANK、ZREVRANK：获取成员在有序集合中的排名
  - ZRANGE、ZREVRANGE：获取指定索引范围内的成员
  - 示例：排行榜
  - ZRANGEBYSCORE、ZREVRANGEBYSCORE：获取指定分值范围内的成员
  - ZCOUNT：统计指定分值范围内的成员数量
  - 示例：时间线
  - ZREMRANGEBYRANK：移除指定排名范围内的成员
  - ZREMRANGEBYSCORE：移除指定分值范围内的成员
  - ZUNIONSTORE、ZINTERSTORE：有序集合的并集运算和交集运算
  - 示例：商品推荐
  - ZRANGEBYLEX、ZREVRANGEBYLEX：返回指定字典序范围内的成员
  - ZLEXCOUNT：统计位于字典序指定范围内的成员数量
  - ZREMRANGEBYLEX：移除位于字典序指定范围内的成员
  - 示例：自动补全
  - ZPOPMAX、ZPOPMIN：弹出分值最高和最低的成员
  - BZPOPMAX、BZPOPMIN：阻塞式最大/最小元素弹出操作
  - 重点回顾

  |

- HyperLogLog

  - HyperLogLog 简介
  - PFADD：对集合元素进行计数
  - PFCOUNT：返回集合的近似基数
  - 示例：优化唯一计数器
  - 示例：检测重复信息
  - PFMERGE：计算多个 HyperLogLog 的并集
  - 示例：实现每周/月度/年度计数器
  - 重点回顾

  |

- 位图（bitmap）

  - SETBIT：设置二进制位的值
  - GETBIT：获取二进制位的值
  - BITCOUNT：统计被设置的二进制位数量
  - 示例：用户行为记录器
  - BITPOS：查找第一个指定的二进制位值
  - BITOP：执行二进制位运算
  - 示例：0-1矩阵
  - BITFIELD：在位图中储存整数值
  - 示例：紧凑计数器
  - 使用字符串命令对位图进行操作
  - 重点回顾

  |

- 地理坐标（GEO）

  - GEOADD：储存坐标
  - GEOPOS：获取指定位置的坐标
  - GEODIST：计算两个位置之间的直线距离
  - 示例：具有基本功能的用户地理位置程序
  - GEORADIUS：查找指定坐标半径范围内的其他位置
  - GEORADIUSBYMEMBER：查找指定位置半径范围内的其他位置
  - 示例：查找附近用户
  - GEOHASH：获取指定位置的 Geohash 值
  - 使用有序集合命令操作 GEO 数据
  - 重点回顾

  |

- 流（Stream）

  - XADD：追加新元素到流的末尾
  - XTRIM：对流进行修剪
  - XDEL：移除指定元素
  - XLEN：获知流包含的元素数量
  - XRANGE、XREVRANGE：访问流中元素
  - XREAD：以阻塞或非阻塞方式获取流元素
  - 示例：消息队列
  - 消费者组
  - XGROUP：管理消费者组
  - XREADGROUP：读取消费者组中的消息
  - XPENDING：显示待处理消息的相关信息
  - XACK：将消息标记为“已处理”
  - XCLAIM：转移消息的归属权
  - XINFO：查看流和消费者组的相关信息
  - 示例：为消息队列提供消费者组功能
  - 重点回顾

**第二部分：附加功能**

- 数据库

  - SELECT：切换至指定的数据库
  - KEYS：获取所有与给定匹配符相匹配的键
  - SCAN：以渐进方式迭代数据库中的键
  - 示例：构建数据库迭代器
  - RANDOMKEY：随机返回一个键
  - SORT：对键的值进行排序
  - EXISTS：检查给定键是否存在
  - DBSIZE：获取数据库包含的键值对数量
  - TYPE：查看键的类型
  - 示例：数据库取样程序
  - RENAME、RENAMENX：修改键名
  - MOVE：将给定的键移动到另一个数据库
  - DEL：移除指定的键
  - UNLINK：以异步方式移除指定的键
  - FLUSHDB：清空当前数据库
  - FLUSHALL：清空所有数据库
  - SWAPDB：互换数据库
  - 示例：使用 SWAPDB 命令实行在线替换数据库
  - 重点回顾

  |

- 自动过期

  - EXPIRE、PEXPIRE：设置生存时间
  - 示例：带有自动移除特性的缓存程序
  - SET 命令的 EX 选项和 PX 选项
  - 示例：带有自动释放特性的锁
  - EXPIREAT、PEXPIREAT：设置过期时间
  - TTL、PTTL：获取键的剩余生存时间
  - 示例：自动过期的登录会话
  - 示例：自动淘汰冷门数据
  - 重点回顾

  |

- 流水线与事务

  - 流水线
  - 示例：使用流水线优化随机键创建程序
  - 事务
  - 示例：实现 MLPOP 函数
  - 带有乐观锁的事务
  - 示例：带有身份验证功能的锁
  - 示例：带有身份验证功能的计数信号量
  - 重点回顾

  |

- Lua 脚本

  - EVAL：执行脚本
  - 示例：使用脚本重新实现带有身份验证功能的锁
  - 示例：实现 LPOPRPUSH 命令
  - SCRIPT LOAD 和 EVALSHA ：缓存并执行脚本
  - 脚本管理
  - 内置函数库
  - 脚本调试
  - 重点回顾

  |

- 持久化

  - RDB 持久化
  - AOF 持久化
  - RDB-AOF 混合持久化
  - 同时使用 RDB 持久化和 AOF 持久化
  - 无持久化
  - SHUTDOWN：关闭服务器
  - 重点回顾

  |

- 发布与订阅

  - PUBLISH：向频道发送消息
  - SUBSCRIBE：订阅频道
  - UNSUBSCRIBE：退订频道
  - PSUBSCRIBE：订阅模式
  - PUNSUBSCRIBE：退订模式
  - PUBSUB：查看发布与订阅的相关信息
  - 示例：广播系统
  - 重点回顾

  |

- 模块

  - 模块的管理
  - ReJSON 模块
  - RediSQL 模块
  - RediSearch 模块
  - 重点回顾

**第三部分：多机功能**

- 复制

  - REPLICAOF：将服务器设置为从服务器
  - ROLE：查看服务器的角色
  - 数据同步
  - 无需硬盘的复制
  - 降低数据不一致的出现几率
  - 可写的从服务器
  - 示例：使用从服务器处理复杂计算操作
  - 脚本复制
  - 重点回顾

  |

- Sentinel

  - 启动 Sentinel
  - Sentinel 网络
  - Sentinel 管理命令
  - 在线配置 Sentinel
  - 实例：使用 redis-py 管理 Sentinel
  - 重点回顾

  |

- 集群

  - 基本特性
  - 搭建集群
  - 实例：使用客户端连接集群
  - 散列标签
  - 打开/关闭从节点的读命令执行权限
  - 集群管理工具 redis-cli
  - 集群管理命令
  - 槽管理命令
  - 重点回顾

**附录**

- 附录 A ：Redis 安装方法

  - 免安装试运行
  - 在 macOS 上安装
  - 在 Linux 上安装
  - 在 Windows 上安装

  |

- 附录 B ：redis-py 安装方法


作者简介
------------

.. image:: image/huangz.png
   :align: right
   :scale: 35%

本书作者黄健宏自 2011 年接触 Redis 起就一直在持续地学习和研究 Redis ，
并通过写书、翻译、讲授课程等方式与大家分享他了解到的 Redis 知识。

黄健宏分别是\ `《Redis 设计与实现》 <http://redisbook.com>`_\ 和\ `《Redis 实战》 <http://redisinaction.com>`_\ 这两本畅销 Redis 图书的作者和译者。
与此同时他还长期翻译并维护着在线的中文 Redis 文档\ `《Redis 命令参考》 <http://www.redisdoc.com>`_\ ，
这个文档每天都为数量众多的 Redis 使用者提供服务。

作为早期接触 Redis 并且一直深入研究 Redis 的技术人员，
黄健宏对 Redis 的应用和源码有深入的了解，
他希望通过这本《Redis使用手册》向读者传授最常用和最核心的 Redis 知识，
帮助读者了解 Redis 和用好 Redis 。

关于黄健宏的更多信息以及他的联系方式可以在他的个人网站\ `huangz.me <http://huangz.me>`_\ 上面找到。

