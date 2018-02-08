
| Features | Java | NET |
| -- | -- |--|
|Template Engine| Velocity, Freemaker, JSP, Thymeleaf | Razor 
|Web Framework| Angular, React, Vue|
|IOC/AOP| Spring Core | Enterprise Libraries 
|MVC| Spring MVC, Swagger | Asp.NET MVC 
|ORM| Mybatis,Hibernate | EntityFramework 
|Distribution Cache| Redis, Memecache, Tair |
|Message Bus| Kafaka, Rabbitmq, Rocketmq, Active MQ| SignalR
|Authentication| Shiro, Spring Security, SSO| Identity, Principle
|Web Container| Tomcat, Jetty, JBoss, undertow|IIS
|log| slf4j, logback, log4j| Enterprise Libraries, log4net
|Session| tbsession, spring session| 
|DB connection pool| druid,tomcat-jdbc,C3P0 | 
|Serialization| fastjson,jackson,gson | Json.NET
|Transport| HTML5:Websocket/Server Sent Event, Comet: Forever Frame(IE only), Ajax long polling, WebHook|
|discovering and configuring services| Eureka, Consul(https://luyiisme.github.io/2017/04/22/spring-cloud-service-discovery-products/) 
||Eureka server event:
||EurekaInstanceCanceledEvent
||EurekaInstanceRegisteredEvent
||EurekaInstanceRenewedEvent
||EurekaInstanceAvailableEvent
||EurekaInstanceStartedEvent|
|Testing Tool| ab - Apache HTTP server benchmarking tool/ Jmeter
|API Gateway| Zuul/Nginx(with SLB)/Linkerd/Spring Cloud Gateway(https://engineering.opsgenie.com/comparing-api-gateway-performances-nginx-vs-zuul-vs-spring-cloud-gateway-vs-linkerd-b2cc59c65369)
|Configure Center| Spring Config service/Disconf|
|Job| Quartz/Elastic-Job/Spring Cloud Task/Obsidian
|Tools| VirtualBox/Vagrant

| Tech| Comment |
| -- | -- |
|velocity,freemaker,jsp|模板引擎，MVC中渲染页面用的
|Angular/React/Vue| web 框架 
|Spring core|主要IOC和AOP两个核心功能，主要功能是依赖注入（DI）和面向切面编程（eg:事务）
|Spring MVC/Swagger|开发web应用的MVC框架，接受HTTP请求然后处理业务逻辑，封装servlet提高开发效率
|Mybatis|持久层框架，访问数据库的，封装JDBC。提供丰富的功能：动态SQL，SQL和业务逻辑分离等
|redis\memecache\tair|分布式缓存
|kafka,rabbitmq,rocketmq,activemq|消息队列，主要用于削峰,系统解耦合
|shiro,spring security/OAuth2/Token|权限管理
|CAS（Central Authentication Service)|单点登陆
|jetty,tomcat,jboss,undertow等|java web应用容器，按照servlet规范实现
|Spring-boot|现在很火的零配置框架，以后也会很火，结合spring-cloud各种组件实现微服务吧
|slf4j,logback,log4j/ELK等|打印日志的（ ，通俗易懂嘛），异步日志，日志切割,统一日志门面等
|zookeeper|用于服务发现,主备切换,做配置中心等，强调CAP理论中的CP，使用ZAB协议保证一致性（类paxos，其他还有raft）类似的有consul,etcd，常用在RPC,kafka等分布式系统
|tbsession\spring session|分布式session组件,管理用户session，结合分布式缓存使用
|apache,nodejs,nginx:代表：Tengine|七层代理，统一接入层，反向代理，提供限流,分流,负债均衡等功能
|Netty/mina|网络框架，封装各种网络协议，也可自定义，开发高性能网络组件或者应用可钻研，如各种RPC
|dubbo,gRPC....|远程过程调用，在SOA架构中不可或缺的组件,利用Zookeeper,configServer,eureka等做服务发现
|druid,tomcat-jdbc,C3P0等|数据库连接池，维持和数据库的连接，一般和mybatis,heibernate等持久层框架一起使用
|fastjson,jackson,gson等|（反）序列化json文本是使用的
|apache-commons|各种工具,如CLI,dbutils,collections,beanutils,IO等|
| guava | google开源的工具类，包含本地缓存,集合,future等包装之后的工具|
|canal,databus | binlog的增量订阅&消费组件
|tddl,atlas,zebra,mycat,sharding-jdbc|数据库访问中间件，分库分表
|elasticsearch,solr|基于lucene,全文检索，反向索引（倒排索引），对文本检索
|httpclient,feign|http访问客户端，用于访问http请求，获取数据，常用于爬虫
|quartz,elastic-job,TBschedule,Spring cloud task|分布式任务调度
|hystrix|熔断,隔离,降级,限流
|spring cloud config,disconf|配置中心，动态下发配置
|storm,spark,hadoop等|流式计算,离线计算
|hive,hbase,hdfs|存储；文件存储,列存储
|Principle |DDD/CQRS      CAP/BASE
|Concept| 分布式事务/两阶段提交协议，事务协调器，本地消息表，消息引用状态表
|Cache | MongoDB做高性能数据库，Redis做缓存，HBase做大数据分析
|RPC 框架| 协议&序列化
| |client 端包含：序列化,反序列化,连接池管理,负载均衡,故障转移,队列管理，超时管理,异步管理等等职责。
| |server 端包含：服务端组件,服务端收发包队列, io 线程,工作线程,序列化反序列化,上下文管理器,超时管理,异步回调等等职责。



# Why microservice
### DDD/CQRS, modules for easy matainance
### independent modules with different language based
### different database kind for different scenarios.
### Scalibitiy on cloud/docker
### Devops/ELK
