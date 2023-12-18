#  类操作工具
**类名：** `ClassUtil`

## getMethodParameter
```java
/**
 * 获取方法参数信息
 *
 * @param constructor    构造器
 * @param parameterIndex 参数序号
 * @return {MethodParameter}
 */
ClassUtil.getMethodParameter(Constructor<?> constructor, int parameterIndex);
```

## getMethodParameter
```java
/**
 * 获取方法参数信息
 *
 * @param method         方法
 * @param parameterIndex 参数序号
 * @return {MethodParameter}
 */
ClassUtil.getMethodParameter(Method method, int parameterIndex);
```

## getAnnotation
```java
/**
 * 获取Annotation
 *
 * @param method         Method
 * @param annotationType 注解类
 * @param <A>            泛型标记
 * @return {Annotation}
 */
ClassUtil.getAnnotation(Method method, Class<A> annotationType);
```

## getAnnotation
```java
/**
 * 获取Annotation
 *
 * @param handlerMethod  HandlerMethod
 * @param annotationType 注解类
 * @param <A>            泛型标记
 * @return {Annotation}
 */
ClassUtil.getAnnotation(HandlerMethod handlerMethod, Class<A> annotationType);
```

## isAnnotated
```java
/**
 * 判断是否有注解 Annotation
 *
 * @param method         Method
 * @param annotationType 注解类
 * @param <A>            泛型标记
 * @return {boolean}
 */
ClassUtil.isAnnotated(Method method, Class<A> annotationType);
```

## getDefaultClassLoader
```java
/**
 * Return the default ClassLoader to use: typically the thread context
 * ClassLoader, if available; the ClassLoader that loaded the ClassUtils
 * class will be used as fallback.
 * <p>Call this method if you intend to use the thread context ClassLoader
 * in a scenario where you clearly prefer a non-null ClassLoader reference:
 * for example, for class path resource loading (but not necessarily for
 * {@code Class.forName}, which accepts a {@code null} ClassLoader
 * reference as well).
 * @return the default ClassLoader (only {@code null} if even the system
 * ClassLoader isn't accessible)
 * @see Thread#getContextClassLoader()
 * @see ClassLoader#getSystemClassLoader()
 */
ClassUtil.getDefaultClassLoader();
```

## overrideThreadContextClassLoader
```java
/**
 * Override the thread context ClassLoader with the environment's bean ClassLoader
 * if necessary, i.e. if the bean ClassLoader is not equivalent to the thread
 * context ClassLoader already.
 * @param classLoaderToUse the actual ClassLoader to use for the thread context
 * @return the original thread context ClassLoader, or {@code null} if not overridden
 */
ClassUtil.overrideThreadContextClassLoader(ClassLoader classLoaderToUse);
```

## forName
```java
/**
 * Replacement for {@code Class.forName()} that also returns Class instances
 * for primitives (e.g. "int") and array class names (e.g. "String[]").
 * Furthermore, it is also capable of resolving inner class names in Java source
 * style (e.g. "java.lang.Thread.State" instead of "java.lang.Thread$State").
 * @param name the name of the Class
 * @param classLoader the class loader to use
 * (may be {@code null}, which indicates the default class loader)
 * @return a class instance for the supplied name
 * @throws ClassNotFoundException if the class was not found
 * @throws LinkageError if the class file could not be loaded
 * @see Class#forName(String, boolean, ClassLoader)
 */
ClassUtil.forName(String name, ClassLoader classLoader);
```

## resolveClassName
```java
/**
 * Resolve the given class name into a Class instance. Supports
 * primitives (like "int") and array class names (like "String[]").
 * <p>This is effectively equivalent to the {@code forName}
 * method with the same arguments, with the only difference being
 * the exceptions thrown in case of class loading failure.
 * @param className the name of the Class
 * @param classLoader the class loader to use
 * (may be {@code null}, which indicates the default class loader)
 * @return a class instance for the supplied name
 * @throws IllegalArgumentException if the class name was not resolvable
 * (that is, the class could not be found or the class file could not be loaded)
 * @throws IllegalStateException if the corresponding class is resolvable but
 * there was a readability mismatch in the inheritance hierarchy of the class
 * (typically a missing dependency declaration in a Jigsaw module definition
 * for a superclass or interface implemented by the class to be loaded here)
 * @see #forName(String, ClassLoader)
 */
ClassUtil.resolveClassName(String className, ClassLoader classLoader);
```

