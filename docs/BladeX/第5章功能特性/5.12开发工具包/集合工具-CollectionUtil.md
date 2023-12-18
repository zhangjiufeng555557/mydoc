#  集合工具类
**类名：** `CollectionUtil`

## isNotEmpty
```java
/**
 * Return {@code true} if the supplied Collection is not {@code null} or empty.
 * Otherwise, return {@code false}.
 *
 * @param collection the Collection to check
 * @return whether the given Collection is not empty
 */
CollectionUtil.isNotEmpty(Collection<?> collection);
```

## isNotEmpty
```java
/**
 * Return {@code true} if the supplied Map is not {@code null} or empty.
 * Otherwise, return {@code false}.
 *
 * @param map the Map to check
 * @return whether the given Map is not empty
 */
CollectionUtil.isNotEmpty(Map<?,?> map);
```

## contains
```java
/**
 * Check whether the given Array contains the given element.
 *
 * @param array   the Array to check
 * @param element the element to look for
 * @param <T>     The generic tag
 * @return {@code true} if found, {@code false} else
 */
CollectionUtil.contains(T[] array, T element);
```

## concat
```java
/**
 * Concatenates 2 arrays
 *
 * @param one   数组1
 * @param other 数组2
 * @return 新数组
 */
CollectionUtil.concat(String[] one, String[] other);
```

## concat
```java
/**
 * Concatenates 2 arrays
 *
 * @param one   数组1
 * @param other 数组2
 * @param clazz 数组类
 * @return 新数组
 */
CollectionUtil.concat(T[] one, T[] other, Class<T> clazz);
```

## isArray
```java
/**
 * 对象是否为数组对象
 *
 * @param obj 对象
 * @return 是否为数组对象，如果为{@code null} 返回false
 */
CollectionUtil.isArray(Object obj);
```

## ofImmutableSet
```java
/**
 * 不可变 Set
 *
 * @param es  对象
 * @param <E> 泛型
 * @return 集合
 */
CollectionUtil.ofImmutableSet(E es);
```

## ofImmutableList
```java
/**
 * 不可变 List
 *
 * @param es  对象
 * @param <E> 泛型
 * @return 集合
 */
CollectionUtil.ofImmutableList(E es);
```

## toList
```java
/**
 * Iterable 转换为List集合
 *
 * @param elements Iterable
 * @param <E>      泛型
 * @return 集合
 */
CollectionUtil.toList(Iterable<E> elements);
```

## toMap
```java
/**
 * 将key value 数组转为 map
 *
 * @param keysValues key value 数组
 * @param <K>        key
 * @param <V>        value
 * @return map 集合
 */
CollectionUtil.toMap(Object keysValues);
```

## isEmpty
```java
/**
 * Return {@code true} if the supplied Collection is {@code null} or empty.
 * Otherwise, return {@code false}.
 * @param collection the Collection to check
 * @return whether the given Collection is empty
 */
CollectionUtil.isEmpty(Collection<?> collection);
```

## isEmpty
```java
/**
 * Return {@code true} if the supplied Map is {@code null} or empty.
 * Otherwise, return {@code false}.
 * @param map the Map to check
 * @return whether the given Map is empty
 */
CollectionUtil.isEmpty(Map<?,?> map);
```

## arrayToList
```java
/**
 * Convert the supplied array into a List. A primitive array gets converted
 * into a List of the appropriate wrapper type.
 * <p><b>NOTE:</b> Generally prefer the standard {@link Arrays#asList} method.
 * This {@code arrayToList} method is just meant to deal with an incoming Object
 * value that might be an {@code Object[]} or a primitive array at runtime.
 * <p>A {@code null} source value will be converted to an empty List.
 * @param source the (potentially primitive) array
 * @return the converted List result
 * @see ObjectUtils#toObjectArray(Object)
 * @see Arrays#asList(Object[])
 */
CollectionUtil.arrayToList(Object source);
```

## mergeArrayIntoCollection
```java
/**
 * Merge the given array into the given Collection.
 * @param array the array to merge (may be {@code null})
 * @param collection the target Collection to merge the array into
 */
CollectionUtil.mergeArrayIntoCollection(Object array, Collection<E> collection);
```

## mergePropertiesIntoMap
```java
/**
 * Merge the given Properties instance into the given Map,
 * copying all properties (key-value pairs) over.
 * <p>Uses {@code Properties.propertyNames()} to even catch
 * default properties linked into the original Properties instance.
 * @param props the Properties instance to merge (may be {@code null})
 * @param map the target Map to merge the properties into
 */
CollectionUtil.mergePropertiesIntoMap(Properties props, Map<K,V> map);
```

## contains
```java
/**
 * Check whether the given Iterator contains the given element.
 * @param iterator the Iterator to check
 * @param element the element to look for
 * @return {@code true} if found, {@code false} otherwise
 */
CollectionUtil.contains(Iterator<?> iterator, Object element);
```

## contains
```java
/**
 * Check whether the given Enumeration contains the given element.
 * @param enumeration the Enumeration to check
 * @param element the element to look for
 * @return {@code true} if found, {@code false} otherwise
 */
CollectionUtil.contains(Enumeration<?> enumeration, Object element);
```

## containsInstance
```java
/**
 * Check whether the given Collection contains the given element instance.
 * <p>Enforces the given instance to be present, rather than returning
 * {@code true} for an equal element as well.
 * @param collection the Collection to check
 * @param element the element to look for
 * @return {@code true} if found, {@code false} otherwise
 */
CollectionUtil.containsInstance(Collection<?> collection, Object element);
```

