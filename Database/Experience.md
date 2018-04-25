`目录 start`
 
- [数据库的使用体会](#数据库的使用体会)
    - [关系型数据库](#关系型数据库)
        - [SQLServer](#sqlserver)
        - [Mysql](#mysql)
        - [Oracle](#oracle)
        - [Postgresql](#postgresql)
    - [非关系型数据库](#非关系型数据库)
        - [Redis](#redis)
        - [MangoDB](#mangodb)
    - [结构设计](#结构设计)
        - [基本表的设计](#基本表的设计)
            - [关于主键的设计](#关于主键的设计)
        - [视图的设计](#视图的设计)
    - [数据库中间件](#数据库中间件)

`目录 end` |_2018-04-25_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************
# 数据库的使用体会
> [码农翻身:爱炫耀的数据库老头儿](https://mp.weixin.qq.com/s?__biz=MzAxOTc0NzExNg==&mid=2665514001&idx=1&sn=17b72c3e69db6c4277e3045c699b7b6b&chksm=80d67c52b7a1f5446020826841869221873f4578524181384592839d19c4810dc68807117e13&scene=21#wechat_redirect) `事务,undo日志`

> [DB-Engines Ranking](https://db-engines.com/en/ranking)
## 关系型数据库
> [参考博客: 什么是数据库ACID?](http://www.jdon.com/concurrent/acid-database.html)

### SQLServer
### Mysql
> 结合docker配置很快，就是默认编码为什么不直接设置utf8，每次要改

### Oracle
> 十分的庞大, 学习了他理念的设计, 感受良多

### Postgresql
> 听说性能强劲, 但是自己没有测试实践过, 命令行倒是很简洁, 就是数据库的逻辑理念和MySQL不一样, 迁移过去要稍微看下基础

## 非关系型数据库
### Redis
> 数据类型丰富,处理非关系型并且结构化的数据十分方便, 结合Python使用就行云流水一般了

### MangoDB
> 正准备学习的文档性数据库, 混合类型: 关系型非关系型

***********************
## 结构设计
### 基本表的设计
#### 关于主键的设计
> 我哥提出, 基本表中连主键的约束都不要了, 全部由后台的代码进行约束处理

- 如果使用的需要高并发，数据库经常迁移，拆分，分布式，使用UUID,GUID最佳
- 如果是小型项目，使用整型自增即可，排序方便节约内存

### 视图的设计

## 数据库中间件
> [MyCat：开源分布式数据库中间件](https://www.csdn.net/article/2015-07-16/2825228)