## isPresent
```java
/**
 * Determine whether the {@link Class} identified by the supplied name is present
 * and can be loaded. Will return {@code false} if either the class or
 * one of its dependencies is not present or cannot be loaded.
 * @param className the name of the class to check
 * @param classLoader the class loader to use
 * (may be {@code null} which indicates the default class loader)
 * @return whether the specified class is present (including all of its
 * superclasses and interfaces)
 * @throws IllegalStateException if the corresponding class is resolvable but
 * there was a readability mismatch in the inheritance hierarchy of the class
 * (typically a missing dependency declaration in a Jigsaw module definition
 * for a superclass or interface implemented by the class to be checked here)
 */
ClassUtil.isPresent(String className, ClassLoader classLoader);
```

## isVisible
```java
/**
 * Check whether the given class is visible in the given ClassLoader.
 * @param clazz the class to check (typically an interface)
 * @param classLoader the ClassLoader to check against
 * (may be {@code null} in which case this method will always return {@code true})
 */
ClassUtil.isVisible(Class<?> clazz, ClassLoader classLoader);
```

## isCacheSafe
```java
/**
 * Check whether the given class is cache-safe in the given context,
 * i.e. whether it is loaded by the given ClassLoader or a parent of it.
 * @param clazz the class to analyze
 * @param classLoader the ClassLoader to potentially cache metadata in
 * (may be {@code null} which indicates the system class loader)
 */
ClassUtil.isCacheSafe(Class<?> clazz, ClassLoader classLoader);
```

## resolvePrimitiveClassName
```java
/**
 * Resolve the given class name as primitive class, if appropriate,
 * according to the JVM's naming rules for primitive classes.
 * <p>Also supports the JVM's internal class names for primitive arrays.
 * Does <i>not</i> support the "[]" suffix notation for primitive arrays;
 * this is only supported by {@link #forName(String, ClassLoader)}.
 * @param name the name of the potentially primitive class
 * @return the primitive class, or {@code null} if the name does not denote
 * a primitive class or primitive array class
 */
ClassUtil.resolvePrimitiveClassName(String name);
```

## isPrimitiveWrapper
```java
/**
 * Check if the given class represents a primitive wrapper,
 * i.e. Boolean, Byte, Character, Short, Integer, Long, Float, Double, or
 * Void.
 * @param clazz the class to check
 * @return whether the given class is a primitive wrapper class
 */
ClassUtil.isPrimitiveWrapper(Class<?> clazz);
```

## isPrimitiveOrWrapper
```java
/**
 * Check if the given class represents a primitive (i.e. boolean, byte,
 * char, short, int, long, float, or double), {@code void}, or a wrapper for
 * those types (i.e. Boolean, Byte, Character, Short, Integer, Long, Float,
 * Double, or Void).
 * @param clazz the class to check
 * @return {@code true} if the given class represents a primitive, void, or
 * a wrapper class
 */
ClassUtil.isPrimitiveOrWrapper(Class<?> clazz);
```

## isPrimitiveArray
```java
/**
 * Check if the given class represents an array of primitives,
 * i.e. boolean, byte, char, short, int, long, float, or double.
 * @param clazz the class to check
 * @return whether the given class is a primitive array class
 */
ClassUtil.isPrimitiveArray(Class<?> clazz);
```

## isPrimitiveWrapperArray
```java
/**
 * Check if the given class represents an array of primitive wrappers,
 * i.e. Boolean, Byte, Character, Short, Integer, Long, Float, or Double.
 * @param clazz the class to check
 * @return whether the given class is a primitive wrapper array class
 */
ClassUtil.isPrimitiveWrapperArray(Class<?> clazz);
```

