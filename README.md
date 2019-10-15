### Spring Cloud 例子合辑
例子 | 实现功能 | 代码仓库
--- | --- | ---
Spring Cloud 集成 Consul（服务注册与发现） |  | https://github.com/cag2050/spring_cloud_consul_demos
服务提供者(可以通过 java -jar 启动多个实例，用于负载均衡) | 1.使用 Spring Cloud Consul Config 来做服务配置中心 | https://github.com/cag2050/spring_cloud_consul_producer_demo.git
使用 LoadBalancerClient 消费服务 |  | https://github.com/cag2050/spring_cloud_consul_consumer1_LoadBalancerClient_demo
使用 Ribbon 消费服务 | 1.使用 Ribbon 消费服务；2.Ribbon 中引入 Hystrix； | https://github.com/cag2050/spring_cloud_consul_consumer2_ribbon_demo
使用 Feign 消费服务 | 1.使用 Feign 消费服务；2.Feign 使用 Hystrix； | https://github.com/cag2050/spring_cloud_consul_consumer3_feign_demo
Gateway 注册到服务中心 Consul，代理服务中心的所有服务 | | https://github.com/cag2050/spring_cloud_gateway_consul_demo
Sleuth 微服务链路追踪 | Sleuth 结合 Zipkin，实现微服务链路追踪；Elasticsearch 保存链路数据；Kibana 展示链路数据 | https://github.com/cag2050/spring_cloud_consul_sleuth_zipkin_demo
Spring Cloud Stream 使用 RabbitMQ |  | https://github.com/cag2050/spring_cloud_stream_rabbitmq_demo

### 总体步骤一：创建 Consul 容器
1.镜像官方网址：https://hub.docker.com/_/consul
2.pull 镜像：
```
docker pull consul:1.6.0
```
3.创建容器（默认http管理端口：8500）
```
docker run -p 8500:8500 consul:1.6.0
```
4.访问管理网址
```
http://localhost:8500/
```

### 总体步骤二：依次创建项目
1.依次创建项目：服务提供者、各个消费端

### 参考
资料 | 网址
--- | ---
springcloud(十三)：注册中心 Consul 使用详解 | http://ityouknow.com/springcloud/2018/07/20/spring-cloud-consul.html
四：服务消费（LoadBalancerClient、Ribbon、Feign）| https://www.jianshu.com/p/562045489d9d