#  对象工具类
**类名：** `ObjectUtil`

## isNotEmpty
```java
/**
 * 判断元素不为空
 * @param obj object
 * @return boolean
 */
ObjectUtil.isNotEmpty(Object obj);
```

## isCheckedException
```java
/**
 * Return whether the given throwable is a checked exception:
 * that is, neither a RuntimeException nor an Error.
 * @param ex the throwable to check
 * @return whether the throwable is a checked exception
 * @see java.lang.Exception
 * @see java.lang.RuntimeException
 * @see java.lang.Error
 */
ObjectUtil.isCheckedException(Throwable ex);
```

## isCompatibleWithThrowsClause
```java
/**
 * Check whether the given exception is compatible with the specified
 * exception types, as declared in a throws clause.
 * @param ex the exception to check
 * @param declaredExceptions the exception types declared in the throws clause
 * @return whether the given exception is compatible
 */
ObjectUtil.isCompatibleWithThrowsClause(Throwable ex, Class<?> declaredExceptions);
```

## isArray
```java
/**
 * Determine whether the given object is an array:
 * either an Object array or a primitive array.
 * @param obj the object to check
 */
ObjectUtil.isArray(Object obj);
```

## isEmpty
```java
/**
 * Determine whether the given array is empty:
 * i.e. {@code null} or of zero length.
 * @param array the array to check
 * @see #isEmpty(Object)
 */
ObjectUtil.isEmpty(Object[] array);
```

## isEmpty
```java
/**
 * Determine whether the given object is empty.
 * <p>This method supports the following object types.
 * <ul>
 * <li>{@code Optional}: considered empty if {@link Optional#empty()}</li>
 * <li>{@code Array}: considered empty if its length is zero</li>
 * <li>{@link CharSequence}: considered empty if its length is zero</li>
 * <li>{@link Collection}: delegates to {@link Collection#isEmpty()}</li>
 * <li>{@link Map}: delegates to {@link Map#isEmpty()}</li>
 * </ul>
 * <p>If the given object is non-null and not one of the aforementioned
 * supported types, this method returns {@code false}.
 * @param obj the object to check
 * @return {@code true} if the object is {@code null} or <em>empty</em>
 * @since 4.2
 * @see Optional#isPresent()
 * @see ObjectUtils#isEmpty(Object[])
 * @see StringUtils#hasLength(CharSequence)
 * @see StringUtils#isEmpty(Object)
 * @see CollectionUtils#isEmpty(java.util.Collection)
 * @see CollectionUtils#isEmpty(java.util.Map)
 */
ObjectUtil.isEmpty(Object obj);
```

## unwrapOptional
```java
/**
 * Unwrap the given object which is potentially a {@link java.util.Optional}.
 * @param obj the candidate object
 * @return either the value held within the {@code Optional}, {@code null}
 * if the {@code Optional} is empty, or simply the given object as-is
 * @since 5.0
 */
ObjectUtil.unwrapOptional(Object obj);
```

## containsElement
```java
/**
 * Check whether the given array contains the given element.
 * @param array the array to check (may be {@code null},
 * in which case the return value will always be {@code false})
 * @param element the element to check for
 * @return whether the element has been found in the given array
 */
ObjectUtil.containsElement(Object[] array, Object element);
```

## containsConstant
```java
/**
 * Check whether the given array of enum constants contains a constant with the given name,
 * ignoring case when determining a match.
 * @param enumValues the enum values to check, typically obtained via {@code MyEnum.values()}
 * @param constant the constant name to find (must not be null or empty string)
 * @return whether the constant has been found in the given array
 */
ObjectUtil.containsConstant(Enum<?>[] enumValues, String constant);
```

## containsConstant
```java
/**
 * Check whether the given array of enum constants contains a constant with the given name.
 * @param enumValues the enum values to check, typically obtained via {@code MyEnum.values()}
 * @param constant the constant name to find (must not be null or empty string)
 * @param caseSensitive whether case is significant in determining a match
 * @return whether the constant has been found in the given array
 */
ObjectUtil.containsConstant(Enum<?>[] enumValues, String constant, boolean caseSensitive);
```

## caseInsensitiveValueOf
```java
/**
 * Case insensitive alternative to {@link Enum#valueOf(Class, String)}.
 * @param <E> the concrete Enum type
 * @param enumValues the array of all Enum constants in question, usually per {@code Enum.values()}
 * @param constant the constant to get the enum value of
 * @throws IllegalArgumentException if the given constant is not found in the given array
 * of enum values. Use {@link #containsConstant(Enum[], String)} as a guard to avoid this exception.
 */
ObjectUtil.caseInsensitiveValueOf(E[] enumValues, String constant);
```

## addObjectToArray
```java
/**
 * Append the given object to the given array, returning a new array
 * consisting of the input array contents plus the given object.
 * @param array the array to append to (can be {@code null})
 * @param obj the object to append
 * @return the new array (of the same component type; never {@code null})
 */
ObjectUtil.addObjectToArray(A[] array, O obj);
```