## resolvePrimitiveIfNecessary
```java
/**
 * Resolve the given class if it is a primitive class,
 * returning the corresponding primitive wrapper type instead.
 * @param clazz the class to check
 * @return the original class, or a primitive wrapper for the original primitive type
 */
ClassUtil.resolvePrimitiveIfNecessary(Class<?> clazz);
```

## isAssignable
```java
/**
 * Check if the right-hand side type may be assigned to the left-hand side
 * type, assuming setting by reflection. Considers primitive wrapper
 * classes as assignable to the corresponding primitive types.
 * @param lhsType the target type
 * @param rhsType the value type that should be assigned to the target type
 * @return if the target type is assignable from the value type
 * @see TypeUtils#isAssignable(java.lang.reflect.Type, java.lang.reflect.Type)
 */
ClassUtil.isAssignable(Class<?> lhsType, Class<?> rhsType);
```

## isAssignableValue
```java
/**
 * Determine if the given type is assignable from the given value,
 * assuming setting by reflection. Considers primitive wrapper classes
 * as assignable to the corresponding primitive types.
 * @param type the target type
 * @param value the value that should be assigned to the type
 * @return if the type is assignable from the value
 */
ClassUtil.isAssignableValue(Class<?> type, Object value);
```

## convertResourcePathToClassName
```java
/**
 * Convert a "/"-based resource path to a "."-based fully qualified class name.
 * @param resourcePath the resource path pointing to a class
 * @return the corresponding fully qualified class name
 */
ClassUtil.convertResourcePathToClassName(String resourcePath);
```

## convertClassNameToResourcePath
```java
/**
 * Convert a "."-based fully qualified class name to a "/"-based resource path.
 * @param className the fully qualified class name
 * @return the corresponding resource path, pointing to the class
 */
ClassUtil.convertClassNameToResourcePath(String className);
```

## addResourcePathToPackagePath
```java
/**
 * Return a path suitable for use with {@code ClassLoader.getResource}
 * (also suitable for use with {@code Class.getResource} by prepending a
 * slash ('/') to the return value). Built by taking the package of the specified
 * class file, converting all dots ('.') to slashes ('/'), adding a trailing slash
 * if necessary, and concatenating the specified resource name to this.
 * <br/>As such, this function may be used to build a path suitable for
 * loading a resource file that is in the same package as a class file,
 * although {@link org.springframework.core.io.ClassPathResource} is usually
 * even more convenient.
 * @param clazz the Class whose package will be used as the base
 * @param resourceName the resource name to append. A leading slash is optional.
 * @return the built-up resource path
 * @see ClassLoader#getResource
 * @see Class#getResource
 */
ClassUtil.addResourcePathToPackagePath(Class<?> clazz, String resourceName);
```

## classPackageAsResourcePath
```java
/**
 * Given an input class object, return a string which consists of the
 * class's package name as a pathname, i.e., all dots ('.') are replaced by
 * slashes ('/'). Neither a leading nor trailing slash is added. The result
 * could be concatenated with a slash and the name of a resource and fed
 * directly to {@code ClassLoader.getResource()}. For it to be fed to
 * {@code Class.getResource} instead, a leading slash would also have
 * to be prepended to the returned value.
 * @param clazz the input class. A {@code null} value or the default
 * (empty) package will result in an empty string ("") being returned.
 * @return a path which represents the package name
 * @see ClassLoader#getResource
 * @see Class#getResource
 */
ClassUtil.classPackageAsResourcePath(Class<?> clazz);
```

## classNamesToString
```java
/**
 * Build a String that consists of the names of the classes/interfaces
 * in the given array.
 * <p>Basically like {@code AbstractCollection.toString()}, but stripping
 * the "class "/"interface " prefix before every class name.
 * @param classes an array of Class objects
 * @return a String of form "[com.foo.Bar, com.foo.Baz]"
 * @see java.util.AbstractCollection#toString()
 */
ClassUtil.classNamesToString(Class<?> classes);
```

## classNamesToString
```java
/**
 * Build a String that consists of the names of the classes/interfaces
 * in the given collection.
 * <p>Basically like {@code AbstractCollection.toString()}, but stripping
 * the "class "/"interface " prefix before every class name.
 * @param classes a Collection of Class objects (may be {@code null})
 * @return a String of form "[com.foo.Bar, com.foo.Baz]"
 * @see java.util.AbstractCollection#toString()
 */
ClassUtil.classNamesToString(Collection<Class<?>> classes);
```

