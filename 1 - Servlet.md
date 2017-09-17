# Java EE - Java 企业级应用

* Java EE 介绍
* Web 容器
* Servlet
* JSP
* HTTP Session 会话
* JSP EL (表达式语言), JSTL (标准标签库), 自定义标签和函数库
* Filter 过滤器, 日志监控
___

## Java EE 介绍
> Java EE 中的内容仅是标准，具体实现交给Web服务器或者Web容器

### Java EE Brief History
* Jul 1997, Servlets 1.0
* Dec 1999, J2EE 1.2 (Servlets 2.2, JDBC 2.0, JNDI 1.0, JSP 1.2, EJB 1.1 etc.)
* Sep 2001, J2EE 1.3 (JAXP 1.1, JSTL 1.0, J2EE Connector Arch 1.0, JAAS 1.0)
* Nov 2003, J2EE 1.4 (JAX-RPC 1.1, JAXR 1.0, EJB 2.1 etc.)
* May 2006, Java EE 5 (JPA 1.0)
* Dec 2009, Java EE 6 (JAX-RS 1.1, EL 2.0), Annotation based programming, Java EE Web Profile
* Jan 2010, Oracle acquired Sun
* Jun 2013, Java EE 7 (Java API for WebSockets, JSON Processing, EL)

### Java SE 7
* try-catch-finally => try-catch-resources
```
        try (conn = getConnection()) {
            // "conn" will be auto closed after try-catch
        } catch(SQLException  e) { }
```        
* "<>" 菱形操作符
```
        Map<String, Map<string, Integer>> map = new HashMap<>();
```
* 二进制字面量 0b1100, 在数字字面量使用下划线 2_017
* 字符串用作switch语句参数

### Java SE 8
* Lambda表达式
```
        new Thread(new Runnable() {
            public void run() {}
        });
        
        new Thread(() -> {});
        
        new Thread(this::doSomething);
```
* Joda Time (java.util.Date, java.util.Calendar)

### Web 应用程序结构
#### 基本特性
* Servlet, 最基本组件, 接收/处理/响应HTTP请求
* Filter过滤器, 拦截发送给Servlet的请求, 进行数据格式化/数据压缩/认证/授权
* Listener, 在Web程序生命周期执行不同任务, 程序启动/程序关闭/HTTP会话创建和销毁
* JSP (Java Server Page), 动态页面, HTML+JSTL+JUEL, 自定义标签/国际化/本地化

#### 目录结构和WAR文件
* WAR归档文件,　简单的ZIP格式归档文件
* 目录结构
    * /Root/
    * /Root/META-INF/
    * /Root/META-INF/MANIFEST.MF
    * /Root/META-INF/Container Resources
    * /Root/WEB-INF/
    * /Root/WEB-INF/web.xml
    * /Root/WEB-INF/web-fragment.xml
    * /Root/WEB-INF/classes/
    * /Root/WEB-INF/classes/META-INF/
    * /Root/WEB-INF/classes/META-INF/App Resources
    * /Root/WEB-INF/classes/*.classes
    * /Root/WEB-INF/i18n/国际化和本地化文件
    * /Root/WEB-INF/lib/*.jar
    * /Root/WEB-INF/tags/标签文件
    * /Root/WEB-INF/tld/标签库描述符
    * /Root/浏览器可以访问的所有文件和目录
* 类加载器ClassLoaders (依据不同服务器具体实现)
    * 在Java SE中, 根加载器优先
    * 在Java EE中, 子女优先加载, 子女无法加载时请求父类加载器
* EAR 企业级应用程序归档文件
    * /Root/
    * /Root/META-INF/
    * /Root/META-INF/application.xml
    * /Root/META-INF/MANIFEST.MF
    * /Root/Module1.war
    * /Root/Module2.war
    * /Root/*.jar
***

## Web 容器
### 选择Web容器
* Apache Tomcat (最流行)
> Sun Java Web Server捐赠给Apache变成Apache Tomcat，占用内存小，配置简单和社区参与，但缺少许多Java EE组件. Apache TomEE提供了对Java EE的完整支持, 同是Tomcat社区支持. 
> Apache还提供另一个完整Java EE应用服务器 Geronimo，和TomEE都是Oracle认证的Java EE 应用服务器，而Tomcat没有认证，仅是Web容器.
* GlassFish
> 开源的社区版本和Oracle支持的商业版本. 由Tomcat核心创建, 优势是提供图形/命令/配置文件进行配置.
* JBoss & WildFly
> 开源的社区版本和Red Hat支持的商业版本. 第二流行的Web应用服务器, 提供EJB/Java EE支持，通过Java EE认证. 2014年更名为WildFly，提供完整管理工具，同Tomcat和GlassFish一样提供集群和高可用性.

* 其他容器和应用服务器
    * Jetty, Web容器
    * Tiny, Web容器
    * Oracle WebLogic, 完整的商业应用服务器
    * IBM WebSphere, 完整的商业应用服务器
### 安装Tomcat
* 下载, <https://tomcat.apache.org>
* 
```























```
## adf
