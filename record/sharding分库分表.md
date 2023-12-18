# shardingsphere+mybatis-plus+dynamic 实现分库分表

### maven 依赖
```maven
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>dynamic-datasource-spring-boot-starter</artifactId>
            <version>3.3.6</version>
        </dependency>
        <!--         sharding-jdbc -->
        <dependency>
            <groupId>org.apache.shardingsphere</groupId>
            <artifactId>shardingsphere-jdbc-core-spring-boot-starter</artifactId>
            <version>5.2.1</version>
        </dependency>
        <!-- 指定版本避免 sharding-jdbc 依赖冲突 -->
        <dependency>
            <groupId>org.yaml</groupId>
            <artifactId>snakeyaml</artifactId>
            <version>1.33</version>
        </dependency>
        <dependency>
            <groupId>com.alibaba</groupId>
            <artifactId>druid</artifactId>
            <version>1.2.16</version>
        </dependency>
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-boot-starter</artifactId>
            <version>3.5.3.1</version>
            <scope>compile</scope>
        </dependency>
        <dependency>
            <groupId>com.baomidou</groupId>
            <artifactId>mybatis-plus-extension</artifactId>
            <version>3.5.3.1</version>
            <scope>compile</scope>
        </dependency>
```

### 配置文件 
 > 该配置为单数据源 单分表操作