## toClassArray
```java
/**
 * Copy the given {@code Collection} into a {@code Class} array.
 * <p>The {@code Collection} must contain {@code Class} elements only.
 * @param collection the {@code Collection} to copy
 * @return the {@code Class} array
 * @since 3.1
 * @see StringUtils#toStringArray
 */
ClassUtil.toClassArray(Collection<Class<?>> collection);
```

## getAllInterfaces
```java
/**
 * Return all interfaces that the given instance implements as an array,
 * including ones implemented by superclasses.
 * @param instance the instance to analyze for interfaces
 * @return all interfaces that the given instance implements as an array
 */
ClassUtil.getAllInterfaces(Object instance);
```

## getAllInterfacesForClass
```java
/**
 * Return all interfaces that the given class implements as an array,
 * including ones implemented by superclasses.
 * <p>If the class itself is an interface, it gets returned as sole interface.
 * @param clazz the class to analyze for interfaces
 * @return all interfaces that the given object implements as an array
 */
ClassUtil.getAllInterfacesForClass(Class<?> clazz);
```

## getAllInterfacesForClass
```java
/**
 * Return all interfaces that the given class implements as an array,
 * including ones implemented by superclasses.
 * <p>If the class itself is an interface, it gets returned as sole interface.
 * @param clazz the class to analyze for interfaces
 * @param classLoader the ClassLoader that the interfaces need to be visible in
 * (may be {@code null} when accepting all declared interfaces)
 * @return all interfaces that the given object implements as an array
 */
ClassUtil.getAllInterfacesForClass(Class<?> clazz, ClassLoader classLoader);
```

## getAllInterfacesAsSet
```java
/**
 * Return all interfaces that the given instance implements as a Set,
 * including ones implemented by superclasses.
 * @param instance the instance to analyze for interfaces
 * @return all interfaces that the given instance implements as a Set
 */
ClassUtil.getAllInterfacesAsSet(Object instance);
```

## getAllInterfacesForClassAsSet
```java
/**
 * Return all interfaces that the given class implements as a Set,
 * including ones implemented by superclasses.
 * <p>If the class itself is an interface, it gets returned as sole interface.
 * @param clazz the class to analyze for interfaces
 * @return all interfaces that the given object implements as a Set
 */
ClassUtil.getAllInterfacesForClassAsSet(Class<?> clazz);
```

## getAllInterfacesForClassAsSet
```java
/**
 * Return all interfaces that the given class implements as a Set,
 * including ones implemented by superclasses.
 * <p>If the class itself is an interface, it gets returned as sole interface.
 * @param clazz the class to analyze for interfaces
 * @param classLoader the ClassLoader that the interfaces need to be visible in
 * (may be {@code null} when accepting all declared interfaces)
 * @return all interfaces that the given object implements as a Set
 */
ClassUtil.getAllInterfacesForClassAsSet(Class<?> clazz, ClassLoader classLoader);
```

## createCompositeInterface
```java
/**
 * Create a composite interface Class for the given interfaces,
 * implementing the given interfaces in one single Class.
 * <p>This implementation builds a JDK proxy class for the given interfaces.
 * @param interfaces the interfaces to merge
 * @param classLoader the ClassLoader to create the composite Class in
 * @return the merged interface as Class
 * @throws IllegalArgumentException if the specified interfaces expose
 * conflicting method signatures (or a similar constraint is violated)
 * @see java.lang.reflect.Proxy#getProxyClass
 */
ClassUtil.createCompositeInterface(Class<?>[] interfaces, ClassLoader classLoader);
```

## determineCommonAncestor
```java
/**
 * Determine the common ancestor of the given classes, if any.
 * @param clazz1 the class to introspect
 * @param clazz2 the other class to introspect
 * @return the common ancestor (i.e. common superclass, one interface
 * extending the other), or {@code null} if none found. If any of the
 * given classes is {@code null}, the other class will be returned.
 * @since 3.2.6
 */
ClassUtil.determineCommonAncestor(Class<?> clazz1, Class<?> clazz2);
```

