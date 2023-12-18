#  反射工具类
**类名：** `ReflectUtil`

## getBeanGetters
```java
/**
 * 获取 Bean 的所有 get方法
 *
 * @param type 类
 * @return PropertyDescriptor数组
 */
ReflectUtil.getBeanGetters(Class type);
```

## getBeanSetters
```java
/**
 * 获取 Bean 的所有 set方法
 *
 * @param type 类
 * @return PropertyDescriptor数组
 */
ReflectUtil.getBeanSetters(Class type);
```

## getPropertiesHelper
```java
/**
 * 获取 Bean 的所有 PropertyDescriptor
 *
 * @param type 类
 * @param read 读取方法
 * @param write 写方法
 * @return PropertyDescriptor数组
 */
ReflectUtil.getPropertiesHelper(Class type, boolean read, boolean write);
```

## getProperty
```java
/**
 * 获取 bean 的属性信息
 * @param propertyType 类型
 * @param propertyName 属性名
 * @return {Property}
 */
ReflectUtil.getProperty(Class<?> propertyType, String propertyName);
```

## getProperty
```java
/**
 * 获取 bean 的属性信息
 * @param propertyType 类型
 * @param propertyDescriptor PropertyDescriptor
 * @param propertyName 属性名
 * @return {Property}
 */
ReflectUtil.getProperty(Class<?> propertyType, PropertyDescriptor propertyDescriptor, String propertyName);
```

## getTypeDescriptor
```java
/**
 * 获取 bean 的属性信息
 * @param propertyType 类型
 * @param propertyName 属性名
 * @return {Property}
 */
ReflectUtil.getTypeDescriptor(Class<?> propertyType, String propertyName);
```

## getTypeDescriptor
```java
/**
 * 获取 类属性信息
 * @param propertyType 类型
 * @param propertyDescriptor PropertyDescriptor
 * @param propertyName 属性名
 * @return {Property}
 */
ReflectUtil.getTypeDescriptor(Class<?> propertyType, PropertyDescriptor propertyDescriptor, String propertyName);
```

## getField
```java
/**
 * 获取 类属性
 * @param clazz 类信息
 * @param fieldName 属性名
 * @return Field
 */
ReflectUtil.getField(Class<?> clazz, String fieldName);
```

## getAnnotation
```java
/**
 * 获取 所有 field 属性上的注解
 * @param clazz 类
 * @param fieldName 属性名
 * @param annotationClass 注解
 * @param <T> 注解泛型
 * @return 注解
 */
ReflectUtil.getAnnotation(Class<?> clazz, String fieldName, Class<T> annotationClass);
```

## handleReflectionException
```java
/**
 * Handle the given reflection exception. Should only be called if no
 * checked exception is expected to be thrown by the target method.
 * <p>Throws the underlying RuntimeException or Error in case of an
 * InvocationTargetException with such a root cause. Throws an
 * IllegalStateException with an appropriate message or
 * UndeclaredThrowableException otherwise.
 * @param ex the reflection exception to handle
 */
ReflectUtil.handleReflectionException(Exception ex);
```

## handleInvocationTargetException
```java
/**
 * Handle the given invocation target exception. Should only be called if no
 * checked exception is expected to be thrown by the target method.
 * <p>Throws the underlying RuntimeException or Error in case of such a root
 * cause. Throws an UndeclaredThrowableException otherwise.
 * @param ex the invocation target exception to handle
 */
ReflectUtil.handleInvocationTargetException(InvocationTargetException ex);
```

## rethrowRuntimeException
```java
/**
 * Rethrow the given {@link Throwable exception}, which is presumably the
 * <em>target exception</em> of an {@link InvocationTargetException}.
 * Should only be called if no checked exception is expected to be thrown
 * by the target method.
 * <p>Rethrows the underlying exception cast to a {@link RuntimeException} or
 * {@link Error} if appropriate; otherwise, throws an
 * {@link UndeclaredThrowableException}.
 * @param ex the exception to rethrow
 * @throws RuntimeException the rethrown exception
 */
ReflectUtil.rethrowRuntimeException(Throwable ex);
```

