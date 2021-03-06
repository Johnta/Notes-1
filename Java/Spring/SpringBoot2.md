`目录 start`
 
- [SringBoot2](#sringboot2)
    - [从1迁移到2](#从1迁移到2)
    - [新特性](#新特性)
    - [Web模块](#web模块)
        - [Web容器](#web容器)
            - [Tomcat](#tomcat)
            - [Jetty](#jetty)
        - [跨域](#跨域)
        - [监听SpringBoot启动和关闭](#监听springboot启动和关闭)
    - [数据库模块](#数据库模块)
        - [Relation Database](#relation-database)
            - [多数据源](#多数据源)
        - [No Relation Database](#no-relation-database)

`目录 end` |_2018-06-19_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************
# SringBoot2
## 从1迁移到2
> 变化比较大 [官方说明对比1所更改的文档](https://github.com/spring-projects/spring-boot/wiki/Spring-Boot-2.0-Migration-Guide)

[spring boot 2.0 半月的实战_阶段性总结1](https://blog.csdn.net/freexyxyz/article/details/79003438)
[SpringBoot2.0 jpa多数据源配置 ](https://blog.csdn.net/tianyaleixiaowu/article/details/78905149)
[Springboot2.0 升级（Gradle工程) ](https://my.oschina.net/tangdu/blog/1625336)
[使用精简版jdk9在docker上运行springboot2 ](https://my.oschina.net/go4it/blog/1623004)
[ Spring Boot 2.0系列文章(一)：Spring Boot 2.0 迁移指南 ](http://www.54tianzhisheng.cn/2018/03/06/SpringBoot2-Migration-Guide/)
## 新特性
> [Spring Boot 2.0系列文章(二)：Spring Boot 2.0 新特性详解 ](http://www.54tianzhisheng.cn/2018/03/06/SpringBoot2-new-features/)

## Web模块
### Web容器
#### Tomcat 
> org.springframework.boot:spring-boot-starter-web 依赖中默认包含了Tomcat

#### Jetty
> [Spring Boot – Configure Jetty Server](https://howtodoinjava.com/spring/spring-boot/configure-jetty-server/)

### 跨域
> [SpringBoot2的跨域配置](https://blog.csdn.net/kcp606/article/details/80036420)
> 最终是采用的Nginx进行反向代理，将后台服务放在前台服务子路径下

### 监听SpringBoot启动和关闭
> [参考博客 监听Spring Boot的启动、停止、重启、关闭 ](http://blog.sina.com.cn/s/blog_70ae1d7b0102wfq2.html) `但是这个博客是老版本的Boot, 自己瞎猜, 竟然下面的配置能够成功`
```java
@Configuration
public class Listener implements ApplicationListener {
  @Override
  public void onApplicationEvent(ApplicationEvent event) {
    // 在这里可以监听到Spring Boot的生命周期
    if (event instanceof ApplicationEnvironmentPreparedEvent) {
      System.out.println("初始化环境变量");
    } else if (event instanceof ApplicationPreparedEvent) {
      System.out.println("初始化完成");

    } else if (event instanceof ContextRefreshedEvent) {
      System.out.println("应用刷新");

    } else if (event instanceof ApplicationReadyEvent) {
      System.out.println("应用已启动完成");
    } else if (event instanceof ContextStartedEvent) {
      System.out.println("应用启动");

    } else if (event instanceof ContextStoppedEvent) {
      System.out.println("应用停止");

    } else if (event instanceof ContextClosedEvent) {
      System.out.println("应用关闭");
    }
  }
}
```
- 但是只有应用刷新, 应用启动完成, 应用关闭是能够正常监听到的

## 数据库模块



### Relation Database

#### 多数据源
- [参考博客: Spring Boot 2.0 多数据源编程 原](https://my.oschina.net/chinesedragon/blog/1647846) | [源码](https://gitee.com/shupengluo/SpringBoot2.0-MultiDataSource)

### No Relation Database