```yaml

spring:
  datasource:
    dynamic:
      #设置默认的数据源或者数据源组,默认值即为master
      primary: master
      datasource:
        master:
          druid:
            #独立校验配置
            validation-query: select 1
          # MySql
          url: jdbc:mysql://8.136.110.34:3307/carbon_offset?useSSL=false&useUnicode=true&characterEncoding=utf-8&zeroDateTimeBehavior=convertToNull&transformedBitIsBoolean=true&serverTimezone=GMT%2B8&nullCatalogMeansCurrent=true&allowPublicKeyRetrieval=true
          username: root
          password: Start123!
          driver-class-name: com.mysql.cj.jdbc.Driver
          # 默认true,初始化失败是否继续
#          continue-on-error: true
  #sharding数据源
  shardingsphere:
    datasource:
      #定义的数据库集合
      names: ds1
      #数据库连接别名
      ds1:
        #数据连接池类型
        type: com.alibaba.druid.pool.DruidDataSource
        #驱动类型
        driver-class-name: com.mysql.cj.jdbc.Driver
        #jdbc地址
        url: jdbc:mysql://8.136.110.34:3307/carbon_offset_dev?useSSL=false&useUnicode=true&characterEncoding=utf-8&zeroDateTimeBehavior=convertToNull&transformedBitIsBoolean=true&serverTimezone=GMT%2B8&nullCatalogMeansCurrent=true&allowPublicKeyRetrieval=true
        #数据库账号
        username: root
        #数据库密码
        password: Start123!
    rules:
      sharding:
        #主键生成类型
        key-generators:
          snowflake:
            type: SNOWFLAKE
        tables:
          #分表代号
          chy_log_api:
            #实际节点名称，格式为 库名$->{0..n1}.表名$->{0..n2}
            #v3d_report_log_$->{1..2} 代表有 v3d_report_log_1和v3d_report_log_2两个表
            actual-data-nodes: ds1.chy_log_api_$->{202301..202312}
            #分表策略
            table-strategy:
              standard:
                #分表列名
                sharding-column: create_time
                #分表算法名,不可用下划线
                sharding-algorithm-name: carbon-offset-log-inline
            #主键生成策略
            key-generate-strategy:
              #主键名
              column: id
              #策略算法
              key-generator-name: snowflake
        #分库分表算法
        sharding-algorithms:
          #分表算法名
          carbon-offset-log-inline:
            type: CLASS_BASED
            props:
              # 分片策略
              strategy: standard
              # 分片算法类
              algorithmClassName: com.engine.demo.conf.ShardingAlgorithmA

#            #算法类型
#            type: INTERVAL
#            props:
#              datetime-pattern: yyyy-MM-dd HH:mm:ss
#              datetime-lower: 2023-09-01 00:00:00
#              sharding-suffix-pattern: yyyyMM
#              datetime-interval-unit: MONTHS
    # 是否启用 Sharding
    props:
      sql-show: true
```
### ShardingSphere与DynamicDatasource配置类
```java
@Configuration
@EnableConfigurationProperties(DynamicDataSourceProperties.class)
@AutoConfigureBefore({DynamicDataSourceAutoConfiguration.class, SpringBootConfiguration.class})
public class ShardingConfiguration {

	@Lazy
	@Resource(name = "shardingSphereDataSource")
	private DataSource shardingSphereDataSource;

	/**
	 * 自定义动态数据源加载逻辑
	 */
	@Bean
	public DynamicDataSourceProvider dynamicDataSourceProvider(DynamicDataSourceProperties dynamicDataSourceProperties) {
		Map<String, DataSourceProperty> datasourceMap = dynamicDataSourceProperties.getDatasource();
		return new AbstractDataSourceProvider() {
			@Override
			public Map<String, DataSource> loadDataSources() {
				Map<String, DataSource> dataSourceMap = createDataSourceMap(datasourceMap);
				dataSourceMap.put("sharding", shardingSphereDataSource);
				return dataSourceMap;
			}
		};
	}

	/**
	 * 配置动态数据源（若引入blade-starter-tenant并开启dynamic-datasource会有冲突，后续将整合适配）
	 */
	@Primary
	@Bean
	public DataSource dataSource(DynamicDataSourceProvider dynamicDataSourceProvider, DynamicDataSourceProperties dynamicDataSourceProperties) {
		DynamicRoutingDataSource dataSource = new DynamicRoutingDataSource();
		dataSource.setPrimary(dynamicDataSourceProperties.getPrimary());
		dataSource.setStrict(dynamicDataSourceProperties.getStrict());
		dataSource.setStrategy(dynamicDataSourceProperties.getStrategy());
		dataSource.setP6spy(dynamicDataSourceProperties.getP6spy());
		dataSource.setSeata(dynamicDataSourceProperties.getSeata());
		dataSource.setProvider(dynamicDataSourceProvider);
		return dataSource;
	}
}
```
### 自定义分片算法类
```java

public class ShardingAlgorithmA implements StandardShardingAlgorithm<Date> {

    private static final SimpleDateFormat SDF = new SimpleDateFormat("yyyyMM");

    /**
     * 精确切片 匹配到条件 大于小于等于等条件  处理逻辑为查找到时间条件对应的具体该查询那个月份的表(单表)
     * @param collection
     * @param preciseShardingValue
     * @return
     */
    @Override
    public String doSharding(Collection<String> collection, PreciseShardingValue<Date> preciseShardingValue) {
        Date date = preciseShardingValue.getValue();
        Optional<String> opt = collection.stream().filter(x -> x.endsWith(SDF.format(date))).findFirst();
        return opt.orElse(null);
    }

    /**
     * 范围切片 匹配到条件 between 等  处理逻辑为查找到最大时间条件与最小时间条件之间的所有的月份的表 (多表)
     * @param collection
     * @param rangeShardingValue
     * @return
     */
    @Override
    public Collection<String> doSharding(Collection<String> collection, RangeShardingValue<Date> rangeShardingValue) {
        Integer lower = Integer.valueOf(SDF.format(rangeShardingValue.getValueRange().lowerEndpoint()));
        Integer upper = Integer.valueOf(SDF.format(rangeShardingValue.getValueRange().upperEndpoint()));
        List<String> suffix = new ArrayList<>();
        collection = collection.stream().filter(x -> Integer.valueOf(x.substring(x.lastIndexOf("_") +1, x.length())) >= lower && Integer.valueOf(x.substring(x.lastIndexOf("_") +1 , x.length())) <= upper).collect(Collectors.toList());
        return collection;
    }

    @Override
    public Properties getProps() {
        return null;
    }

    @Override
    public void init(Properties properties) {

    }
}

```
### 使用 
 > 在数据库将对应的表chy_log_api的分表创建好chy_log_api_202301 ~ chy_log_api_202312
 > 直接按照正常查询逻辑对chy_log_api进行查询