## isJavaLanguageInterface
```java
/**
 * Determine whether the given interface is a common Java language interface:
 * {@link Serializable}, {@link Externalizable}, {@link Closeable}, {@link AutoCloseable},
 * {@link Cloneable}, {@link Comparable} - all of which can be ignored when looking
 * for 'primary' user-level interfaces. Common characteristics: no service-level
 * operations, no bean property methods, no default methods.
 * @param ifc the interface to check
 * @since 5.0.3
 */
ClassUtil.isJavaLanguageInterface(Class<?> ifc);
```

## isInnerClass
```java
/**
 * Determine if the supplied class is an <em>inner class</em>,
 * i.e. a non-static member of an enclosing class.
 * @return {@code true} if the supplied class is an inner class
 * @since 5.0.5
 * @see Class#isMemberClass()
 */
ClassUtil.isInnerClass(Class<?> clazz);
```

## isCglibProxy
```java
/**
 * Check whether the given object is a CGLIB proxy.
 * @param object the object to check
 * @see #isCglibProxyClass(Class)
 * @see org.springframework.aop.support.AopUtils#isCglibProxy(Object)
 */
ClassUtil.isCglibProxy(Object object);
```

## isCglibProxyClass
```java
/**
 * Check whether the specified class is a CGLIB-generated class.
 * @param clazz the class to check
 * @see #isCglibProxyClassName(String)
 */
ClassUtil.isCglibProxyClass(Class<?> clazz);
```

## isCglibProxyClassName
```java
/**
 * Check whether the specified class name is a CGLIB-generated class.
 * @param className the class name to check
 */
ClassUtil.isCglibProxyClassName(String className);
```

## getUserClass
```java
/**
 * Return the user-defined class for the given instance: usually simply
 * the class of the given instance, but the original class in case of a
 * CGLIB-generated subclass.
 * @param instance the instance to check
 * @return the user-defined class
 */
ClassUtil.getUserClass(Object instance);
```

## getUserClass
```java
/**
 * Return the user-defined class for the given class: usually simply the given
 * class, but the original class in case of a CGLIB-generated subclass.
 * @param clazz the class to check
 * @return the user-defined class
 */
ClassUtil.getUserClass(Class<?> clazz);
```

## getDescriptiveType
```java
/**
 * Return a descriptive name for the given object's type: usually simply
 * the class name, but component type class name + "[]" for arrays,
 * and an appended list of implemented interfaces for JDK proxies.
 * @param value the value to introspect
 * @return the qualified name of the class
 */
ClassUtil.getDescriptiveType(Object value);
```

## matchesTypeName
```java
/**
 * Check whether the given class matches the user-specified type name.
 * @param clazz the class to check
 * @param typeName the type name to match
 */
ClassUtil.matchesTypeName(Class<?> clazz, String typeName);
```

## getShortName
```java
/**
 * Get the class name without the qualified package name.
 * @param className the className to get the short name for
 * @return the class name of the class without the package name
 * @throws IllegalArgumentException if the className is empty
 */
ClassUtil.getShortName(String className);
```

## getShortName
```java
/**
 * Get the class name without the qualified package name.
 * @param clazz the class to get the short name for
 * @return the class name of the class without the package name
 */
ClassUtil.getShortName(Class<?> clazz);
```

## getShortNameAsProperty
```java
/**
 * Return the short string name of a Java class in uncapitalized JavaBeans
 * property format. Strips the outer class name in case of an inner class.
 * @param clazz the class
 * @return the short name rendered in a standard JavaBeans property format
 * @see java.beans.Introspector#decapitalize(String)
 */
ClassUtil.getShortNameAsProperty(Class<?> clazz);
```

## getClassFileName
```java
/**
 * Determine the name of the class file, relative to the containing
 * package: e.g. "String.class"
 * @param clazz the class
 * @return the file name of the ".class" file
 */
ClassUtil.getClassFileName(Class<?> clazz);
```

