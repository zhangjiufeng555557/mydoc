#  通过在ThreadLocal存储map信息,实现维护多个信息
**类名：** `ThreadLocalUtil`

## getAll
```java
/**
 * @return threadLocal中的全部值
 */
ThreadLocalUtil.getAll();
```

## put
```java
/**
 * 设置一个值到ThreadLocal
 *
 * @param key   键
 * @param value 值
 * @param <T>   值的类型
 * @return 被放入的值
 * @see Map#put(Object, Object)
 */
ThreadLocalUtil.put(String key, T value);
```

## put
```java
/**
 * 设置一个值到ThreadLocal
 *
 * @param map map
 * @return 被放入的值
 * @see Map#putAll(Map)
 */
ThreadLocalUtil.put(Map<String,Object> map);
```

## remove
```java
/**
 * 删除参数对应的值
 *
 * @param key
 * @see Map#remove(Object)
 */
ThreadLocalUtil.remove(String key);
```

## clear
```java
/**
 * 清空ThreadLocal
 *
 * @see Map#clear()
 */
ThreadLocalUtil.clear();
```

## get
```java
/**
 * 从ThreadLocal中获取值
 *
 * @param key 键
 * @param <T> 值泛型
 * @return 值, 不存在则返回null, 如果类型与泛型不一致, 可能抛出{@link ClassCastException}
 * @see Map#get(Object)
 * @see ClassCastException
 */
ThreadLocalUtil.get(String key);
```

## getIfAbsent
```java
/**
 * 从ThreadLocal中获取值,并指定一个当值不存在的提供者
 *
 * @see Supplier
 */
ThreadLocalUtil.getIfAbsent(String key, Supplier<T> supplierOnNull);
```

## getAndRemove
```java
/**
 * 获取一个值后然后删除掉
 *
 * @param key 键
 * @param <T> 值类型
 * @return 值, 不存在则返回null
 * @see this#get(String)
 * @see this#remove(String)
 */
ThreadLocalUtil.getAndRemove(String key);
```