## rethrowException
```java
/**
 * Rethrow the given {@link Throwable exception}, which is presumably the
 * <em>target exception</em> of an {@link InvocationTargetException}.
 * Should only be called if no checked exception is expected to be thrown
 * by the target method.
 * <p>Rethrows the underlying exception cast to an {@link Exception} or
 * {@link Error} if appropriate; otherwise, throws an
 * {@link UndeclaredThrowableException}.
 * @param ex the exception to rethrow
 * @throws Exception the rethrown exception (in case of a checked exception)
 */
ReflectUtil.rethrowException(Throwable ex);
```

## accessibleConstructor
```java
/**
 * Obtain an accessible constructor for the given class and parameters.
 * @param clazz the clazz to check
 * @param parameterTypes the parameter types of the desired constructor
 * @return the constructor reference
 * @throws NoSuchMethodException if no such constructor exists
 * @since 5.0
 */
ReflectUtil.accessibleConstructor(Class<T> clazz, Class<?> parameterTypes);
```

## makeAccessible
```java
/**
 * Make the given constructor accessible, explicitly setting it accessible
 * if necessary. The {@code setAccessible(true)} method is only called
 * when actually necessary, to avoid unnecessary conflicts with a JVM
 * SecurityManager (if active).
 * @param ctor the constructor to make accessible
 * @see java.lang.reflect.Constructor#setAccessible
 */
ReflectUtil.makeAccessible(Constructor<?> ctor);
```

## findMethod
```java
/**
 * Attempt to find a {@link Method} on the supplied class with the supplied name
 * and no parameters. Searches all superclasses up to {@code Object}.
 * <p>Returns {@code null} if no {@link Method} can be found.
 * @param clazz the class to introspect
 * @param name the name of the method
 * @return the Method object, or {@code null} if none found
 */
ReflectUtil.findMethod(Class<?> clazz, String name);
```

## findMethod
```java
/**
 * Attempt to find a {@link Method} on the supplied class with the supplied name
 * and parameter types. Searches all superclasses up to {@code Object}.
 * <p>Returns {@code null} if no {@link Method} can be found.
 * @param clazz the class to introspect
 * @param name the name of the method
 * @param paramTypes the parameter types of the method
 * (may be {@code null} to indicate any signature)
 * @return the Method object, or {@code null} if none found
 */
ReflectUtil.findMethod(Class<?> clazz, String name, Class<?> paramTypes);
```

## invokeMethod
```java
/**
 * Invoke the specified {@link Method} against the supplied target object with no arguments.
 * The target object can be {@code null} when invoking a static {@link Method}.
 * <p>Thrown exceptions are handled via a call to {@link #handleReflectionException}.
 * @param method the method to invoke
 * @param target the target object to invoke the method on
 * @return the invocation result, if any
 * @see #invokeMethod(java.lang.reflect.Method, Object, Object[])
 */
ReflectUtil.invokeMethod(Method method, Object target);
```

## invokeMethod
```java
/**
 * Invoke the specified {@link Method} against the supplied target object with the
 * supplied arguments. The target object can be {@code null} when invoking a
 * static {@link Method}.
 * <p>Thrown exceptions are handled via a call to {@link #handleReflectionException}.
 * @param method the method to invoke
 * @param target the target object to invoke the method on
 * @param args the invocation arguments (may be {@code null})
 * @return the invocation result, if any
 */
ReflectUtil.invokeMethod(Method method, Object target, Object args);
```

## invokeJdbcMethod
```java
/**
 * Invoke the specified JDBC API {@link Method} against the supplied target
 * object with no arguments.
 * @param method the method to invoke
 * @param target the target object to invoke the method on
 * @return the invocation result, if any
 * @throws SQLException the JDBC API SQLException to rethrow (if any)
 * @see #invokeJdbcMethod(java.lang.reflect.Method, Object, Object[])
 * @deprecated as of 5.0.11, in favor of custom SQLException handling
 */
ReflectUtil.invokeJdbcMethod(Method method, Object target);
```

## invokeJdbcMethod
```java
/**
 * Invoke the specified JDBC API {@link Method} against the supplied target
 * object with the supplied arguments.
 * @param method the method to invoke
 * @param target the target object to invoke the method on
 * @param args the invocation arguments (may be {@code null})
 * @return the invocation result, if any
 * @throws SQLException the JDBC API SQLException to rethrow (if any)
 * @see #invokeMethod(java.lang.reflect.Method, Object, Object[])
 * @deprecated as of 5.0.11, in favor of custom SQLException handling
 */
ReflectUtil.invokeJdbcMethod(Method method, Object target, Object args);
```

