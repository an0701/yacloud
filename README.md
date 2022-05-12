# YaCloud

## 如果您觉得有帮助，请点右上角 "Star" 支持一下谢谢

YaCloud是一款基于Spring Cloud Alibaba的微服务架构，旨在为大家提供技术框架的基础能力的封装，减少开发工作。



## 一、系统演示

### 演示地址：

账号 | 密码| 操作权限
---|---|---
      |      |          

## 二、官方文档
### 文档地址：
### 快速安装：

![](https://gitee.com/changan/imgurl/raw/master/20220508103817.png)

## 三、技术交流

技术交流群待创建

![](https://gitee.com/changan/imgurl/raw/master/20220508103817.png)

## 四、系统架构图
架构图

![](https://gitee.com/changan/imgurl/raw/master/20220508103817.png)

## 五、功能特点

- 主体框架：采用最新的`Spring Cloud 2021.0.2`, `Spring Boot 2.6.7`, `Spring Cloud Alibaba 2021.0.1.0`版本进行系统设计；

- 统一注册：支持`Nacos`作为注册中心，实现多配置、分群组、分命名空间、多业务模块的注册和发现功能；

- 统一认证：统一`Oauth2`认证协议，采用jwt的方式，实现统一认证，并支持自定义grant_type实现手机号码登录，第三方登录集成JustAuth实现微信、支付宝等多种登录模式；

- 业务监控：利用`Spring Boot Admin`来监控各个独立Service的运行状态。

- 内部调用：集成了`Feign`和`Dubbo`两种模式支持内部调用，并且可以实现无缝切换，适合新老程序员，快速熟悉项目；

- 业务熔断：采用`Sentinel`实现业务熔断处理，避免服务之间出现雪崩;

- 身份注入：通过注解的方式，实现用户登录信息的快速注入；

- 在线文档：通过接入`Knife4j`，实现在线API文档的查看与调试;

- 代码生成：基于`Mybatis-plus-generator`自动生成代码，提升开发效率，生成模式不断优化中，暂不支持前端代码生成；

- 消息中心：集成消息中间件`RocketMQ`和`Kafka`，对业务进行异步处理;

- 业务分离：采用前后端分离的框架设计，前端采用`vue-element-admin`,商业版采用`antd-pro-vue`

- 链路追踪：自定义traceId的方式，实现简单的链路追踪功能

- 多租户功能：集成`Mybatis Plus`,实现SAAS多租户功能

## 六、文件结构

```lua
matecloud -- 父项目,各模块分离，方便集成和微服务
│  ├─mate-core -- 核心通用模块，主模块
│  │  ├─mate-starter-common -- 封装通用模块
│  │  ├─mate-starter-cloud -- 封装微服务模块
│  │  ├─mate-starter-auth -- 封装token验证模块
│  │  ├─mate-starter-security -- 封装OAuth2基础模块
│  │  ├─mate-starter-web -- 封装WEB服务基础模块
│  │  ├─mate-starter-database -- 封装Mybatis及数据库基础模块
│  │  ├─mate-starter-dependencies -- 封装所有依赖模块，可作为父项目独立引用
│  │  ├─mate-starter-dubbo -- 封装dubbo基础模块
│  │  ├─mate-starter-feign -- 封装feign基础模块
│  │  ├─mate-starter-jetcache -- 封装JetCache阿里缓存基础模块
│  │  ├─mate-starter-rocketmq -- 封装RocketMQ基础模块
│  │  ├─mate-starter-gray -- 封装灰度发布基础模块
│  │  ├─mate-starter-elasticsearch -- 封装ElasticSearch模块
│  │  ├─mate-starter-oss -- 封装oss存储基础模块,支持阿里云、七牛云、minio等
│  │  ├─mate-starter-log -- 封装日志基础模块
│  │  ├─mate-starter-sharding -- 封装多数据库基础模块
│  │  ├─mate-starter-sms -- 封装短信基础模块
│  │  ├─mate-starter-mail -- 封装邮件模块
│  │  ├─mate-starter-kafka -- 封装kafka基础模块
│  │  ├─mate-starter-rule -- 封装黑名单基础模块
│  │  ├─mate-starter-idempotent -- 封装幂等基础模块
│  │  ├─mate-starter-lock -- 封装分布式锁基础模块
│  │  ├─mate-starter-encrypt -- 封装报文加密模块，支持AES和RSA
│  │  ├─mate-starter-mongodb -- 封装mongodb数据库模块
│  │  ├─mate-starter-strategy -- 封装策略模块
│  │  ├─mate-starter-job -- 封装定时任务基础模块
│  │  ├─mate-starter-validator -- 封装统一检验基础模块
│  │─mate-gateway -- 统一网关模块 [10001]
│  │─mate-uaa -- 统一认证中心模块 [20001]
│  │─mate-platform -- 平台模块项目，目前包含系统子模块
│  │  ├─mate-system-api -- 系统模块的通用模块，供其他模块引用
│  │  ├─mate-system -- 系统模块核心功能 [20002]
│  │  ├─mate-component-api -- 组件模块核心功能，供其他模块引用
│  │  ├─mate-component -- 组件模块核心功能 [20003]
│  │─mate-support -- 支持中心项目，目前包括代码生成、admin模块
│  │  ├─mate-code -- 封装代码生成逻辑 [30002]
│  │  ├─mate-admin -- 封装spring-boot-admin逻辑 [30001]
│  │  ├─mate-job -- xxl-jog定时任务模块
│  │  ├─mate-job-admin -- 定时任务管理平台模块
│  │─mate-mq -- 消息中心项目，支持kafka、RocketMQ等多种消息中间件
│  │  ├─mate-log-producer -- 日志消息生产者，集成kafka [40001]
│  │  ├─mate-message-consumer -- 消息服务消费者 [40002]
│  │  ├─mate-message-producer -- 消息服务生产者 [40003] 
```

## 七、技术选型

### 后端技术

| 技术                   | 说明                 | 官网                                                 |
| ---------------------- | -------------------- | ---------------------------------------------------- |
| Spring Cloud           | 微服务框架           | https://spring.io/projects/spring-cloud              |
| Spring Cloud Alibaba   | 微服务框架           | https://github.com/alibaba/spring-cloud-alibaba      |
| Spring Boot            | 容器+MVC框架         | https://spring.io/projects/spring-boot               |
| Spring Security Oauth2 | 认证和授权框架       | https://spring.io/projects/spring-security-oauth     |
| MyBatis                | ORM框架              | http://www.mybatis.org/mybatis-3/zh/index.html       |
| MyBatisGenerator       | 数据层代码生成       | http://www.mybatis.org/generator/index.html          |
| PageHelper             | MyBatis物理分页插件  | http://git.oschina.net/free/Mybatis_PageHelper       |
| Knife4j                | 文档生产工具         | https://github.com/xiaoymin/swagger-bootstrap-ui     |
| Elasticsearch          | 搜索引擎             | https://github.com/elastic/elasticsearch             |
| RabbitMq               | 消息队列             | https://www.rabbitmq.com/                            |
| Redis                  | 分布式缓存           | https://redis.io/                                    |
| MongoDb                | NoSql数据库          | https://www.mongodb.com/                             |
| Docker                 | 应用容器引擎         | https://www.docker.com/                              |
| Druid                  | 数据库连接池         | https://github.com/alibaba/druid                     |
| OSS                    | 对象存储             | https://github.com/aliyun/aliyun-oss-java-sdk        |
| MinIO                  | 对象存储             | https://github.com/minio/minio                       |
| JWT                    | JWT登录支持          | https://github.com/jwtk/jjwt                         |
| LogStash               | 日志收集             | https://github.com/logstash/logstash-logback-encoder |
| Lombok                 | 简化对象封装工具     | https://github.com/rzwitserloot/lombok               |
| Seata                  | 全局事务管理框架     | https://github.com/seata/seata                       |
| Portainer              | 可视化Docker容器管理 | https://github.com/portainer/portainer               |
| Jenkins                | 自动化部署工具       | https://github.com/jenkinsci/jenkins                 |
| Kubernetes             | 应用容器管理平台     | https://kubernetes.io/                               |

### 前端技术

| 技术       | 说明                  | 官网                           |
| ---------- | --------------------- | ------------------------------ |
| Vue        | 前端框架              | https://vuejs.org/             |
| Vue-router | 路由框架              | https://router.vuejs.org/      |
| Vuex       | 全局状态管理框架      | https://vuex.vuejs.org/        |
| Element    | 前端UI框架            | https://element.eleme.io/      |
| Axios      | 前端HTTP框架          | https://github.com/axios/axios |
| v-charts   | 基于Echarts的图表框架 | https://v-charts.js.org/       |


## 八、环境搭建

### 开发环境

| 工具          | 版本号 | 下载                                                         |
| ------------- | ------ | ------------------------------------------------------------ |
| JDK           | 1.8    | https://www.oracle.com/technetwork/java/javase/downloads/jdk8-downloads-2133151.html |
| Mysql         | 5.7    | https://www.mysql.com/                                       |
| Redis         | 5.0    | https://redis.io/download                                    |
| Elasticsearch | 7.6.2  | https://www.elastic.co/cn/downloads/elasticsearch            |
| Kibana        | 7.6.2  | https://www.elastic.co/cn/downloads/kibana                   |
| Logstash      | 7.6.2  | https://www.elastic.co/cn/downloads/logstash                 |
| MongoDb       | 4.2.5  | https://www.mongodb.com/download-center                      |
| RabbitMq      | 3.7.14 | http://www.rabbitmq.com/download.html                        |
| nginx         | 1.10   | http://nginx.org/en/download.html                            |



## 九、运行效果演示

<table>
    <tr>
        <td><img src="https://gitee.com/changan/imgurl/raw/master/20220508103817.png"/></td>
        <td><img src="https://gitee.com/changan/imgurl/raw/master/20220508103817.png"/></td>
    </tr>
    <tr>
        <td><img src="https://gitee.com/changan/imgurl/raw/master/20220508103817.png"/></td>
        <td><img src="https://gitee.com/changan/imgurl/raw/master/20220508103817.png"/></td>
    </tr>
</table>



## 十、贡献者名单
欢迎新战友，以下为项目贡献的同志（排名不分先后）：

@an0701

