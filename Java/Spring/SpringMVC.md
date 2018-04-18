`目录 start`
 
- [SpringMVC](#springmvc)
    - [MVC思想](#mvc思想)
        - [原理](#原理)
    - [API](#api)
    - [配置](#配置)
    - [使用](#使用)
        - [自定义拦截器](#自定义拦截器)
        - [Q&A](#q&a)

`目录 end` |_2018-04-18_| [码云](https://gitee.com/kcp1104) | [CSDN](http://blog.csdn.net/kcp606) | [OSChina](https://my.oschina.net/kcp1104)
****************************************

# SpringMVC

## MVC思想
> [参考博客](http://blog.csdn.net/besley/article/details/8479943)
![图](https://raw.githubusercontent.com/Kuangcp/ImageRepos/master/Tech/Model/mvc.png)

### 原理
> 统一使用一个Servlet 进行请求的收发, 通过配置的URL对应的方法, 进行调用, 然后返回视图解析器进行渲染

************************
## API 
> [简洁的API设计](http://www.csdn.net/article/2013-05-02/2815115-stop-designing-fragile-web-api)

***********
## SpringBoot中配置
> 如果引入了别的模板引擎就不需要配置解析器，不然就要配

- 没有用模板引擎themleaf的依赖，配置前后缀并没有用, 这是什么原因？？？ classpath:/templates/  .html  
    - 单纯的想写个前后端分离不行?
> [SpringBoot 较完善的入门博客](https://www.tianmaying.com/tutorial/spring-mvc-quickstart)

***********************
## 传统项目配置
> [参考](https://www.cnblogs.com/Sinte-Beuve/p/5730553.html)

### 配置依赖
#### Maven
```xml
<properties>
    <spring.version>4.3.9.RELEASE</spring.version>
</properties>
......
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-web</artifactId>
    <version>${spring.version}</version>
</dependency>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-webmvc</artifactId>
    <version>${spring.version}</version>
</dependency>
<!-- 如果使用JSP作为视图层,还需 -->
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>javax.servlet-api</artifactId>
    <version>3.1.0</version>
</dependency>
<dependency>
    <groupId>javax.servlet.jsp</groupId>
    <artifactId>jsp-api</artifactId>
    <version>2.2</version>
</dependency>
<dependency>
    <groupId>javax.servlet</groupId>
    <artifactId>jstl</artifactId>
    <version>1.2</version>
</dependency>
<dependency>
```
#### Gradle
```groovy
compile('org.springframework:spring-web:4.3.9.RELEASE')
compile('org.springframework:spring-webmvc:4.3.9.RELEASE')
```
### web.xml

```xml
  <servlet>
    <servlet-name>mysql</servlet-name>
    <servlet-class>org.springframework.web.servlet.DispatcherServlet</servlet-class>
    <init-param>
      <param-name>contextConfigLocation</param-name>
      <param-value>/WEB-INF/applicationContext.xml</param-value>
    </init-param>
    <load-on-startup>1</load-on-startup>
  </servlet>

  <listener>
    <listener-class>org.springframework.web.context.ContextLoaderListener</listener-class>
  </listener>
  <servlet-mapping>
    <servlet-name>mysql</servlet-name>
    <url-pattern>/</url-pattern>
  </servlet-mapping>
```

### ApplicationContext.xml
```xml
<?xml version="1.0" encoding="UTF-8"?>
<beans xmlns="http://www.springframework.org/schema/beans"
       xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
       xmlns:context="http://www.springframework.org/schema/context"
       xmlns:mvc="http://www.springframework.org/schema/mvc"
       xsi:schemaLocation="http://www.springframework.org/schema/beans
            http://www.springframework.org/schema/beans/spring-beans-3.2.xsd
                http://www.springframework.org/schema/context
            http://www.springframework.org/schema/context/spring-context-3.2.xsd
            http://www.springframework.org/schema/mvc
            http://www.springframework.org/schema/mvc/spring-mvc.xsd">
<!--启用spring的一些annotation -->
<context:annotation-config/>
<!-- 自动扫描该包，使SpringMVC认为包下用了@controller注解的类是控制器 -->
<context:component-scan base-package="com.test.controller">
    <context:include-filter type="annotation" expression="org.springframework.stereotype.Controller"/>
</context:component-scan>
<!--HandlerMapping 无需配置，springmvc可以默认启动-->
<!--静态资源映射-->
<!--本项目把静态资源放在了WEB-INF的statics目录下，资源映射如下-->
<!--<mvc:resources mapping="/css/**" location="/WEB-INF/statics/css/"/>-->
<!--<mvc:resources mapping="/js/**" location="/WEB-INF/statics/js/"/>-->
<!--<mvc:resources mapping="/image/**" location="/WEB-INF/statics/image/"/>-->
<!--但是项目部署到linux下发现WEB-INF的静态资源会出现无法解析的情况，但是本地tomcat访问正常，因此建议还是直接把静态资源放在webapp的statics下，映射配置如下-->
<!--<mvc:resources mapping="/css/**" location="/statics/css/"/>-->
<!--<mvc:resources mapping="/js/**" location="/statics/js/"/>-->
<!--<mvc:resources mapping="/image/**" location="/statics/images/"/>-->
<!-- 配置注解驱动 可以将request参数与绑定到controller参数上 -->
<mvc:annotation-driven/>
<!-- 对模型视图名称的解析，即在模型视图名称添加前后缀(如果最后一个还是表示文件夹,则最后的斜杠不要漏了) 使用JSP-->
<!-- 默认的视图解析器 在上边的解析错误时使用 (默认使用html)- -->
<!--<bean id="defaultViewResolver" class="org.springframework.web.servlet.view.InternalResourceViewResolver">-->
    <!--<property name="viewClass" value="org.springframework.web.servlet.view.JstlView"/>-->
    <!--<property name="prefix" value="/WEB-INF/views/"/>&lt;!&ndash;设置JSP文件的目录位置&ndash;&gt;-->
    <!--<property name="suffix" value=".jsp"/>-->
<!--</bean>-->
<!-- springmvc文件上传需要配置的节点-->
<bean id="multipartResolver" class="org.springframework.web.multipart.commons.CommonsMultipartResolver">
    <property name="maxUploadSize" value="20971500"/>
    <property name="defaultEncoding" value="UTF-8"/>
    <property name="resolveLazily" value="true"/>
</bean>
</beans>
```
### 创建类
包 com.test.controller 下创建一个类
```java
@RestController
@RequestMapping("/hi")
public class Hi {
    @RequestMapping("/hi")
    public String hi(){
        return "Hi";
    }
}
```
************************
## 使用
> 在Springboot框架中，static templates 文件夹下分别代表了tomcat管理的静态文件和MVC负责跳转的HTML文件或JSP文件
> 在static中对于路径的使用一定要带上应用路径，而在templates中就只要写相对路径即可

### 自定义拦截器
- [相关博客](http://www.jianshu.com/p/f14ed6ca4e56)|[相关博客](http://blog.csdn.net/catoop/article/details/50501696)

`定义拦截器类`
```java
public class MythInterceptor extends HandlerInterceptorAdapter{
    @Override
    public boolean preHandle(HttpServletRequest request, HttpServletResponse response, Object handler) throws Exception {
        Long startTime = System.currentTimeMillis();
        request.setAttribute("startTime",startTime);
        return true;// true就继续跳转，false就停止
    }
    @Override
    public void postHandle(HttpServletRequest request, HttpServletResponse response, Object handler, ModelAndView modelAndView) throws Exception {
        long startTime = (Long)request.getAttribute("startTime");
        request.removeAttribute("startTime");
        Long endTime = System.currentTimeMillis();
        log.info(request.getRequestURL()+"发起请求耗时:[ "+ (endTime - startTime) +"  ms]");
    }
}
```
`配置MVC的配置类`
```java
@Configuration
public class WebMvcConfig extends WebMvcConfigurerAdapter{
    //自定义拦截器bean
    @Bean
    public MythInterceptor mythInterceptor(){
        return new MythInterceptor();
    }
    //注册拦截器
    @Override
    public void addInterceptors(InterceptorRegistry registry) {
        //拦截器的URL正则
        registry.addInterceptor(mythInterceptor()).addPathPatterns("/**");
        super.addInterceptors(registry);
    }
    // 自定义错误页面 需要放在静态资源下面
    @Bean
    public EmbeddedServletContainerCustomizer containerCustomizer() {
        return (container -> {
            ErrorPage error401Page = new ErrorPage(HttpStatus.FORBIDDEN, "/500.html");
            ErrorPage error404Page = new ErrorPage(HttpStatus.NOT_FOUND, "/404.html");
            ErrorPage error500Page = new ErrorPage(HttpStatus.INTERNAL_SERVER_ERROR, "/500.html");
            container.addErrorPages(error401Page, error404Page, error500Page);
        });
    }
}
```



### Q&A
URL 中带了 jsessionid 参数，导致页面各种问题
- 一种原因：禁用cookie导致的
- 最终解决： chrome中在设置里清除localhost的所有cookie和缓存

- [解决问题参考博客](https://yq.aliyun.com/articles/101169)
- [jsessionid的作用](http://sxsoft.blog.163.com/blog/static/190412229200911103116773)
