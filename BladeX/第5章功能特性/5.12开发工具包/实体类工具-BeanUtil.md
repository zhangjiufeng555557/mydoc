#  实体工具类
**类名：** `BeanUtil`

## newInstance
```java
/**
 * 实例化对象
 *
 * @param clazz 类
 * @param <T>   泛型标记
 * @return 对象
 */
BeanUtil.newInstance(Class<?> clazz);
```

## newInstance
```java
/**
 * 实例化对象
 *
 * @param clazzStr 类名
 * @param <T>      泛型标记
 * @return 对象
 */
BeanUtil.newInstance(String clazzStr);
```

## getProperty
```java
/**
 * 获取Bean的属性, 支持 propertyName 多级 ：test.user.name
 *
 * @param bean         bean
 * @param propertyName 属性名
 * @return 属性值
 */
BeanUtil.getProperty(Object bean, String propertyName);
```

## setProperty
```java
/**
 * 设置Bean属性, 支持 propertyName 多级 ：test.user.name
 *
 * @param bean         bean
 * @param propertyName 属性名
 * @param value        属性值
 */
BeanUtil.setProperty(Object bean, String propertyName, Object value);
```

## clone
```java
/**
 * 深复制
 *
 * <p>
 * 支持 map bean
 * </p>
 *
 * @param source 源对象
 * @param <T>    泛型标记
 * @return T
 */
BeanUtil.clone(T source);
```

## copy
```java
/**
 * copy 对象属性，默认不使用Convert
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source 源对象
 * @param clazz  类名
 * @param <T>    泛型标记
 * @return T
 */
BeanUtil.copy(Object source, Class<T> clazz);
```

## copy
```java
/**
 * copy 对象属性，默认不使用Convert
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source      源对象
 * @param sourceClazz 源类型
 * @param targetClazz 转换成的类型
 * @param <T>         泛型标记
 * @return T
 */
BeanUtil.copy(Object source, Class sourceClazz, Class<T> targetClazz);
```

## copy
```java
/**
 * copy 列表对象，默认不使用Convert
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param sourceList  源列表
 * @param targetClazz 转换成的类型
 * @param <T>         泛型标记
 * @return T
 */
BeanUtil.copy(Collection<?> sourceList, Class<T> targetClazz);
```

## copy
```java
/**
 * 拷贝对象
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source     源对象
 * @param targetBean 需要赋值的对象
 */
BeanUtil.copy(Object source, Object targetBean);
```

## copyNonNull
```java
/**
 * 拷贝对象，source 属性做 null 判断，Map 不支持，map 会做 instanceof 判断，不会
 *
 * <p>
 * 支持 bean copy
 * </p>
 *
 * @param source     源对象
 * @param targetBean 需要赋值的对象
 */
BeanUtil.copyNonNull(Object source, Object targetBean);
```

## copyWithConvert
```java
/**
 * 拷贝对象并对不同类型属性进行转换
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source 源对象
 * @param targetClazz 转换成的类
 * @param <T>    泛型标记
 * @return T
 */
BeanUtil.copyWithConvert(Object source, Class<T> targetClazz);
```

## copyWithConvert
```java
/**
 * 拷贝对象并对不同类型属性进行转换
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source 源对象
 * @param sourceClazz 源类
 * @param targetClazz 转换成的类
 * @param <T>    泛型标记
 * @return T
 */
BeanUtil.copyWithConvert(Object source, Class<?> sourceClazz, Class<T> targetClazz);
```

## copyWithConvert
```java
/**
 * 拷贝列表并对不同类型属性进行转换
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param sourceList 源对象列表
 * @param targetClazz 转换成的类
 * @param <T>    泛型标记
 * @return List
 */
BeanUtil.copyWithConvert(Collection<?> sourceList, Class<T> targetClazz);
```

## copyProperties
```java
/**
 * Copy the property values of the given source bean into the target class.
 * <p>Note: The source and target classes do not have to match or even be derived
 * from each other, as long as the properties match. Any bean properties that the
 * source bean exposes but the target bean does not will silently be ignored.
 * <p>This is just a convenience method. For more complex transfer needs,
 *
 * @param source the source bean
 * @param targetClazz the target bean class
 * @param <T>    泛型标记
 * @return T
 * @throws BeansException if the copying failed
 */
BeanUtil.copyProperties(Object source, Class<T> targetClazz);
```

## copyProperties
```java
/**
 * Copy the property values of the given source bean into the target class.
 * <p>Note: The source and target classes do not have to match or even be derived
 * from each other, as long as the properties match. Any bean properties that the
 * source bean exposes but the target bean does not will silently be ignored.
 * <p>This is just a convenience method. For more complex transfer needs,
 *
 * @param sourceList the source list bean
 * @param targetClazz the target bean class
 * @param <T>    泛型标记
 * @return List
 * @throws BeansException if the copying failed
 */
BeanUtil.copyProperties(Collection<?> sourceList, Class<T> targetClazz);
```

## toMap
```java
/**
 * 将对象装成map形式
 *
 * @param bean 源对象
 * @return {Map}
 */
BeanUtil.toMap(Object bean);
```

## toBean
```java
/**
 * 将map 转为 bean
 *
 * @param beanMap   map
 * @param valueType 对象类型
 * @param <T>       泛型标记
 * @return {T}
 */
BeanUtil.toBean(Map<String,Object> beanMap, Class<T> valueType);
```

## generator
```java
/**
 * 给一个Bean添加字段
 *
 * @param superBean 父级Bean
 * @param props     新增属性
 * @return {Object}
 */
BeanUtil.generator(Object superBean, BeanProperty props);
```

## generator
```java
/**
 * 给一个class添加字段
 *
 * @param superclass 父级
 * @param props      新增属性
 * @return {Object}
 */
BeanUtil.generator(Class<?> superclass, BeanProperty props);
```