## declaresException
```java
/**
 * Determine whether the given method explicitly declares the given
 * exception or one of its superclasses, which means that an exception
 * of that type can be propagated as-is within a reflective invocation.
 * @param method the declaring method
 * @param exceptionType the exception to throw
 * @return {@code true} if the exception can be thrown as-is;
 * {@code false} if it needs to be wrapped
 */
ReflectUtil.declaresException(Method method, Class<?> exceptionType);
```

## doWithLocalMethods
```java
/**
 * Perform the given callback operation on all matching methods of the given
 * class, as locally declared or equivalent thereof (such as default methods
 * on Java 8 based interfaces that the given class implements).
 * @param clazz the class to introspect
 * @param mc the callback to invoke for each method
 * @throws IllegalStateException if introspection fails
 * @since 4.2
 * @see #doWithMethods
 */
ReflectUtil.doWithLocalMethods(Class<?> clazz, ReflectionUtils.MethodCallback mc);
```

## doWithMethods
```java
/**
 * Perform the given callback operation on all matching methods of the given
 * class and superclasses.
 * <p>The same named method occurring on subclass and superclass will appear
 * twice, unless excluded by a {@link ReflectionUtils.MethodFilter}.
 * @param clazz the class to introspect
 * @param mc the callback to invoke for each method
 * @throws IllegalStateException if introspection fails
 * @see #doWithMethods(Class, ReflectionUtils.MethodCallback, ReflectionUtils.MethodFilter)
 */
ReflectUtil.doWithMethods(Class<?> clazz, ReflectionUtils.MethodCallback mc);
```

## doWithMethods
```java
/**
 * Perform the given callback operation on all matching methods of the given
 * class and superclasses (or given interface and super-interfaces).
 * <p>The same named method occurring on subclass and superclass will appear
 * twice, unless excluded by the specified {@link ReflectionUtils.MethodFilter}.
 * @param clazz the class to introspect
 * @param mc the callback to invoke for each method
 * @param mf the filter that determines the methods to apply the callback to
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.doWithMethods(Class<?> clazz, ReflectionUtils.MethodCallback mc, ReflectionUtils.MethodFilter mf);
```

## getAllDeclaredMethods
```java
/**
 * Get all declared methods on the leaf class and all superclasses.
 * Leaf class methods are included first.
 * @param leafClass the class to introspect
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.getAllDeclaredMethods(Class<?> leafClass);
```

## getUniqueDeclaredMethods
```java
/**
 * Get the unique set of declared methods on the leaf class and all superclasses.
 * Leaf class methods are included first and while traversing the superclass hierarchy
 * any methods found with signatures matching a method already included are filtered out.
 * @param leafClass the class to introspect
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.getUniqueDeclaredMethods(Class<?> leafClass);
```

## isEqualsMethod
```java
/**
 * Determine whether the given method is an "equals" method.
 * @see java.lang.Object#equals(Object)
 */
ReflectUtil.isEqualsMethod(Method method);
```

## isHashCodeMethod
```java
/**
 * Determine whether the given method is a "hashCode" method.
 * @see java.lang.Object#hashCode()
 */
ReflectUtil.isHashCodeMethod(Method method);
```

## isToStringMethod
```java
/**
 * Determine whether the given method is a "toString" method.
 * @see java.lang.Object#toString()
 */
ReflectUtil.isToStringMethod(Method method);
```

## isObjectMethod
```java
/**
 * Determine whether the given method is originally declared by {@link java.lang.Object}.
 */
ReflectUtil.isObjectMethod(Method method);
```

## isCglibRenamedMethod
```java
/**
 * Determine whether the given method is a CGLIB 'renamed' method,
 * following the pattern "CGLIB$methodName$0".
 * @param renamedMethod the method to check
 */
ReflectUtil.isCglibRenamedMethod(Method renamedMethod);
```

## makeAccessible
```java
/**
 * Make the given method accessible, explicitly setting it accessible if
 * necessary. The {@code setAccessible(true)} method is only called
 * when actually necessary, to avoid unnecessary conflicts with a JVM
 * SecurityManager (if active).
 * @param method the method to make accessible
 * @see java.lang.reflect.Method#setAccessible
 */
ReflectUtil.makeAccessible(Method method);
```

