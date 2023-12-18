#  占位符解析器
**类名：** `PlaceholderUtil`

## getDefaultResolver
```java
/**
 * 获取默认的占位符解析器，即占位符前缀为"${", 后缀为"}"
 *
 * @return PlaceholderUtil
 */
PlaceholderUtil.getDefaultResolver();
```

## getResolver
```java
/**
 */
PlaceholderUtil.getResolver(String placeholderPrefix, String placeholderSuffix);
```

## resolve
```java
/**
 * 解析带有指定占位符的模板字符串，默认占位符为前缀：${  后缀：}<br/><br/>
 * 如：template = category:${}:product:${}<br/>
 * values = {"1", "2"}<br/>
 * 返回 category:1:product:2<br/>
 *
 * @param content 要解析的带有占位符的模板字符串
 * @param values  按照模板占位符索引位置设置对应的值
 * @return {String}
 */
PlaceholderUtil placeholderUtil = new PlaceholderUtil();
placeholderUtil.resolve(String content, String values);
```

## resolve
```java
/**
 * 解析带有指定占位符的模板字符串，默认占位符为前缀：${  后缀：}<br/><br/>
 * 如：template = category:${}:product:${}<br/>
 * values = {"1", "2"}<br/>
 * 返回 category:1:product:2<br/>
 *
 * @param content 要解析的带有占位符的模板字符串
 * @param values  按照模板占位符索引位置设置对应的值
 * @return {String}
 */
PlaceholderUtil placeholderUtil = new PlaceholderUtil();
placeholderUtil.resolve(String content, Object[] values);
```

## resolveByRule
```java
/**
 * 根据替换规则来替换指定模板中的占位符值
 *
 * @param content 要解析的字符串
 * @param rule    解析规则回调
 * @return {String}
 */
PlaceholderUtil placeholderUtil = new PlaceholderUtil();
placeholderUtil.resolveByRule(String content, Function<String,String> rule);
```

## resolveByMap
```java
/**
 * 替换模板中占位符内容，占位符的内容即为map key对应的值，key为占位符中的内容。<br/><br/>
 * 如：content = product:${id}:detail:${did}<br/>
 * valueMap = id -> 1; pid -> 2<br/>
 * 经过解析返回 product:1:detail:2<br/>
 *
 * @param content  模板内容
 * @param valueMap 值映射
 * @return 替换完成后的字符串
 */
PlaceholderUtil placeholderUtil = new PlaceholderUtil();
placeholderUtil.resolveByMap(String content, Map<String,Object> valueMap);
```

## resolveByProperties
```java
/**
 * 根据properties文件替换占位符内容
 *
 * @param content    模板内容
 * @param properties 配置
 * @return {String}
 */
PlaceholderUtil placeholderUtil = new PlaceholderUtil();
placeholderUtil.resolveByProperties(String content, Properties properties);
```