## containsAny
```java
/**
 * Return {@code true} if any element in '{@code candidates}' is
 * contained in '{@code source}'; otherwise returns {@code false}.
 * @param source the source Collection
 * @param candidates the candidates to search for
 * @return whether any of the candidates has been found
 */
CollectionUtil.containsAny(Collection<?> source, Collection<?> candidates);
```

## findFirstMatch
```java
/**
 * Return the first element in '{@code candidates}' that is contained in
 * '{@code source}'. If no element in '{@code candidates}' is present in
 * '{@code source}' returns {@code null}. Iteration order is
 * {@link Collection} implementation specific.
 * @param source the source Collection
 * @param candidates the candidates to search for
 * @return the first present object, or {@code null} if not found
 */
CollectionUtil.findFirstMatch(Collection<?> source, Collection<E> candidates);
```

## findValueOfType
```java
/**
 * Find a single value of the given type in the given Collection.
 * @param collection the Collection to search
 * @param type the type to look for
 * @return a value of the given type found if there is a clear match,
 * or {@code null} if none or more than one such value found
 */
CollectionUtil.findValueOfType(Collection<?> collection, Class<T> type);
```

## findValueOfType
```java
/**
 * Find a single value of one of the given types in the given Collection:
 * searching the Collection for a value of the first type, then
 * searching for a value of the second type, etc.
 * @param collection the collection to search
 * @param types the types to look for, in prioritized order
 * @return a value of one of the given types found if there is a clear match,
 * or {@code null} if none or more than one such value found
 */
CollectionUtil.findValueOfType(Collection<?> collection, Class<?>[] types);
```

## hasUniqueObject
```java
/**
 * Determine whether the given Collection only contains a single unique object.
 * @param collection the Collection to check
 * @return {@code true} if the collection contains a single reference or
 * multiple references to the same instance, {@code false} otherwise
 */
CollectionUtil.hasUniqueObject(Collection<?> collection);
```

## findCommonElementType
```java
/**
 * Find the common element type of the given Collection, if any.
 * @param collection the Collection to check
 * @return the common element type, or {@code null} if no clear
 * common type has been found (or the collection was empty)
 */
CollectionUtil.findCommonElementType(Collection<?> collection);
```

## lastElement
```java
/**
 * Retrieve the last element of the given Set, using {@link SortedSet#last()}
 * or otherwise iterating over all elements (assuming a linked set).
 * @param set the Set to check (may be {@code null} or empty)
 * @return the last element, or {@code null} if none
 * @since 5.0.3
 * @see SortedSet
 * @see LinkedHashMap#keySet()
 * @see java.util.LinkedHashSet
 */
CollectionUtil.lastElement(Set<T> set);
```

## lastElement
```java
/**
 * Retrieve the last element of the given List, accessing the highest index.
 * @param list the List to check (may be {@code null} or empty)
 * @return the last element, or {@code null} if none
 * @since 5.0.3
 */
CollectionUtil.lastElement(List<T> list);
```

## toArray
```java
/**
 * Marshal the elements from the given enumeration into an array of the given type.
 * Enumeration elements must be assignable to the type of the given array. The array
 * returned will be a different instance than the array given.
 */
CollectionUtil.toArray(Enumeration<E> enumeration, A[] array);
```

## toIterator
```java
/**
 * Adapt an {@link Enumeration} to an {@link Iterator}.
 * @param enumeration the original {@code Enumeration}
 * @return the adapted {@code Iterator}
 */
CollectionUtil.toIterator(Enumeration<E> enumeration);
```

## toMultiValueMap
```java
/**
 * Adapt a {@code Map<K, List<V>>} to an {@code MultiValueMap<K, V>}.
 * @param map the original map
 * @return the multi-value map
 * @since 3.1
 */
CollectionUtil.toMultiValueMap(Map<K,List<V>> map);
```

## unmodifiableMultiValueMap
```java
/**
 * Return an unmodifiable view of the specified multi-value map.
 * @param  map the map for which an unmodifiable view is to be returned.
 * @return an unmodifiable view of the specified multi-value map.
 * @since 3.1
 */
CollectionUtil.unmodifiableMultiValueMap(MultiValueMap<? extends K,? extends V> map);
```

## hasNext
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.hasNext();
```

## next
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.next();
```

## remove
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.remove();
```

## getFirst
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.getFirst(K key);
```

## add
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.add(K key, V value);
```

## addAll
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.addAll(K key, List<? extends V> values);
```

## addAll
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.addAll(MultiValueMap<K,V> values);
```

## set
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.set(K key, V value);
```

## setAll
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.setAll(Map<K,V> values);
```

## toSingleValueMap
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.toSingleValueMap();
```

## size
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.size();
```

## isEmpty
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.isEmpty();
```

## containsKey
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.containsKey(Object key);
```

## containsValue
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.containsValue(Object value);
```

## get
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.get(Object key);
```

## put
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.put(K key, List<V> value);
```

## remove
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.remove(Object key);
```

## putAll
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.putAll(Map<? extends K,? extends List<V>> map);
```

## clear
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.clear();
```

## keySet
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.keySet();
```

## values
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.values();
```

## entrySet
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.entrySet();
```

## equals
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.equals(Object other);
```

## hashCode
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.hashCode();
```

## toString
```java
/**
 */
CollectionUtil collectionUtil = new CollectionUtil();
collectionUtil.toString();
```