## getPackageName
```java
/**
 * Determine the name of the package of the given class,
 * e.g. "java.lang" for the {@code java.lang.String} class.
 * @param clazz the class
 * @return the package name, or the empty String if the class
 * is defined in the default package
 */
ClassUtil.getPackageName(Class<?> clazz);
```

## getPackageName
```java
/**
 * Determine the name of the package of the given fully-qualified class name,
 * e.g. "java.lang" for the {@code java.lang.String} class name.
 * @param fqClassName the fully-qualified class name
 * @return the package name, or the empty String if the class
 * is defined in the default package
 */
ClassUtil.getPackageName(String fqClassName);
```

## getQualifiedName
```java
/**
 * Return the qualified name of the given class: usually simply
 * the class name, but component type class name + "[]" for arrays.
 * @param clazz the class
 * @return the qualified name of the class
 */
ClassUtil.getQualifiedName(Class<?> clazz);
```

## getQualifiedMethodName
```java
/**
 * Return the qualified name of the given method, consisting of
 * fully qualified interface/class name + "." + method name.
 * @param method the method
 * @return the qualified name of the method
 */
ClassUtil.getQualifiedMethodName(Method method);
```

## getQualifiedMethodName
```java
/**
 * Return the qualified name of the given method, consisting of
 * fully qualified interface/class name + "." + method name.
 * @param method the method
 * @param clazz the clazz that the method is being invoked on
 * (may be {@code null} to indicate the method's declaring class)
 * @return the qualified name of the method
 * @since 4.3.4
 */
ClassUtil.getQualifiedMethodName(Method method, Class<?> clazz);
```

## hasConstructor
```java
/**
 * Determine whether the given class has a public constructor with the given signature.
 * <p>Essentially translates {@code NoSuchMethodException} to "false".
 * @param clazz the clazz to analyze
 * @param paramTypes the parameter types of the method
 * @return whether the class has a corresponding constructor
 * @see Class#getConstructor
 */
ClassUtil.hasConstructor(Class<?> clazz, Class<?> paramTypes);
```

## getConstructorIfAvailable
```java
/**
 * Determine whether the given class has a public constructor with the given signature,
 * and return it if available (else return {@code null}).
 * <p>Essentially translates {@code NoSuchMethodException} to {@code null}.
 * @param clazz the clazz to analyze
 * @param paramTypes the parameter types of the method
 * @return the constructor, or {@code null} if not found
 * @see Class#getConstructor
 */
ClassUtil.getConstructorIfAvailable(Class<T> clazz, Class<?> paramTypes);
```

## hasMethod
```java
/**
 * Determine whether the given class has a public method with the given signature.
 * <p>Essentially translates {@code NoSuchMethodException} to "false".
 * @param clazz the clazz to analyze
 * @param methodName the name of the method
 * @param paramTypes the parameter types of the method
 * @return whether the class has a corresponding method
 * @see Class#getMethod
 */
ClassUtil.hasMethod(Class<?> clazz, String methodName, Class<?> paramTypes);
```

## getMethod
```java
/**
 * Determine whether the given class has a public method with the given signature,
 * and return it if available (else throws an {@code IllegalStateException}).
 * <p>In case of any signature specified, only returns the method if there is a
 * unique candidate, i.e. a single public method with the specified name.
 * <p>Essentially translates {@code NoSuchMethodException} to {@code IllegalStateException}.
 * @param clazz the clazz to analyze
 * @param methodName the name of the method
 * @param paramTypes the parameter types of the method
 * (may be {@code null} to indicate any signature)
 * @return the method (never {@code null})
 * @throws IllegalStateException if the method has not been found
 * @see Class#getMethod
 */
ClassUtil.getMethod(Class<?> clazz, String methodName, Class<?> paramTypes);
```

## getMethodIfAvailable
```java
/**
 * Determine whether the given class has a public method with the given signature,
 * and return it if available (else return {@code null}).
 * <p>In case of any signature specified, only returns the method if there is a
 * unique candidate, i.e. a single public method with the specified name.
 * <p>Essentially translates {@code NoSuchMethodException} to {@code null}.
 * @param clazz the clazz to analyze
 * @param methodName the name of the method
 * @param paramTypes the parameter types of the method
 * (may be {@code null} to indicate any signature)
 * @return the method, or {@code null} if not found
 * @see Class#getMethod
 */
ClassUtil.getMethodIfAvailable(Class<?> clazz, String methodName, Class<?> paramTypes);
```

