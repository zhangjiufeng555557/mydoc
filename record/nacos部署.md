# docker 部署nacos 服务
 > 本次部署是使用之前已部署好的mysql 数据库

> #### 拉取docker nacos 服务
>> ```docker docker pull nacos/nacos-server:2.0.3 ```
> #### 配置创建挂载文件夹 E:\docker-volumes\nacos\conf、data、logs
> #### 在E:\docker-volumes\nacos\conf文件夹下创建配置文件application.properties
```properties
#*************** Spring Boot Related Configurations ***************#
### Default web context path:
server.servlet.contextPath=/nacos
### Default web server port:
server.port=8848
 
#*************** Config Module Related Configurations ***************#
### If use MySQL as datasource:
spring.datasource.platform=mysql
 
### Count of DB:
db.num=1
 
### Connect URL of DB:
db.url=jdbc:mysql://127.0.0.1:3306/nacos?characterEncoding=utf8&connectTimeout=1000&socketTimeout=3000&autoReconnect=true&useUnicode=true&useSSL=false&serverTimezone=UTC
db.user=root
db.password=123456
 
### Connection pool configuration: hikariCP
db.pool.config.connectionTimeout=30000
db.pool.config.validationTimeout=10000
db.pool.config.maximumPoolSize=20
db.pool.config.minimumIdle=2
 
### will be removed and replaced by `nacos.naming.clean` properties
nacos.naming.empty-service.auto-clean=true
nacos.naming.empty-service.clean.initial-delay-ms=50000
nacos.naming.empty-service.clean.period-time-ms=30000
 
### Metrics for elastic search
management.metrics.export.elastic.enabled=false
#management.metrics.export.elastic.host=http://localhost:9200
 
### Metrics for influx
management.metrics.export.influx.enabled=false
#management.metrics.export.influx.db=springboot
#management.metrics.export.influx.uri=http://localhost:8086
#management.metrics.export.influx.auto-create-db=true
#management.metrics.export.influx.consistency=one
#management.metrics.export.influx.compressed=true
 
#*************** Access Log Related Configurations ***************#
### If turn on the access log:
server.tomcat.accesslog.enabled=true
 
### The access log pattern:
server.tomcat.accesslog.pattern=%h %l %u %t "%r" %s %b %D %{User-Agent}i %{Request-Source}i
 
### The directory of access log:
server.tomcat.basedir=
 
#*************** Access Control Related Configurations ***************#
### If enable spring security, this option is deprecated in 1.2.0:
#spring.security.enabled=false
 
### The ignore urls of auth, is deprecated in 1.2.0:
nacos.security.ignore.urls=/,/error,/**/*.css,/**/*.js,/**/*.html,/**/*.map,/**/*.svg,/**/*.png,/**/*.ico,/console-ui/public/**,/v1/auth/**,/v1/console/health/**,/actuator/**,/v1/console/server/**
 
### The auth system to use, currently only 'nacos' and 'ldap' is supported:
nacos.core.auth.system.type=nacos
 
### If turn on auth system:
nacos.core.auth.enabled=false
 
### worked when nacos.core.auth.system.type=ldapï¼{0} is Placeholder,replace login username
# nacos.core.auth.ldap.url=ldap://localhost:389
# nacos.core.auth.ldap.userdn=cn={0},ou=user,dc=company,dc=com
 
### The token expiration in seconds:
nacos.core.auth.default.token.expire.seconds=18000
 
### The default token:
nacos.core.auth.default.token.secret.key=SecretKey012345678901234567890123456789012345678901234567890123456789
 
### Turn on/off caching of auth information. By turning on this switch, the update of auth information would have a 15 seconds delay.
nacos.core.auth.caching.enabled=true
 
### Since 1.4.1, Turn on/off white auth for user-agent: nacos-server, only for upgrade from old version.
nacos.core.auth.enable.userAgentAuthWhite=false
 
### Since 1.4.1, worked when nacos.core.auth.enabled=true and nacos.core.auth.enable.userAgentAuthWhite=false.
### The two properties is the white list for auth and used by identity the request from other server.
nacos.core.auth.server.identity.key=serverIdentity
nacos.core.auth.server.identity.value=security
 
#*************** Istio Related Configurations ***************#
### If turn on the MCP server:
nacos.istio.mcp.server.enabled=false
```