## toObjectArray
```java
/**
 * Convert the given array (which may be a primitive array) to an
 * object array (if necessary of primitive wrapper objects).
 * <p>A {@code null} source value will be converted to an
 * empty Object array.
 * @param source the (potentially primitive) array
 * @return the corresponding object array (never {@code null})
 * @throws IllegalArgumentException if the parameter is not an array
 */
ObjectUtil.toObjectArray(Object source);
```

## nullSafeEquals
```java
/**
 * Determine if the given objects are equal, returning {@code true} if
 * both are {@code null} or {@code false} if only one is {@code null}.
 * <p>Compares arrays with {@code Arrays.equals}, performing an equality
 * check based on the array elements rather than the array reference.
 * @param o1 first Object to compare
 * @param o2 second Object to compare
 * @return whether the given objects are equal
 * @see Object#equals(Object)
 * @see java.util.Arrays#equals
 */
ObjectUtil.nullSafeEquals(Object o1, Object o2);
```

## nullSafeHashCode
```java
/**
 * Return as hash code for the given object; typically the value of
 * {@code Object#hashCode()}}. If the object is an array,
 * this method will delegate to any of the {@code nullSafeHashCode}
 * methods for arrays in this class. If the object is {@code null},
 * this method returns 0.
 * @see Object#hashCode()
 * @see #nullSafeHashCode(Object[])
 * @see #nullSafeHashCode(boolean[])
 * @see #nullSafeHashCode(byte[])
 * @see #nullSafeHashCode(char[])
 * @see #nullSafeHashCode(double[])
 * @see #nullSafeHashCode(float[])
 * @see #nullSafeHashCode(int[])
 * @see #nullSafeHashCode(long[])
 * @see #nullSafeHashCode(short[])
 */
ObjectUtil.nullSafeHashCode(Object obj);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(Object[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(boolean[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(byte[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(char[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(double[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(float[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(int[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(long[] array);
```

## nullSafeHashCode
```java
/**
 * Return a hash code based on the contents of the specified array.
 * If {@code array} is {@code null}, this method returns 0.
 */
ObjectUtil.nullSafeHashCode(short[] array);
```

## hashCode
```java
/**
 * Return the same value as {@link Boolean#hashCode(boolean)}}.
 * @deprecated as of Spring Framework 5.0, in favor of the native JDK 8 variant
 */
ObjectUtil.hashCode(boolean bool);
```

## hashCode
```java
/**
 * Return the same value as {@link Double#hashCode(double)}}.
 * @deprecated as of Spring Framework 5.0, in favor of the native JDK 8 variant
 */
ObjectUtil.hashCode(double dbl);
```

## hashCode
```java
/**
 * Return the same value as {@link Float#hashCode(float)}}.
 * @deprecated as of Spring Framework 5.0, in favor of the native JDK 8 variant
 */
ObjectUtil.hashCode(float flt);
```

## hashCode
```java
/**
 * Return the same value as {@link Long#hashCode(long)}}.
 * @deprecated as of Spring Framework 5.0, in favor of the native JDK 8 variant
 */
ObjectUtil.hashCode(long lng);
```

## identityToString
```java
/**
 * Return a String representation of an object's overall identity.
 * @param obj the object (may be {@code null})
 * @return the object's identity as String representation,
 * or an empty String if the object was {@code null}
 */
ObjectUtil.identityToString(Object obj);
```

## getIdentityHexString
```java
/**
 * Return a hex String form of an object's identity hash code.
 * @param obj the object
 * @return the object's identity code in hex notation
 */
ObjectUtil.getIdentityHexString(Object obj);
```

## getDisplayString
```java
/**
 * Return a content-based String representation if {@code obj} is
 * not {@code null}; otherwise returns an empty String.
 * <p>Differs from {@link #nullSafeToString(Object)} in that it returns
 * an empty String rather than "null" for a {@code null} value.
 * @param obj the object to build a display String for
 * @return a display String representation of {@code obj}
 * @see #nullSafeToString(Object)
 */
ObjectUtil.getDisplayString(Object obj);
```

## nullSafeClassName
```java
/**
 * Determine the class name for the given object.
 * <p>Returns a {@code "null"} String if {@code obj} is {@code null}.
 * @param obj the object to introspect (may be {@code null})
 * @return the corresponding class name
 */
ObjectUtil.nullSafeClassName(Object obj);
```

## nullSafeToString
```java
/**
 * Return a String representation of the specified Object.
 * <p>Builds a String representation of the contents in case of an array.
 * Returns a {@code "null"} String if {@code obj} is {@code null}.
 * @param obj the object to build a String representation for
 * @return a String representation of {@code obj}
 */
ObjectUtil.nullSafeToString(Object obj);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(Object[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(boolean[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(byte[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(char[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(double[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(float[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(int[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(long[] array);
```

## nullSafeToString
```java
/**
 * Return a String representation of the contents of the specified array.
 * <p>The String representation consists of a list of the array's elements,
 * enclosed in curly braces ({@code "{}"}). Adjacent elements are separated
 * by the characters {@code ", "} (a comma followed by a space).
 * Returns a {@code "null"} String if {@code array} is {@code null}.
 * @param array the array to build a String representation for
 * @return a String representation of {@code array}
 */
ObjectUtil.nullSafeToString(short[] array);
```

