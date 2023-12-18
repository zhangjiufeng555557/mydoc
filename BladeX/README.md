![](images/cover.jpg)



# 简介

*   BladeX 是一个基于 Spring Boot 2.7 & Spring Cloud 2021 & Mybatis 等核心技术，用于快速构建中大型系统的基础框架。
*   已稳定生产近一年，经历了从Camden->2021的技术架构，也经历了从FatJar->Docker->K8S+Jenkins的部署架构。
*   采用前后端分离的模式，前端开发两个框架：Sword(基于React、Ant Design)、Saber(基于Vue、ElementUI)。
*   后端采用SpringCloud系列，对其基础组件做了高度的封装，单独出一个后端核心框架：BladeX-Tool。
*   BladeX-Tool已推送至Maven私有库，直接引入减少工程的模块与依赖，可更注重于业务开发。
*   集成Sentinel从流量控制、熔断降级、系统负载保护等多个维度保护服务的稳定性。
*   注册中心、配置中心选型Nacos，为工程瘦身的同时加强了各模块之间的联动。
*   封装集成了基于注解+Web可视化的数据权限，灵活配置，无需重启直接生效。
*   定制了基于Nacos的轻量级、高拓展性的动态网关，完美支持多团队开发。
*   精心设计集成了minio，完美支持多租户模式下的oss对象存储需求。
*   Traefik反向代理，监听后台变化自动化应用新的配置文件。
*   集成Oauth2协议，完美支持多终端的接入与认证授权。
*   项目分包明确，规范微服务的开发模式。



# 商业授权说明

## 版权声明
* BladeX是一个商业化软件，系列产品知识产权归**上海布雷德科技有限公司**独立所有
* 您一旦开始复制、下载、安装或者使用本产品，即被视为完全理解并接受本协议的各项条款
* 更多详情请看：[商业协议](第0章 序/0.7商用协议.md)
* BladeX官网：https://bladex.vip/

