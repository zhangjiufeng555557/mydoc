#  基于 spring ConversionService 类型转换
**类名：** `ConvertUtil`

## convert
```java
/**
 * Convenience operation for converting a source object to the specified targetType.
 * {@link TypeDescriptor#forObject(Object)}.
 * @param source the source object
 * @param targetType the target type
 * @param <T> 泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 * or sourceType is {@code null} but source is not {@code null}
 */
ConvertUtil.convert(Object source, Class<T> targetType);
```

## convert
```java
/**
 * Convenience operation for converting a source object to the specified targetType,
 * where the target type is a descriptor that provides additional conversion context.
 * {@link TypeDescriptor#forObject(Object)}.
 * @param source the source object
 * @param sourceType the source type
 * @param targetType the target type
 * @param <T> 泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 * or sourceType is {@code null} but source is not {@code null}
 */
ConvertUtil.convert(Object source, TypeDescriptor sourceType, TypeDescriptor targetType);
```

## convert
```java
/**
 * Convenience operation for converting a source object to the specified targetType,
 * where the target type is a descriptor that provides additional conversion context.
 * Simply delegates to {@link #convert(Object, TypeDescriptor, TypeDescriptor)} and
 * encapsulates the construction of the source type descriptor using
 * {@link TypeDescriptor#forObject(Object)}.
 * @param source the source object
 * @param targetType the target type
 * @param <T> 泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 * or sourceType is {@code null} but source is not {@code null}
 */
ConvertUtil.convert(Object source, TypeDescriptor targetType);
```

