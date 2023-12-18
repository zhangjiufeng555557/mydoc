#  Protostuff 工具类
**类名：** `ProtostuffUtil`

## serialize
```java
/**
 * 序列化方法，把指定对象序列化成字节数组
 *
 * @param obj obj
 * @param <T> T
 * @return byte[]
 */
ProtostuffUtil.serialize(T obj);
```

## deserialize
```java
/**
 * 反序列化方法，将字节数组反序列化成指定Class类型
 *
 * @param data data
 * @param clazz clazz
 * @param <T> T
 * @return T
 */
ProtostuffUtil.deserialize(byte[] data, Class<T> clazz);
```