>#### 启动服务
```docker 
docker run -d --name nacos --restart=always -p 8848:8848 
 -e MODE=standalone -e PREFER_HOST_MODE=mysql 
 -v E:\docker-volumes\nacos\conf\application.properties:/home/nacos/conf/application.properties 
 -v E:\docker-volumes\nacos\logs:/home/nacos/logs  
 -v E:\docker-volumes\nacos\data:/home/nacos/data  
 nacos/nacos-server:2.0.3
```
>#### 正常来说流程已经完成 但是本次爆出异常 
```console 
2023-10-30 11:43:52 Caused by: com.alibaba.nacos.api.exception.NacosException: Nacos Server did not start because dumpservice bean construction failure :
2023-10-30 11:43:52 No DataSource set
2023-10-30 11:43:52     at com.alibaba.nacos.config.server.service.dump.DumpService.dumpOperate(DumpService.java:236)
2023-10-30 11:43:52     at com.alibaba.nacos.config.server.service.dump.ExternalDumpService.init(ExternalDumpService.java:52)
2023-10-30 11:43:52     at sun.reflect.NativeMethodAccessorImpl.invoke0(Native Method)
2023-10-30 11:43:52     at sun.reflect.NativeMethodAccessorImpl.invoke(NativeMethodAccessorImpl.java:62)
2023-10-30 11:43:52     at sun.reflect.DelegatingMethodAccessorImpl.invoke(DelegatingMethodAccessorImpl.java:43)
2023-10-30 11:43:52     at java.lang.reflect.Method.invoke(Method.java:498)
2023-10-30 11:43:52     at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor$LifecycleElement.invoke(InitDestroyAnnotationBeanPostProcessor.java:363)
2023-10-30 11:43:52     at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor$LifecycleMetadata.invokeInitMethods(InitDestroyAnnotationBeanPostProcessor.java:307)
2023-10-30 11:43:52     at org.springframework.beans.factory.annotation.InitDestroyAnnotationBeanPostProcessor.postProcessBeforeInitialization(InitDestroyAnnotationBeanPostProcessor.java:136)
2023-10-30 11:43:52     ... 53 common frames omitted
```
>+ 问题分析 数据库配置无效、无法正常链接数据库
>+ 原因是 配置中数据是打算直接链接宿主机的mysql 服务 但是当前容器其实是无法通过127.0.0.1访问宿主机 
>#### 解决：链接到docker 服务中的mysql 172.18.0.2:3307
>>+ 之前已经部署过一个docker 容器服务的mysql 开启的端口是3307:3306 绑定的宿主机3307端口
>>+ 但是配置启动之后依然抛出上面的异常信息后排查是<mark>两个容器不在一个网段中</mark>
>>+ 解决方案：
##### 创建一个网关my-bridge
```docker
docker network create --driver bridge my-bridge    
```

#### 将两个服务都添加该网关使两个容器能有同一个内网网段
```docker
docker network connect my-bridge mysql

docker network connect my-bridge nacos
```
#### 后查看配置 
```docker
docker inspect mysql
```
```yaml
        "Networks": {
			"my-bridge": {
				"IPAMConfig": null,
				"Links": null,
				"Aliases": [
					"bf009e16ad42"
				],
				"NetworkID": "40bdb380c418de3f4d4685e58c635ea420b5c27c399534b9d0e703840eb901fd",
				"EndpointID": "e5137de6b1491641b594e163983f24a36afefcb9e88d40bbce123b8227cdac4a",
				"Gateway": "172.18.0.1",
				"IPAddress": "172.18.0.3",
				"IPPrefixLen": 16,
				"IPv6Gateway": "",
				"GlobalIPv6Address": "",
				"GlobalIPv6PrefixLen": 0,
				"MacAddress": "02:42:ac:12:00:03",
				"DriverOpts": null
			}
		}
```
>+ 现在mysql 服务已经有一个网关是my-bridge 并且网段是172.18.0.1 
>+ 查看nacos 服务网段为 172.18.0.2
>+ <mark>更改配置172.18.0.2:3306  3306是服务的端口  3307是绑定在宿主机的端口 这里直接链的mysql 容器所以直接使用3306端口</mark>

> 启动时指定网关
> docker run -d --name nacos --restart=always -p 8848:8848 <mark>--network my-bridge</mark>
> -e MODE=standalone -e PREFER_HOST_MODE=mysql 
> -v E:\docker-volumes\nacos\conf\application.properties:/home/nacos/conf/application.properties 
> -v E:\docker-volumes\nacos\logs:/home/nacos/logs  
> -v E:\docker-volumes\nacos\data:/home/nacos/data  nacos/nacos-server:2.0.3




