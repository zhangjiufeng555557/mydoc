#  Jackson工具类
**类名：** `JsonUtil`

## toJson
```java
/**
 * 将对象序列化成json字符串
 *
 * @param value javaBean
 * @return jsonString json字符串
 */
JsonUtil.toJson(T value);
```

## toJsonAsBytes
```java
/**
 * 将对象序列化成 json byte 数组
 *
 * @param object javaBean
 * @return jsonString json字符串
 */
JsonUtil.toJsonAsBytes(Object object);
```

## parse
```java
/**
 * 将json反序列化成对象
 *
 * @param content   content
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
JsonUtil.parse(String content, Class<T> valueType);
```

## parse
```java
/**
 * 将json反序列化成对象
 *
 * @param content       content
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.parse(String content, TypeReference<?> typeReference);
```

## parse
```java
/**
 * 将json byte 数组反序列化成对象
 *
 * @param bytes     json bytes
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
JsonUtil.parse(byte[] bytes, Class<T> valueType);
```

## parse
```java
/**
 * 将json反序列化成对象
 *
 * @param bytes         bytes
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.parse(byte[] bytes, TypeReference<?> typeReference);
```

## parse
```java
/**
 * 将json反序列化成对象
 *
 * @param in        InputStream
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
JsonUtil.parse(InputStream in, Class<T> valueType);
```

## parse
```java
/**
 * 将json反序列化成对象
 *
 * @param in            InputStream
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.parse(InputStream in, TypeReference<?> typeReference);
```

## parseArray
```java
/**
 * 将json反序列化成List对象
 *
 * @param content      content
 * @param valueTypeRef class
 * @param <T>          T 泛型标记
 * @return List<T>
 */
JsonUtil.parseArray(String content, Class<T> valueTypeRef);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param jsonString jsonString
 * @return jsonString json字符串
 */
JsonUtil.readTree(String jsonString);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param in InputStream
 * @return jsonString json字符串
 */
JsonUtil.readTree(InputStream in);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param content content
 * @return jsonString json字符串
 */
JsonUtil.readTree(byte[] content);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param jsonParser JsonParser
 * @return jsonString json字符串
 */
JsonUtil.readTree(JsonParser jsonParser);
```

## readValue
```java
/**
 * 将json byte 数组反序列化成对象
 *
 * @param content   json bytes
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(byte[] content, Class<T> valueType);
```

## readValue
```java
/**
 * 将json反序列化成对象
 *
 * @param jsonString jsonString
 * @param valueType  class
 * @param <T>        T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(String jsonString, Class<T> valueType);
```

## readValue
```java
/**
 * 将json反序列化成对象
 *
 * @param in        InputStream
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(InputStream in, Class<T> valueType);
```

## readValue
```java
/**
 * 将json反序列化成对象
 *
 * @param content       bytes
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(byte[] content, TypeReference<T> typeReference);
```

## readValue
```java
/**
 * 将json反序列化成对象
 *
 * @param jsonString    jsonString
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(String jsonString, TypeReference<T> typeReference);
```

## readValue
```java
/**
 * 将json反序列化成对象
 *
 * @param in            InputStream
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
JsonUtil.readValue(InputStream in, TypeReference<T> typeReference);
```

## getMapType
```java
/**
 * 封装 map type
 *
 * @param keyClass   key 类型
 * @param valueClass value 类型
 * @return MapType
 */
JsonUtil.getMapType(Class<?> keyClass, Class<?> valueClass);
```

## getListType
```java
/**
 * 封装 map type
 *
 * @param elementClass 集合值类型
 * @return CollectionLikeType
 */
JsonUtil.getListType(Class<?> elementClass);
```

## readList
```java
/**
 * 读取集合
 *
 * @param content      bytes
 * @param elementClass elementClass
 * @param <T>          泛型
 * @return 集合
 */
JsonUtil.readList(byte[] content, Class<T> elementClass);
```

## readList
```java
/**
 * 读取集合
 *
 * @param content      InputStream
 * @param elementClass elementClass
 * @param <T>          泛型
 * @return 集合
 */
JsonUtil.readList(InputStream content, Class<T> elementClass);
```

## readList
```java
/**
 * 读取集合
 *
 * @param content      bytes
 * @param elementClass elementClass
 * @param <T>          泛型
 * @return 集合
 */
JsonUtil.readList(String content, Class<T> elementClass);
```

## readMap
```java
/**
 * 读取集合
 *
 * @param content    bytes
 * @param keyClass   key类型
 * @param valueClass 值类型
 * @param <K>        泛型
 * @param <V>        泛型
 * @return 集合
 */
JsonUtil.readMap(byte[] content, Class<?> keyClass, Class<?> valueClass);
```

## readMap
```java
/**
 * 读取集合
 *
 * @param content    InputStream
 * @param keyClass   key类型
 * @param valueClass 值类型
 * @param <K>        泛型
 * @param <V>        泛型
 * @return 集合
 */
JsonUtil.readMap(InputStream content, Class<?> keyClass, Class<?> valueClass);
```

## readMap
```java
/**
 * 读取集合
 *
 * @param content    bytes
 * @param keyClass   key类型
 * @param valueClass 值类型
 * @param <K>        泛型
 * @param <V>        泛型
 * @return 集合
 */
JsonUtil.readMap(String content, Class<?> keyClass, Class<?> valueClass);
```

## convertValue
```java
/**
 * jackson 的类型转换
 *
 * @param fromValue   来源对象
 * @param toValueType 转换的类型
 * @param <T>         泛型标记
 * @return 转换结果
 */
JsonUtil.convertValue(Object fromValue, Class<T> toValueType);
```

## convertValue
```java
/**
 * jackson 的类型转换
 *
 * @param fromValue   来源对象
 * @param toValueType 转换的类型
 * @param <T>         泛型标记
 * @return 转换结果
 */
JsonUtil.convertValue(Object fromValue, JavaType toValueType);
```

## convertValue
```java
/**
 * jackson 的类型转换
 *
 * @param fromValue      来源对象
 * @param toValueTypeRef 泛型类型
 * @param <T>            泛型标记
 * @return 转换结果
 */
JsonUtil.convertValue(Object fromValue, TypeReference<T> toValueTypeRef);
```

## treeToValue
```java
/**
 * tree 转对象
 *
 * @param treeNode  TreeNode
 * @param valueType valueType
 * @param <T>       泛型标记
 * @return 转换结果
 */
JsonUtil.treeToValue(TreeNode treeNode, Class<T> valueType);
```

## valueToTree
```java
/**
 * 对象转为 json node
 *
 * @param value 对象
 * @return JsonNode
 */
JsonUtil.valueToTree(Object value);
```

## canSerialize
```java
/**
 * 判断是否可以序列化
 *
 * @param value 对象
 * @return 是否可以序列化
 */
JsonUtil.canSerialize(Object value);
```

## toMap
```java
/**
 * 转换为Map
 */
JsonUtil.toMap(String content);
```

## toMap
```java
/**
 * 转换为Map
 */
JsonUtil.toMap(String content, Class<T> valueTypeRef);
```

## toPojo
```java
/**
 * 转换为Bean
 */
JsonUtil.toPojo(Map fromValue, Class<T> toValueType);
```