## findField
```java
/**
 * Attempt to find a {@link Field field} on the supplied {@link Class} with the
 * supplied {@code name}. Searches all superclasses up to {@link Object}.
 * @param clazz the class to introspect
 * @param name the name of the field
 * @return the corresponding Field object, or {@code null} if not found
 */
ReflectUtil.findField(Class<?> clazz, String name);
```

## findField
```java
/**
 * Attempt to find a {@link Field field} on the supplied {@link Class} with the
 * supplied {@code name} and/or {@link Class type}. Searches all superclasses
 * up to {@link Object}.
 * @param clazz the class to introspect
 * @param name the name of the field (may be {@code null} if type is specified)
 * @param type the type of the field (may be {@code null} if name is specified)
 * @return the corresponding Field object, or {@code null} if not found
 */
ReflectUtil.findField(Class<?> clazz, String name, Class<?> type);
```

## setField
```java
/**
 * Set the field represented by the supplied {@link Field field object} on the
 * specified {@link Object target object} to the specified {@code value}.
 * In accordance with {@link Field#set(Object, Object)} semantics, the new value
 * is automatically unwrapped if the underlying field has a primitive type.
 * <p>Thrown exceptions are handled via a call to {@link #handleReflectionException(Exception)}.
 * @param field the field to set
 * @param target the target object on which to set the field
 * @param value the value to set (may be {@code null})
 */
ReflectUtil.setField(Field field, Object target, Object value);
```

## getField
```java
/**
 * Get the field represented by the supplied {@link Field field object} on the
 * specified {@link Object target object}. In accordance with {@link Field#get(Object)}
 * semantics, the returned value is automatically wrapped if the underlying field
 * has a primitive type.
 * <p>Thrown exceptions are handled via a call to {@link #handleReflectionException(Exception)}.
 * @param field the field to get
 * @param target the target object from which to get the field
 * @return the field's current value
 */
ReflectUtil.getField(Field field, Object target);
```

## doWithLocalFields
```java
/**
 * Invoke the given callback on all locally declared fields in the given class.
 * @param clazz the target class to analyze
 * @param fc the callback to invoke for each field
 * @throws IllegalStateException if introspection fails
 * @since 4.2
 * @see #doWithFields
 */
ReflectUtil.doWithLocalFields(Class<?> clazz, ReflectionUtils.FieldCallback fc);
```

## doWithFields
```java
/**
 * Invoke the given callback on all fields in the target class, going up the
 * class hierarchy to get all declared fields.
 * @param clazz the target class to analyze
 * @param fc the callback to invoke for each field
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.doWithFields(Class<?> clazz, ReflectionUtils.FieldCallback fc);
```

## doWithFields
```java
/**
 * Invoke the given callback on all fields in the target class, going up the
 * class hierarchy to get all declared fields.
 * @param clazz the target class to analyze
 * @param fc the callback to invoke for each field
 * @param ff the filter that determines the fields to apply the callback to
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.doWithFields(Class<?> clazz, ReflectionUtils.FieldCallback fc, ReflectionUtils.FieldFilter ff);
```

## shallowCopyFieldState
```java
/**
 * Given the source object and the destination, which must be the same class
 * or a subclass, copy all fields, including inherited fields. Designed to
 * work on objects with public no-arg constructors.
 * @throws IllegalStateException if introspection fails
 */
ReflectUtil.shallowCopyFieldState(Object src, Object dest);
```

## isPublicStaticFinal
```java
/**
 * Determine whether the given field is a "public static final" constant.
 * @param field the field to check
 */
ReflectUtil.isPublicStaticFinal(Field field);
```

## makeAccessible
```java
/**
 * Make the given field accessible, explicitly setting it accessible if
 * necessary. The {@code setAccessible(true)} method is only called
 * when actually necessary, to avoid unnecessary conflicts with a JVM
 * SecurityManager (if active).
 * @param field the field to make accessible
 * @see java.lang.reflect.Field#setAccessible
 */
ReflectUtil.makeAccessible(Field field);
```

## clearCache
```java
/**
 * Clear the internal method/field cache.
 * @since 4.2.4
 */
ReflectUtil.clearCache();
```