## getMethodCountForName
```java
/**
 * Return the number of methods with a given name (with any argument types),
 * for the given class and/or its superclasses. Includes non-public methods.
 * @param clazz	the clazz to check
 * @param methodName the name of the method
 * @return the number of methods with the given name
 */
ClassUtil.getMethodCountForName(Class<?> clazz, String methodName);
```

## hasAtLeastOneMethodWithName
```java
/**
 * Does the given class or one of its superclasses at least have one or more
 * methods with the supplied name (with any argument types)?
 * Includes non-public methods.
 * @param clazz	the clazz to check
 * @param methodName the name of the method
 * @return whether there is at least one method with the given name
 */
ClassUtil.hasAtLeastOneMethodWithName(Class<?> clazz, String methodName);
```

## getMostSpecificMethod
```java
/**
 * Given a method, which may come from an interface, and a target class used
 * in the current reflective invocation, find the corresponding target method
 * if there is one. E.g. the method may be {@code IFoo.bar()} and the
 * target class may be {@code DefaultFoo}. In this case, the method may be
 * {@code DefaultFoo.bar()}. This enables attributes on that method to be found.
 * <p><b>NOTE:</b> In contrast to {@link org.springframework.aop.support.AopUtils#getMostSpecificMethod},
 * this method does <i>not</i> resolve Java 5 bridge methods automatically.
 * Call {@link org.springframework.core.BridgeMethodResolver#findBridgedMethod}
 * if bridge method resolution is desirable (e.g. for obtaining metadata from
 * the original method definition).
 * <p><b>NOTE:</b> Since Spring 3.1.1, if Java security settings disallow reflective
 * access (e.g. calls to {@code Class#getDeclaredMethods} etc, this implementation
 * will fall back to returning the originally provided method.
 * @param method the method to be invoked, which may come from an interface
 * @param targetClass the target class for the current invocation
 * (may be {@code null} or may not even implement the method)
 * @return the specific target method, or the original method if the
 * {@code targetClass} does not implement it
 * @see #getInterfaceMethodIfPossible
 */
ClassUtil.getMostSpecificMethod(Method method, Class<?> targetClass);
```

## getInterfaceMethodIfPossible
```java
/**
 * Determine a corresponding interface method for the given method handle, if possible.
 * <p>This is particularly useful for arriving at a public exported type on Jigsaw
 * which can be reflectively invoked without an illegal access warning.
 * @param method the method to be invoked, potentially from an implementation class
 * @return the corresponding interface method, or the original method if none found
 * @since 5.1
 * @see #getMostSpecificMethod
 */
ClassUtil.getInterfaceMethodIfPossible(Method method);
```

## isUserLevelMethod
```java
/**
 * Determine whether the given method is declared by the user or at least pointing to
 * a user-declared method.
 * <p>Checks {@link Method#isSynthetic()} (for implementation methods) as well as the
 * {@code GroovyObject} interface (for interface methods; on an implementation class,
 * implementations of the {@code GroovyObject} methods will be marked as synthetic anyway).
 * Note that, despite being synthetic, bridge methods ({@link Method#isBridge()}) are considered
 * as user-level methods since they are eventually pointing to a user-declared generic method.
 * @param method the method to check
 * @return {@code true} if the method can be considered as user-declared; [@code false} otherwise
 */
ClassUtil.isUserLevelMethod(Method method);
```

## getStaticMethod
```java
/**
 * Return a public static method of a class.
 * @param clazz the class which defines the method
 * @param methodName the static method name
 * @param args the parameter types to the method
 * @return the static method, or {@code null} if no static method was found
 * @throws IllegalArgumentException if the method name is blank or the clazz is null
 */
ClassUtil.getStaticMethod(Class<?> clazz, String methodName, Class<?> args);
```