## 答疑流程
>1. 遇到问题或Bug
>2. 业务型问题打断点调试尝试找出问题所在
>3. 系统型问题通过百度、谷歌、社区查找解决方案
>4. 未解决问题则进入技术社区进行发帖提问：[https://sns.bladex.vip/](https://sns.bladex.vip/)
>5. 将帖子地址发至商业群，特别简单三言两语就能描述清楚的也可在答疑时间内发至商业群提问
>6. 发帖的时候一定要描述清楚，详细描述遇到问题的**重现步骤**、**报错详细信息**、**相关代码与逻辑**、**使用软件版本**以及**操作系统版本**，否则随意发帖提问将会提高我们的答疑难度。

## 答疑时间
* 工作日：9:00 ~ 17:00 提供答疑，周末、节假日休息，暂停答疑
* 请勿**私聊提问**，以免被其他用户的消息覆盖从而无法获得答疑
* 答疑时间外遇到问题可以将问题发帖至[技术社区](https://sns.bladex.vip/)，我们后续会逐个回复

## 授权范围
* 专业版：只可用于**个人学习**及**个人私活**项目，不可用于公司或团队，不可泄露给任何第三方
* 企业版：可用于**企业名下**的任何项目，企业版员工在**未购买**专业版授权前，只授权开发**所在授权企业名下**的项目，**不得将BladeX用于个人私活**
* 共同遵守：若甲方需要您提供项目源码，则需代为甲方购买BladeX企业授权，甲方购买后续的所有项目都无需再次购买授权

## 商用权益
* ✔️ 遵守[商业协议](第0章 序/0.7商用协议.md)的前提下，将BladeX系列产品用于授权范围内的商用项目，并上线运营
* ✔️ 遵守[商业协议](第0章 序/0.7商用协议.md)的前提下，不限制项目数，不限制服务器数
* ✔️ 遵守[商业协议](第0章 序/0.7商用协议.md)的前提下，将自行编写的业务代码申请软件著作权

## 何为侵权
* ❌ 不遵守商业协议，私自销售商业源码
* ❌ 以任何理由将BladeX源码用于申请软件著作权
* ❌ 将商业源码以任何途径任何理由泄露给未授权的单位或个人
* ❌ 开发完毕项目，没有为甲方购买企业授权，向甲方提供了BladeX代码
* ❌ 基于BladeX拓展研发与BladeX有竞争关系的衍生框架，并将其开源或销售

## 侵权后果
* 情节较轻：第一次发现警告处理
* 情节较重：封禁账号，踢出商业群，并保留追究法律责任的权利
* 情节严重：与本地律师事务所合作，以公司名义起诉侵犯计算机软件著作权

## 举报有奖
* 向官方提供有用线索并成功捣毁盗版个人或窝点，将会看成果给予 500～10000 不等的现金奖励
* 官方唯一指定QQ：1272154962



# 更新日志

## 3.2.0.RELEASE  [2023-09-08]

* [升级]SpringCloud 至 2021.0.8
* [升级]SpringBoot 至 2.7.15
* [升级]Spring 至 5.3.29
* [升级]Druid 至 1.2.19
* [升级]Mybatis-Plus 至 3.5.3.2
* [升级]Avue3 至 3.2.19
* [升级]Avue-Plugin 至 1.0.3
* [新增]SkyWalking集成
* [新增]Token加密传输与校验
* [新增]JwtCrypto工具
* [新增]LiteFlow规则引擎集成
* [新增]多租户对象存储改造为规则引擎实现
* [新增]多租户短信配置改造为规则引擎实现
* [新增]新租户创建流程改造为规则引擎实现
* [优化]minio增加URL转换功能，支持使用内网地址上传并返回外网地址数据
* [优化]多租户动态数据源逻辑
* [修复]saber3编辑器文件上传配置
* [修复]saber3同路由tab切换不刷新数据的问题
* [修复]saber3代码生产模版错误语法
* [提醒]minio由于转变开源协议为AGPLv3,最新开源版已不适用与商业化项目
* [提醒]minio开源版若需要请下载apache2.0协议的最后一个版本
* [提醒]minio开源版可用版本:minio-RELEASE.2021-04-22T15-44-28Z



## 3.1.1.RELEASE [2023-05-15]
- [升级]SpringBoot 至 2.7.11
- [升级]Druid 至 1.2.18
- [新增]新版nexus仓库依赖
- [新增]docker构建工具更换为fabric
- [新增]支持国产崖山数据库(YashanDB)
- [新增]控制台日志增加放行url的特性
- [新增]单人登录模式新增全平台唯一与单客户端唯一两种选择
- [新增]signKey生成器
- [新增]多租户对象存储新增 华为云obs 与 amazon s3
- [优化]适配腾讯云cos最新API
- [优化]适配最新版minio接口，手动关闭流
- [优化]代码生成增加查询字段适配
- [优化]saber3添加prod环境的启动与打包命令
- [优化]取消Dept模块默认的全局管理员接口权限
- [优化]SqlKeyword类的防sql注入功能
- [优化]数据模型字段comment改名为jdbc_comment避免数据库关键词
- [优化]element风格代码生成增加按钮权限
- [优化]vue3版代码生成适配新的时间格式
- [优化]达梦数据库文件修改为脚本文件避免编码不同导入失败
- [修复]报表管理外链打开问题



### 3.1.0.RELEASE[2023-03-31]

- [升级]SpringCloud 至 2021.0.6
- [升级]SpringBoot 至 2.7.10
- [升级]SpringBootAdmin 至 2.7.10
- [升级]AlibabaCloud 至 2021.0.5.0
- [升级]Mybatis-Plus 至 3.5.3.1
- [升级]Mybatis-Plus-Generator 至 3.5.3.1
- [升级]Nacos 至 2.1.2
- [升级]Seata 至 1.6.1
- [升级]Knife4j 至 4.1.0
- [升级]Avue2 至 2.10.10
- [升级]Avue3 至 3.2.13
- [新增]基于Vue3与Element-Plus版本的Saber正式发布
- [新增]新增Sharding-Jdbc与动态数据源联合demo
- [新增]axios支持baseUrl自动追加
- [新增]字典管理新增全数据接口提供前端缓存支持
- [新增]使用 flatten maven 插件优化版本处理
- [新增]BizService供用户自行修改拓展并引入新的业务模块
- [新增]Auto 支持 spring boot 2.7.x spi
- [新增]Metrics 增加 undertow 指标
- [新增]Redis 添加 stream,轻量级 mq，支持广播和集群模式
- [新增]Redis 调整限流脚本,更好的支持云服务器
- [新增]S3Template支持 aws s3 且可同时支持minio作为分布式存储
- [新增]可配置七牛云region的方式 增加七牛云私有文件下载方式
- [新增]OssTemplate实现类获取流的方式去下载文件
- [新增]代码生成saber3以及element-plus模版
- [优化]代码生成数据模型新增后增加提示框是否需要配置详情
- [优化]代码生成查询类型适配
- [优化]代码生成优化基础业务的判断逻辑
- [优化]代码生成增加excel导出功能
- [优化]代码生成加快物理表信息读取速度
- [优化]代码生成参数类型适配pg
- [优化]代码生成数据模型新增逻辑
- [优化]代码生成数据模型增加表前缀提醒
- [优化]代码生成优化表前缀判断
- [优化]代码生成数据模型删除增加关联表
- [优化]登录成功后清除验证码缓存
- [优化]代码生成通用字段默认隐藏
- [优化]关闭nacos默认日志解决与logback冲突的问题
- [优化]取消token默认签名，强制要求配置自定义签名
- [优化]资源管理默认参数判断逻辑
- [优化]Oauth2 token发放增加空判断
- [优化]BladeReids getIncr与getDecr专用方法
- [修复]BladeRedis rPush 方法
- [修复]Xss转义符
- [修复]行政区划市级新增报错问题
- [修复]Jackson注册模块失效的问题
- [修复]流程部署问题
- [修复]字典管理新增缓存上级数据不匹配的问题
- [修复]用户模块先查看再提交会失败的问题
- [迁移]Xxl-Job迁移至Biz工程
- [迁移]user服务合并至system服务，保留blade-user-api



### 3.0.1.RELEASE[2022-08-15]

* [新增]数据模型在线配置
* [新增]代码生成表单组件在线配置
* [新增]Saber风格的单表生成模版
* [新增]Saber风格的主子表生成模版
* [新增]Saber风格的树表生成模版
* [新增]ElementUI风格的单表生成模版
* [新增]ElementUI风格的主子表生成模版
* [新增]ElementUI风格的树表生成模版

## 3.0.0.RELEASE[2022-07-15]

* [升级]SpringCloud 至 2021.0.3
* [升级]SpringBoot 至 2.7.1
* [升级]SpringBootAdmin 至 2.7.1
* [升级]AlibabaCloud 至 2021.0.1.0
* [升级]Mybatis-Plus 至 3.5.2
* [升级]Mybatis-Plus-Generator 至 3.5.3
* [升级]Nacos 至 2.1.0
* [升级]Seata 至 1.5.2
* [升级]Log4J 至 2.18.0
* [升级]JackSon 至 2.13.3
* [升级]FastJson 至 1.2.83
* [升级]Avue 至 2.9.12
* [新增]基于Oauth2的单点登录
* [新增]灰度服务发布与调用
* [新增]代码生成增加element和feign模版
* [优化]自动装配模块采用新版[@AutoConfiguration](https://git.bladex.vip/AutoConfiguration)注解
* [优化]TencentCosTemplate避免oom的情况
* [优化]TreeNode类
* [优化]Gateway鉴权逻辑
* [修复]BladeRedis incr方法失效的问题
* [修复]租户产品包更新后缓存未刷新的问题
* [修复]绑定租户产品包后普通管理员权限配置丢失按钮选项的问题
* [修复]流程设计器监听无法删除的问题
* [修复]用户excel导出条件为空的判断逻辑
* [删除]Hystrix接入以Sentinel取代
* [删除]Ribbon接入以LoadBalancer取代
* [删除]Zipkin接入
* [删除]Turbine接入
* [替代]后续版本将对接SkyWalking取代Zipkin与Turbine



## 2.9.1.RELEASE[2022-03-28]

- [升级]Mybatis-Plus 至 3.5.1

- [升级]Mybatis-Plus-Generator 至 3.5.2

- [升级]Nacos 至 2.0.4

- [升级]Log4j2 至 2.17.2

- [升级]FastJson 至 1.2.80

- [升级]Sentinel 至 1.8.3

- [升级]EasyExcel 至 2.2.11

- [升级]JuatAuth 至 1.16.5

- [升级]OkHttp 至 4.9.3

- [升级]AliyunOss 至 3.14.0

- [升级]Minio 至 8.3.7

- [升级]Qiniu 至 7.9.4

- [升级]TencentCOS 至 5.6.69

- [升级]HuaweiOss 至 3.21.12

- [升级]Avue 至 2.9.4

- [升级]ElementUI 至 2.15.6

- [新增]达梦数据库支持

- [新增]NutFlow流程设计器集成

- [新增]Sword升级至AntdV4版本

- [优化]租户全局数据源拦截器逻辑

- [优化]单人在线模式RefreshToken的处理逻辑

- [优化]单元测试支持读取服务名不同环境的配置

- [优化]租户产品包支持配置清空

- [优化]配置解决oracle更新null值报错的问题

- [优化]适配oss与sms操作栏不换行

- [优化]提升excel导出功能的用户体验

- [优化]主页部门切换逻辑

- [修复]用户解封增加空数据判断逻辑

- [修复]流程用户查询增加租户ID筛选

- [修复]Oauth2授权码模式失效

- [修复]登录锁定逻辑

- [修复]通知公告日期段查询报错

  

## 2.9.0.RELEASE[2021-12-19]

* [升级]SpringCloud 至 Hoxton.SR12
* [升级]AlibabaCloud 至 2.2.7.RELEASE
* [升级]Nacos 至 2.0.3
* [升级]Log4j2 至 2.17.0
* [升级]Druid 至 1.2.8
* [升级]FastJson 至 1.2.78
* [升级]Lombok 至 1.18.22
* [升级]Avue 至 2.8.25
* [升级]阿里云仓库为最新地址
* [新增]租户菜单产品包功能
* [新增]部门角色在线切换功能
* [新增]登录错误次数支持从参数管理读取
* [新增]管理端手动解锁用户功能
* [新增]actuator接口增加内网放行外网认证功能
* [新增]pg数据库int类型条件查询处理示例
* [新增]Lemon平台代码生成模板
* [优化]角色删除增加子节点判断
* [优化]流程条件查询增加租户过滤
* [优化]流程列表增加名称查询
* [优化]登录成功时清除错误次数
* [优化]适配cloud最新版异常处理
* [优化]数据权限新增成功后清空表单数据
* [修复]修复用户导入部门数据为null时保存报错的问题
* [修复]修复刷新token导致多部门id被覆盖的问题
* [修复]修复登录界面多部门选择弹框出现后直接刷新就能进入主页的问题
* [修复]修复通知公告分页未带入查询条件的问题



## 2.8.2.RELEASE [2021-08-16]
- [升级]SpringBoot 至 2.3.12
- [升级]SpringBootAdmin 至 2.3.1
- [升级]Knife4j 至 2.0.9
- [升级]Nacos 至 2.0.2
- [升级]Seata 至 1.4.2
- [升级]MybatisPlus 至 3.4.3.1
- [升级]DynamicDatasource 至 3.3.6
- [升级]Druid 至 1.2.6
- [升级]Avue 至 2.8.18
- [新增]用户登录错误次数锁定功能
- [新增]多部门多角色用户在登录时增加下拉选项
- [新增]用户多条件查询接口
- [新增]Ribbon组件权重读取逻辑
- [新增]ExcelUtil新增WriteHandler参数
- [新增]CacheUtil增加指定tenantId清空方法
- [优化]手机短信校验逻辑，增加手机号强制判断
- [优化]短信调试功能增加资源编号读取
- [优化]多租户切面逻辑
- [优化]多租户缓存清空逻辑
- [优化]ISqlInjector支持自定义覆盖
- [优化]优化日志对于租户id的判断
- [优化]Menu类重写hashCode方法
- [优化]MySql脚本将long类型字段改为bigint(20)
- [修复]用户中心字段绑定相反的问题
- [修复]关闭验证码模式后首页仍调用验证码接口的问题



## 2.8.1.RELEASE [2021-05-19]

* [升级]SpringCloud 至 Hoxton.SR11
* [升级]Avue 至 2.8.12
* [升级]Lombok 至 1.18.18
* [升级]Nacos 至 2.0.1
* [升级]JustAuth 至 1.16.1
* [新增]JustAuth支持基于redis的state缓存
* [新增]服务内部调用文件上传的工具类
* [新增]插件市场目录说明
* [新增]全新布局的字典管理模块
* [优化]Dockerfile初始镜像改为固化的openjdk8-openj9含字体版本
* [优化]SmsResponse返回字段message为msg
* [优化]Feign熔断加载逻辑
* [优化]Sql打印插件增加java8时间处理
* [优化]多数据源环境下生效Sql打印插件的配置
* [优化]校验短信验证码时与手机号关联验证
* [优化]Request包装逻辑支持配置跳过
* [优化]Mybatis-plus的SQLServerDialect逻辑
* [优化]ObjectMapper支持可配
* [优化]增加跨域请求头以防独立swagger服务出现跨域
* [优化]数据权限与接口权限的缓存改为全局
* [优化]Xss过滤逻辑
* [优化]角色配置逻辑
* [优化]菜单配置逻辑
* [修复]ImageUtil宽高反转的bug
* [修复]树组件未全选导致父节点没有入库从而引发顶部菜单生成的bug
* [修复]字典通用接口未返回id与parentId产生的bug
* [脚本]启动脚本增加jvm配置
* [脚本]修复report脚本部署逻辑
* [移除]过时的BladeRedisCache，请用BladeRedis取代

## 2.8.0.RELEASE [2021-02-28]

* [升级]SpringCloud 至 Hoxton.SR10
* [升级]AlibabaCloud 至 2.2.5.RELEASE
* [升级]FastJson 至 1.2.75
* [升级]Druid 至 1.2.5
* [升级]EasyExcel 至 1.2.7
* [升级]JustAuth 至 1.15.9
* [升级]Avue 至 2.8.1
* [升级]ElementUI 至 2.15.1
* [升级]Oss与Sms升级依赖并适配最新版
* [新增]基于宝塔系统的部署方案
* [新增]Prometheus全方位监控方案
* [新增]blade-admin服务支持prometheus对nacos的服务发现
* [新增]BladeX对接Prometheus部署脚本
* [新增]Saber远程部署推送脚本
* [新增]基于Sentinel的服务熔断方案
* [新增]Mybatis-Plus添加OptimizeJoin配置参数
* [优化]将oss-starter系列合并为一
* [优化]将sms-starter系列合并为一
* [优化]增强优化Url通配符匹配逻辑
* [优化]数据权限缓存逻辑
* [优化]blade-auto封装
* [优化]SqlLogInterceptor配置

## 2.7.2.RELEASE [2021-01-30]
- [升级]SpringBoot 至 2.2.13.RELEASE
- [升级]AlibabaCloud 至 2.2.5
- [升级]Mybatis-Plus 至 3.4.2
- [升级]Dynamic-Datasource 至3.3.1
- [升级]Avue 至 2.7.8
- [升级]适配 Knife4j 2.0.8
- [重构]Swagger聚合网关迁移至全新的blade-swagger服务
- [重构]Sql日志打印采用druid底层实现展示完整带参SQL
- [新增]LocalFile的domain字段
- [新增]Sign模式鉴权timestamp在10秒内的合法时间段判断
- [新增]开启租户插件后使用@TenantIgnore注解精准关闭租户过滤逻辑
- [新增]Swagger公共信息配置
- [新增]Saber矢量图标离线化
- [新增]菜单管理isOpen字段控制左侧菜单是否可以使用新tab打开外链
- [新增]Mybatis-Plus的Page合并工具类  
- [优化]阿里云短信返回成功判断逻辑
- [优化]Token过期时间处理
- [优化]Redis加载逻辑
- [优化]用户登录逻辑
- [优化]多租户角色创建逻辑
- [优化]Dockerfile加速字体构建
- [优化]Nacos Shared Config配置API改为最新版
- [优化]Saber授权类型字段改为checkbox
- [修复]RequestLog遇到MultipartFile.[]类型序列化报错的问题
- [修复]顶级字典更新后未同步更新下属字典的编号
- [修复]Saber退出后未刷新浏览器顶部title路由的问题
- [修复]菜单机构模块关闭编辑界面再打开新增界面数据没有清空的问题

## 2.7.1.RELEASE [2020-12-24]
- [升级]SpringBoot 至 2.2.12.RELEASE
- [升级]SpringCloud 至 Hoxton.SR9
- [升级]Knife4j 至 2.0.8
- [升级]Druid 至 1.2.4
- [升级]Seata 至 1.4.1
- [升级]Jackson 至 2.11.4
- [升级]Mybatis-Plus 至 3.4.1
- [升级]Dynamic-Datasource 至3.2.1
- [升级]Avue 至 2.7.4
- [新增]Secure模块动态签名认证特性
- [新增]Redis序列化方式的配置
- [新增]用户导入导出的用户平台字段
- [修改]日志路径默认优先级，支持配置覆盖
- [修改]Report模块包路径，新增Core目录
- [重构]blade-admin，钉钉监控通知实现
- [优化]blade-admin，增加账号密码登录
- [优化]RefreshToken刷新逻辑
- [优化]租户新增逻辑，业务字典支持无限层级复制
- [优化]Ribbon组件，支持Feign调用配置
- [修复]流程名搜索失效的问题
- [修复]附件管理租户隔离问题
- [修复]数据权限分配模块的sqlserver兼容性
- [修复]系统字典缓存刷新逻辑
- [修复]Swagger文档出现Locale参数的问题
- [删除]spring-cloud-stream依赖，按需引入

## 2.7.0.RELEASE [2020-10-31]
- [升级]SpringBoot 至 2.2.11.RELEASE
- [升级]SpringCloud 至 Hoxton.SR8
- [升级]AlibabaCloud 至 2.2.3.RELEASE
- [升级]SpringBootAdmin 至 2.2.4
- [升级]Knife4j 至 2.0.6
- [升级]Swagger 至 2.10.5
- [升级]SwaggerModel 至 1.6.2
- [升级]SpringPlugin 至 2.2.0.RELEASE
- [升级]Druid 至 1.2.1
- [升级]JustAuth 至 1.15.8
- [升级]Dubbo 至 2.7.8
- [升级]Guava 至 30.0-jre
- [升级]Avue 至 2.7.0
- [优化]Swagger封装以支持Knife4j最新API
- [优化]引入Knife4j增强配置,生产环境将完全隔离文档访问
- [修复]未引入租户插件后,自定义类空指针的问题
- [删除]Zipkin模块,推荐使用官方独立模式运行服务

## 2.6.1.RELEASE [2020-10-24]
- [升级]SpringBoot 至 2.1.17.RELEASE
- [升级]Mybatis-Plus 至 3.4.0
- [升级]Knife4j 至 2.0.5
- [升级]JJWT 至 0.11.2
- [升级]FastJson 至 1.2.74
- [新增]上下文核心包，优化全局上下文配置
- [新增]secure模块的basic认证功能
- [新增]用户平台拓展模块
- [优化]重构增强cloud模块
- [优化]request核心至boot模块
- [优化]增强mybatis-plus的分页防注入功能
- [优化]sms返回结果，去掉验证码序列化
- [优化]数据权限插件支持最新版mybatis-plus
- [优化]增强sql日志拦截器
- [优化]增强令牌，新增对用户平台的判断逻辑
- [优化]代码生成增加对sqlserver的支持
- [优化]自定义mapper的api
- [修复]Kv类克隆强转问题
- [修复]elk配置无法读取项目名的问题
- [修复]区划字段level为regionLevel以防oracle报错

## 2.6.0.RELEASE [2020-08-16]
- [升级]Avue 至 2.6.15
- [升级]SpringBoot 至 2.1.16.RELEASE
- [升级]Seata 至 1.3.0
- [升级]Nacos 至 1.3.2
- [升级]FastJson 至 1.2.73
- [升级]Knife4j 至 2.0.4
- [升级]EasyExcel 至 2.2.6
- [升级]JustAuth 至 1.15.6
- [新增]多租户数据库隔离、动态数据源特性
- [新增]SqlServer兼容
- [新增]UReport2报表管理模块
- [新增]对象存储附件表功能
- [优化]LocalFile支持序列化
- [优化]MinioTemplate增加ContentType配置
- [优化]LogBack-Elk的配置
- [优化]流程状态变更的返回信息
- [优化]顶部菜单配置接口，支持大容量数据传输
- [优化]User密码字段序列化
- [优化]序列化additionalInformation，解决非null值报错的问题
- [修复]启用Token有状态模式下刷新Token的问题
- [修复]日志表无法入库TenantId的问题
- [修复]flowable-oracle脚本运行错误的问题

## 2.5.1.RELEASE [2020-06-10]
- [升级]Avue 至 2.6.1、ElementUI 至 2.13.2
- [升级]SpringBoot 至 2.1.14.RELEASE
- [升级]SpringCloud 至 Greenwich.SR6
- [升级]SpringCloud Alibaba 至 2.1.2.RELEASE
- [升级]Seata 至 1.2.0
- [升级]FastJson 至 1.2.70
- [升级]Knife4j 至 2.0.3
- [升级]MybatisPlus 至3.3.2
- [升级]EasyExcel 至 2.2.4
- [新增]第三方系统登录，集成拓展JustAuth
- [新增]行政区划功能模块
- [新增]API报文加密工具
- [新增]Token配置，支持有状态模式，支持一人在线或多人在线
- [新增]Secure配置，支持配置请求方法类型、请求路径、请求表达式匹配
- [新增]Jackson配置，支持大数字转字符串模式，支持null转空值模式
- [新增]租户账号授权码保护机制，防止私有部署客户篡改数据库越权
- [优化]字典模块，增加树形结构
- [优化]新增租户逻辑，新增时同步超管配置的默认业务字典数据
- [优化]用户导入逻辑，只有超管才可以定义租户编号
- [优化]部门列表逻辑，非超管角色只可看到本级及以下部门数据
- [优化]字典模块，增加枚举类，统一入口
- [优化]DictCache缓存加载逻辑
- [优化]租户缓存刷新逻辑
- [优化]角色配置逻辑，同步取消子角色对应的菜单权限
- [优化]顶部菜单，增加排序功能
- [优化]INode，支持泛型
- [优化]代码结构，为bean统一加上final关键字修饰
- [优化]Nacos动态刷新配置
- [优化]Dockerfile，采用Openj9基础镜像，大幅度降低内存占用
- [优化]工程启动逻辑，关闭Flowable自动建表功能，需要手动导入流程sql
- [修复]SpringBootAdmin读取actuator路径配置
- [修复]用户导入逻辑，修正密码加密规则
- [修复]Boot版本Xss默认配置路径

## 2.5.0.RELEASE [2020-04-15]
- [升级]Avue 至 2.5.0
- [升级]SpringBoot 至 2.1.13
- [升级]FastJson 至 1.2.68
- [升级]Druid 至 1.1.22
- [升级]Knife4j 至 2.0.2
- [升级]Taobao-Sdk 至 20200415
- [升级]docker-maven-plugin 至 dockerfile-maven-plugin
- [新增]验证码开关
- [新增]数据权限全局开关
- [新增]岗位管理模块
- [新增]用户Excel导入导出功能
- [新增]用户绑定岗位功能
- [新增]EasyExcel封装工具ExcelUtil
- [新增]Feign内部线程传递
- [新增]Mybatis-Plus配置，支持配置最大分页数
- [新增]Gateway在多团队协作模式灵活指向本地服务的配置
- [新增]Sms模块的sendMessage接口及SmsResponse响应类
- [新增]CacheUtil租户缓存隔离功能
- [优化]CacheUtil缓存重载逻辑，返回bean不为null但数据全为空将不入缓存
- [优化]缓存清除逻辑，@CacheEvict统一修改为CacheUtil.clear
- [优化]登陆逻辑，前端对密码加密后再传递至鉴权接口
- [优化]Oss上传接口，返回domain字段
- [优化]BladeRedisCache命名为BladeRedis
- [优化]控制台日志打印功能，规避MultipartFile读取报错
- [优化]配置关键字enable统一为enabled
- [优化]keyword日期处理
- [优化]代码生成sql脚本默认在工作台菜单下
- [优化]Jwt获取Token逻辑
- [优化]Token返回，增加岗位ID
- [优化]TokenGranter，采用更简洁的拓展方式
- [优化]日志管理展现方式
- [优化]新建租户逻辑，增加参数读取来设置新建租户的配置
- [优化]流程签收接口，支持多角色操作
- [优化]动态网关，支持读取自定义namespace配置
- [优化]删除租户逻辑，同时删除对应的用户
- [优化]树形懒加载，支持局部实时刷新功能
- [优化]多租户插件新增修改逻辑，若指定tenantId为空则不进行操作
- [优化]SmsBuilder、OssBuilder
- [优化]Sentinel配置
- [优化]XssFilter为全局的BladeRequestFilter
- [优化]BladeX开发手册Linux部署章节讲解
- [优化]Saber相关配置，以适配Avue最新版API
- [优化]Saber相关配置内done与loading的顺序
- [修复]用户基本信息修改的bug
- [修复]QiniuTemplate的putFile循环调用的bug
- [修复]日志框架获取RequestBody为空的bug
- [修复]Saber组件被复用导致没有刷新的bug
- [删除]过时的BladeSecureUrlProperties
- [删除]过时的XssUrlProperties
- [删除]过时的RedisUtil

## 2.4.0.RELEASE [2020-02-28]
- [新增]集成七牛、阿里云、腾讯云、云片等短信服务，支持多租户配置
- [新增]对象存储模块的资源编号字段，可根据编号指定oss配置的服务
- [新增]对象存储、短信配置模块的调试功能，可在线调试配置是否可用
- [新增]超管启用租户过滤的配置
- [升级]SpringBoot 2.1.12，SpringCloud SR5
- [升级]兼容 Seata 1.1
- [优化]对象存储的模块使用体验
- [优化]兼容Oracle模糊查询的写法
- [优化]超管权限，不受租户过期时间影响
- [优化]mybatis-plus相关过期注解
- [优化]xxl-job模块的配置文件
- [优化]INode支持序列化接口
- [优化]统一Oss模块命名
- [优化]部署脚本，升级相关版本
- [修复]数据权限部门过滤已删除对象
- [修复]业务字典缓存bug，增加租户过滤
- [修复]占位符解析器的bug

## 2.3.1.RELEASE [2020-02-09]
- [新增]登陆验证码功能
- [新增]Oauth2自定义TokenGranter
- [新增]工作流绑定租户功能，支持通用流程和定制流程
- [新增]Condition类的自定义参数排除入口
- [新增]增强租户插件功能，新增操作可根据自定义的tenantId值进行覆盖
- [新增]增强超管权限，不受数据权限插件影响
- [升级]mybatis-plus至3.3.1
- [优化]mybatis-plus封装，提升分页可拓展性
- [优化]lib分离打包逻辑
- [优化]CacheUtil初始化逻辑
- [优化]HttpUtil，采用最新封装逻辑
- [优化]角色信息获取逻辑为实时，不受开源版、单体版缓存影响
- [优化]日志打印工具判断空逻辑
- [修复]BeanUtil的class类型判断逻辑
- [删除]基于zookeeper体验不佳的分布式锁

## 2.3.0.RELEASE [2020-01-08]
- [新增]swagger-bootstrap-ui全新升级为knife4j
- [新增]saber升级至avue2.3.5版本
- [新增]saber树表懒加载模式
- [新增]腾讯云存储封装
- [新增]xxl-job集成，支持分布式任务调度
- [新增]kafka、rabbitmq、cloudstream集成
- [新增]redis分布式锁插件
- [新增]高性能http调用模块
- [新增]PropertySource注册逻辑，提高安全性
- [新增]Param参数缓存工具类
- [新增]租户操作，增加创建对应的租户管理员账号、菜单权限
- [新增]租户插件，超管可查看所有租户数据的逻辑
- [新增]租户功能，绑定域名、系统背景、账号额度、过期时间
- [新增]登录、创建用户操作绑定租户配置
- [优化]租户插件判断逻辑，增加flowable相关表的租户过滤排除
- [优化]xss过滤逻辑，提高性能
- [优化]本地文件上传逻辑
- [优化]oss配置，修改后及时生效无需点击启用
- [优化]请求日志展示功能
- [修复]前端关闭租户模式导致的新增用户失效问题
- [修复]OSS相关bucket命名的问题
- [修复]ribbon组件由降级引起的问题

## 2.2.2.RELEASE [2019-12-11]
- [新增]拆分出系统字典表与业务字典表，字典键值改为string类型
- [新增]用户管理增加左树右表功能
- [新增]租户新增增加租户默认类型
- [新增]多租户表对应实体继承TenantEntity
- [新增]用于本地上传的BladeFile类更名为LocalFile防止冲突
- [优化]菜单新增逻辑
- [优化]mybatis-plus默认配置的处理
- [优化]租户过滤判断逻辑，删除多余的类
- [优化]alioss生成地址的逻辑
- [优化]redisTemplate加载逻辑
- [优化]租户处理，简化配置，自动识别需要过滤的租户表
- [优化]数据权限表单用户体验
- [修复]数据权限插件不兼容的问题
- [修复]数据权限树勾选显示问题
- [修复]windows平台elk开关失效的问题
- [修复]租户bean加载逻辑
- [修复]saber代码生成驼峰路径导致的问题
- [修复]docker脚本nginx端口匹配问题
- [修复]机构模块提交未删除缓存的问题
- [修复]oss缓存获取未加租户判断的问题
- [修复]blade-auth在java11下无法运行的问题

## 2.2.1.RELEASE [2019-11-15]
- [新增]集成最新版ELK，增加分布式日志追踪功能
- [新增]增加ELK一键部署docker脚本
- [新增]抽象封装日志管理逻辑
- [新增]BladeX-Biz增加easypoi的demo工程
- [新增]BladeX-Biz增加websocket的demo工程
- [优化]minio文件策略
- [新增]Sql条件构建类去除分页字段
- [优化]sql打印功能
- [优化]wrapper逻辑
- [新增]CommonConstant拆分出LauncherConstant

## 2.2.0.RELEASE [2019-10-29]
- [新增]turbine集群监控服务
- [新增]zipkin分布式链路追踪
- [升级]seata版本至0.9.0，解决分布式事务遇到的bug
- [新增]Launcher的nacos配置改为sharedIds，提升子工程配置优先级
- [新增]changeStatus方法，方便修改业务状态字段
- [新增]saber代码模板增加刷新事件
- [新增]saber底层架构升级
- [新增]saber支持tab切换保存页面状态
- [新增]bom统一版本配置
- [新增]trace starter
- [新增]blade-admin排除seata服务
- [新增]oss敏感操作增加权限校验
- [修复]dict、role不选择父节点报错
- [新增]动态网关设置启动加载
- [新增]字典增加封存功能

## 2.1.0.RELEASE [2019-10-09]
- [升级]springboot 2.1.8、springcloud greenwich sr3
- [新增]seata，提供最简集成方案
- [新增]blade-admin增加nacos动态监听
- [新增]alioss集成，强化oss返回信息
- [新增]获取令牌操作增加空判断
- [新增]拆分数据库依赖、增强mybatis、增加yml自定义配置读取
- [新增]各模块增加默认的yml配置，不占用application.yml
- [新增]ribbon组件，可自定义lb优先选择的ip端，解决团队网关调试需求
- [优化]feign的bean加载逻辑
- [优化]增强condition条件
- [优化]日志打印效果
- [重构]redis模块，增加redis限流功能
- [优化]beanutil性能
- [优化]去掉调试用的RouteEndpoint，增强安全性
- [优化]部门新增逻辑
- [注意]：2.1.0的BladeX-Tool有结构变动，升级时请仔细对比


## 2.0.7.RELEASE [2019-08-18]
- [新增]基于Nacos的动态网关鉴权
- [新增]代码生成增加多数据源选择，强化单表代码生成
- [新增]个人信息修改、头像上传、密码更新功能
- [优化]新建角色逻辑
- [新增]springboot版本升级至2.1.7
- [新增]swagger-bootstrap-ui降级至1.9.4
- [修复]若干issue


## 2.0.6.RELEASE [2019-08-05]
- [新增]一套代码兼容Mysql、Oracle、PostgreSQL三大主流数据库
- [升级]flowable 6.4.2
- [新增]超管默认拥有所有菜单权限
- [修复]权限配置数据长度过大的bug
- [新增]租户信息获取
- [优化]命令行启动顺序
- [升级]alibaba cloud毕业版本
- [新增]日志监听增加自定义配置
- [升级]swagger-bootstrap-ui版本
- [新增]saber表格自适应、增加loading
- [新增]saber通知公告模块增加富文本编辑器


## 2.0.5.RELEASE [2019-07-18]
- [升级]为分布式接口权限系统
- [新增]多租户自定义顶部菜单功能
- [升级]greenwich SR2，mybatis-plus 3.1.2
- [新增]swagger排序规则采用最新注解
- [新增]数据权限增加可见字段配置
- [新增]数据权限增加分布式服务支持
- [新增]远程调用分页的例子，解决mybatis-plus传递IPage反序化出现的bug
- [优化]租户接口权限规则
- [新增]SqlKeyword增加条件判断
- [修复]部分模块包名分层的问题


## 2.0.4.RELEASE [2019-06-28]
- [新增]注解+web可视化配置的动态数据权限系统
- [升级]部门管理为机构管理，增加机构类型
- [新增]解决mybatis-plus排序字段的sql注入问题
- [新增]create_dept统一业务字段
- [新增]swagger ui页面设置Authorize 默认全局参数
- [新增]jsonutil增加封装方法,去掉devtools依赖
- [新增]数据库连接适配mysql8
- [新增]docker-compose脚本增加时区
- [新增]oauth申请token可支持自定义表
- [修复]代码生成sql缺失主键的问题
- [新增]boot版本重构登录逻辑，增强可拓展性

## 2.0.3.RELEASE [2019-06-01]
- [新增]gateway增加动态文档配置，可通过配置nacos动态刷新
- [优化]修正blade_menu代码生成模块删除api的地址
- [优化]mysql依赖
- [新增]LauncherService增加排序功能
- [优化]hystrixfeign加载
- [优化]多租户oss系统逻辑，使之更加易用
- [新增]tenant_code字段统一为tenant_id 


## 2.0.2.RELEASE [2019-05-27]
- [新增]minio封装
- [新增]qiniu封装
- [新增]oss统一接口
- [新增]minio、qiniu，进行统一管理的多租户oss系统
- [优化]blade-core-cloud逻辑
- [新增]bladex-biz增加不同包名的swagger、mybatis配置demo
- [新增]bladex-biz增加nacos自定义注册文件demo
- [新增]bladex-biz增加nacos参数动态刷新demo


## 2.0.1.RELEASE [2019-05-20]
- [新增]兼容jdk11
- [新增]支持refresh_token功能
- [新增]minio封装，支持多租户模式的oss对象存储
- [新增]dubbo最新版本，支持rpc远程调用
- [新增]定制基于nacos的gateway动态网关
- [优化]聚合网关配置，使之更加轻巧
- [新增]CacheUtil增加缓存清除方法
- [优化]日志文件格式
- [新增]Secure拦截器支持自定义加载
- [修复]部分bug修复

## 2.0.0.RELEASE [2019-05-15]
- [升级]SpringBoot 2.1.5
- [新增]Swagger提供list形式配置扫描包
- [新增]DictCache、UserCache、SysCache缓存工具类
- [新增]重新设计EntityWrapper结构，使之更加简单易用
- [新增]强化部分敏感数据的删除校验
- [新增]Condition类的sql条件构造器
- [修复]工作流分页bug
- [优化]docker配置
- [优化]多租户逻辑
- [优化]request打印日志逻辑
- [修复]getIp的bug
- [优化]saber代码生成模板
- [新增]saber更新至element-ui 2.8.2版本
- [修复]saber分页bug
- [新增]crud组件提交报错后恢复按钮状态
- [新增]字典管理表单调整
- [修复]若干issue问题修复

## 2.0.0.RC9 [2019-05-09]
- [新增]深度定制的工作流系统
- [新增]拆分blade-starter-cache，单独分离出redis和ehcache
- [升级]springcloud-alibaba最新版本，支持nacos-1.0.0与sentinel-1.6.0
- [新增]mvn package后jar包汇总至根目录target的功能
- [新增]DictUtil方便调用获取字典数据
- [新增]swagger增加多包扫描的配置
- [新增]单独抽离出流程设计器工程flowable-design
- [新增]业务工程bladex-biz
- [优化]工程目录结构

## 2.0.0.RC8 [2019-04-01]
- [新增]多终端令牌认证系统
- [新增]多租户开关
- [新增]自定义启动器对应的单元测试模块
- [修复]springboot-admin无法读取到服务的bug
- [修复]部分模块没有筛选已删除的问题
- [优化]调整角色分配会越权的问题
- [优化]部署脚本

## 2.0.0.RC7 [2019-03-26]
- [升级]支持OAuth2协议
- [优化]代码生成模板
- [升级]sword核心至antd pro最新版
- [修复]菜单管理获取用户权限路由的bug
- [优化]部署脚本


## 2.0.0.RC6 [2019-03-11]
- [升级]为SaaS多租户系统
- [优化]代码生成逻辑
- [新增]代码生成增加菜单sql
- [新增]SysClient，提供系统信息远程调用
- [优化]部署脚本，增加前端部署实例
- [新增]父子角色过滤，使得角色无法越权配置
- [修复]SecureUtil部分bug

## 2.0.0.RC5 [2019-03-01]
- [修复]字典管理的bug
- [新增]sysclient远程调用
- [升级]依赖
- [优化]更新菜单，分离sword与saber

## 2.0.0.RC4 [2019-02-24]
- [新增]saber代码生成功能
- [优化]统一合并saber与sword系统生成代码的接口
- [优化]blade-develop模块支持本地手动生成代码
- [修复]用户重置密码后无法更新时间的bug
- [优化]用户修改密码时增加判断，不再做二次加密

## 2.0.0.RC3 [2019-02-20]
- [删除]oracle jdk企业库的类，兼容openjdk
- [优化]重写jjwt的类，兼容jdk11
- [优化]设定热加载接口

## 2.0.0.RC2 [2019-02-17]
- [修复]blade-admin启动失败的bug
- [修复]swagger文档失效的bug
- [修复]feign请求头传递失效的bug
- [修复]登陆失败仍跳转至首页的bug
- [修复] open jdk 打包bladex-tool失败的bug
- [删除]去掉sentinel hystrix，重新集成官方原版hystrix


## 2.0.0.RC1 [2019-02-15]
- [全新]第一个预览版首发，全面集成BladeX-Tool