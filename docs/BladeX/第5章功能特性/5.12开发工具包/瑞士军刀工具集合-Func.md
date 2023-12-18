#  工具包集合，工具类快捷方式
**类名：** `Func`

## requireNotNull
```java
/**
 * 断言，必须不能为 null
 * <blockquote><pre>
 * public Foo(Bar bar) {
 *     this.bar = $.requireNotNull(bar);
 * }
 * </pre></blockquote>
 *
 * @param obj the object reference to check for nullity
 * @param <T> the type of the reference
 * @return {@code obj} if not {@code null}
 * @throws NullPointerException if {@code obj} is {@code null}
 */
Func.requireNotNull(T obj);
```

## requireNotNull
```java
/**
 * 断言，必须不能为 null
 * <blockquote><pre>
 * public Foo(Bar bar, Baz baz) {
 *     this.bar = $.requireNotNull(bar, "bar must not be null");
 *     this.baz = $.requireNotNull(baz, "baz must not be null");
 * }
 * </pre></blockquote>
 *
 * @param obj     the object reference to check for nullity
 * @param message detail message to be used in the event that a {@code
 *                NullPointerException} is thrown
 * @param <T>     the type of the reference
 * @return {@code obj} if not {@code null}
 * @throws NullPointerException if {@code obj} is {@code null}
 */
Func.requireNotNull(T obj, String message);
```

## requireNotNull
```java
/**
 * 断言，必须不能为 null
 * <blockquote><pre>
 * public Foo(Bar bar, Baz baz) {
 *     this.bar = $.requireNotNull(bar, () -> "bar must not be null");
 * }
 * </pre></blockquote>
 *
 * @param obj             the object reference to check for nullity
 * @param messageSupplier supplier of the detail message to be
 *                        used in the event that a {@code NullPointerException} is thrown
 * @param <T>             the type of the reference
 * @return {@code obj} if not {@code null}
 * @throws NullPointerException if {@code obj} is {@code null}
 */
Func.requireNotNull(T obj, Supplier<String> messageSupplier);
```

## isNull
```java
/**
 * 判断对象是否为null
 * <p>
 * This method exists to be used as a
 * {@link java.util.function.Predicate}, {@code filter($::isNull)}
 * </p>
 *
 * @param obj a reference to be checked against {@code null}
 * @return {@code true} if the provided reference is {@code null} otherwise
 * {@code false}
 * @see java.util.function.Predicate
 */
Func.isNull(Object obj);
```

## notNull
```java
/**
 * 判断对象是否 not null
 * <p>
 * This method exists to be used as a
 * {@link java.util.function.Predicate}, {@code filter($::notNull)}
 * </p>
 *
 * @param obj a reference to be checked against {@code null}
 * @return {@code true} if the provided reference is non-{@code null}
 * otherwise {@code false}
 * @see java.util.function.Predicate
 */
Func.notNull(Object obj);
```

## firstCharToLower
```java
/**
 * 首字母变小写
 *
 * @param str 字符串
 * @return {String}
 */
Func.firstCharToLower(String str);
```

## firstCharToUpper
```java
/**
 * 首字母变大写
 *
 * @param str 字符串
 * @return {String}
 */
Func.firstCharToUpper(String str);
```

## isBlank
```java
/**
 * 判断是否为空字符串
 * <pre class="code">
 * $.isBlank(null)		= true
 * $.isBlank("")		= true
 * $.isBlank(" ")		= true
 * $.isBlank("12345")	= false
 * $.isBlank(" 12345 ")	= false
 * </pre>
 *
 * @param cs the {@code CharSequence} to check (may be {@code null})
 * @return {@code true} if the {@code CharSequence} is not {@code null},
 * its length is greater than 0, and it does not contain whitespace only
 * @see Character#isWhitespace
 */
Func.isBlank(CharSequence cs);
```

## isNotBlank
```java
/**
 * 判断不为空字符串
 * <pre>
 * $.isNotBlank(null)	= false
 * $.isNotBlank("")		= false
 * $.isNotBlank(" ")	= false
 * $.isNotBlank("bob")	= true
 * $.isNotBlank("  bob  ") = true
 * </pre>
 *
 * @param cs the CharSequence to check, may be null
 * @return {@code true} if the CharSequence is
 * not empty and not null and not whitespace
 * @see Character#isWhitespace
 */
Func.isNotBlank(CharSequence cs);
```

## isAnyBlank
```java
/**
 * 判断是否有任意一个 空字符串
 *
 * @param css CharSequence
 * @return boolean
 */
Func.isAnyBlank(CharSequence css);
```

## isNoneBlank
```java
/**
 * 判断是否全为非空字符串
 *
 * @param css CharSequence
 * @return boolean
 */
Func.isNoneBlank(CharSequence css);
```

## isArray
```java
/**
 * 判断对象是数组
 *
 * @param obj the object to check
 * @return 是否数组
 */
Func.isArray(Object obj);
```

## isEmpty
```java
/**
 * 判断空对象 object、map、list、set、字符串、数组
 *
 * @param obj the object to check
 * @return 数组是否为空
 */
Func.isEmpty(Object obj);
```

## isNotEmpty
```java
/**
 * 对象不为空 object、map、list、set、字符串、数组
 *
 * @param obj the object to check
 * @return 是否不为空
 */
Func.isNotEmpty(Object obj);
```

## isEmpty
```java
/**
 * 判断数组为空
 *
 * @param array the array to check
 * @return 数组是否为空
 */
Func.isEmpty(Object[] array);
```

## isNotEmpty
```java
/**
 * 判断数组不为空
 *
 * @param array 数组
 * @return 数组是否不为空
 */
Func.isNotEmpty(Object[] array);
```

## hasEmpty
```java
/**
 * 对象组中是否存在 Empty Object
 *
 * @param os 对象组
 * @return boolean
 */
Func.hasEmpty(Object os);
```

## isAllEmpty
```java
/**
 * 对象组中是否全部为 Empty Object
 *
 * @param os 对象组
 * @return boolean
 */
Func.isAllEmpty(Object os);
```

## format
```java
/**
 * 将字符串中特定模式的字符转换成map中对应的值
 * <p>
 * use: format("my name is ${name}, and i like ${like}!", {"name":"L.cm", "like": "Java"})
 *
 * @param message 需要转换的字符串
 * @param params  转换所需的键值对集合
 * @return 转换后的字符串
 */
Func.format(String message, Map<String,Object> params);
```

## format
```java
/**
 * 同 log 格式的 format 规则
 * <p>
 * use: format("my name is {}, and i like {}!", "L.cm", "Java")
 *
 * @param message   需要转换的字符串
 * @param arguments 需要替换的变量
 * @return 转换后的字符串
 */
Func.format(String message, Object arguments);
```

## equals
```java
/**
 * 比较两个对象是否相等。

 * 相同的条件有两个，满足其一即可：

 *
 * @param obj1 对象1
 * @param obj2 对象2
 * @return 是否相等
 */
Func.equals(Object obj1, Object obj2);
```

## equalsSafe
```java
/**
 * 安全的 equals
 *
 * @param o1 first Object to compare
 * @param o2 second Object to compare
 * @return whether the given objects are equal
 * @see Object#equals(Object)
 * @see java.util.Arrays#equals
 */
Func.equalsSafe(Object o1, Object o2);
```

## contains
```java
/**
 * 判断数组中是否包含元素
 *
 * @param array   the Array to check
 * @param element the element to look for
 * @param <T>     The generic tag
 * @return {@code true} if found, {@code false} else
 */
Func.contains(T[] array, T element);
```

## contains
```java
/**
 * 判断迭代器中是否包含元素
 *
 * @param iterator the Iterator to check
 * @param element  the element to look for
 * @return {@code true} if found, {@code false} otherwise
 */
Func.contains(Iterator<?> iterator, Object element);
```

## contains
```java
/**
 * 判断枚举是否包含该元素
 *
 * @param enumeration the Enumeration to check
 * @param element     the element to look for
 * @return {@code true} if found, {@code false} otherwise
 */
Func.contains(Enumeration<?> enumeration, Object element);
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
Func.ofImmutableSet(E es);
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
Func.ofImmutableList(E es);
```

## toStr
```java
/**
 * 强转string,并去掉多余空格
 *
 * @param str 字符串
 * @return {String}
 */
Func.toStr(Object str);
```

## toStr
```java
/**
 * 强转string,并去掉多余空格
 *
 * @param str          字符串
 * @param defaultValue 默认值
 * @return {String}
 */
Func.toStr(Object str, String defaultValue);
```

## toStrWithEmpty
```java
/**
 * 强转string(包含空字符串),并去掉多余空格
 *
 * @param str          字符串
 * @param defaultValue 默认值
 * @return {String}
 */
Func.toStrWithEmpty(Object str, String defaultValue);
```

## isNumeric
```java
/**
 * 判断一个字符串是否是数字
 *
 * @param cs the CharSequence to check, may be null
 * @return {boolean}
 */
Func.isNumeric(CharSequence cs);
```

## toInt
```java
/**
 * 字符串转 int，为空则返回0
 *
 * <pre>
 *   $.toInt(null) = 0
 *   $.toInt("")   = 0
 *   $.toInt("1")  = 1
 * </pre>
 *
 * @param str the string to convert, may be null
 * @return the int represented by the string, or <code>zero</code> if
 * conversion fails
 */
Func.toInt(Object str);
```

## toInt
```java
/**
 * 字符串转 int，为空则返回默认值
 *
 * <pre>
 *   $.toInt(null, 1) = 1
 *   $.toInt("", 1)   = 1
 *   $.toInt("1", 0)  = 1
 * </pre>
 *
 * @param str          the string to convert, may be null
 * @param defaultValue the default value
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toInt(Object str, int defaultValue);
```

## toLong
```java
/**
 * 字符串转 long，为空则返回0
 *
 * <pre>
 *   $.toLong(null) = 0L
 *   $.toLong("")   = 0L
 *   $.toLong("1")  = 1L
 * </pre>
 *
 * @param str the string to convert, may be null
 * @return the long represented by the string, or <code>0</code> if
 * conversion fails
 */
Func.toLong(Object str);
```

## toLong
```java
/**
 * 字符串转 long，为空则返回默认值
 *
 * <pre>
 *   $.toLong(null, 1L) = 1L
 *   $.toLong("", 1L)   = 1L
 *   $.toLong("1", 0L)  = 1L
 * </pre>
 *
 * @param str          the string to convert, may be null
 * @param defaultValue the default value
 * @return the long represented by the string, or the default if conversion fails
 */
Func.toLong(Object str, long defaultValue);
```

## toDouble
```java
/**
 * <p>Convert a <code>String</code> to an <code>Double</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toDouble(null, 1) = 1.0
 *   $.toDouble("", 1)   = 1.0
 *   $.toDouble("1", 0)  = 1.0
 * </pre>
 *
 * @param value the string to convert, may be null
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toDouble(Object value);
```

## toDouble
```java
/**
 * <p>Convert a <code>String</code> to an <code>Double</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toDouble(null, 1) = 1.0
 *   $.toDouble("", 1)   = 1.0
 *   $.toDouble("1", 0)  = 1.0
 * </pre>
 *
 * @param value        the string to convert, may be null
 * @param defaultValue the default value
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toDouble(Object value, Double defaultValue);
```

## toFloat
```java
/**
 * <p>Convert a <code>String</code> to an <code>Float</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toFloat(null, 1) = 1.00f
 *   $.toFloat("", 1)   = 1.00f
 *   $.toFloat("1", 0)  = 1.00f
 * </pre>
 *
 * @param value the string to convert, may be null
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toFloat(Object value);
```

## toFloat
```java
/**
 * <p>Convert a <code>String</code> to an <code>Float</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toFloat(null, 1) = 1.00f
 *   $.toFloat("", 1)   = 1.00f
 *   $.toFloat("1", 0)  = 1.00f
 * </pre>
 *
 * @param value        the string to convert, may be null
 * @param defaultValue the default value
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toFloat(Object value, Float defaultValue);
```

## toBoolean
```java
/**
 * <p>Convert a <code>String</code> to an <code>Boolean</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toBoolean("true", true)  = true
 *   $.toBoolean("false")   	= false
 *   $.toBoolean("", false)  	= false
 * </pre>
 *
 * @param value the string to convert, may be null
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toBoolean(Object value);
```

## toBoolean
```java
/**
 * <p>Convert a <code>String</code> to an <code>Boolean</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   $.toBoolean("true", true)  = true
 *   $.toBoolean("false")   	= false
 *   $.toBoolean("", false)  	= false
 * </pre>
 *
 * @param value        the string to convert, may be null
 * @param defaultValue the default value
 * @return the int represented by the string, or the default if conversion fails
 */
Func.toBoolean(Object value, Boolean defaultValue);
```

## toIntArray
```java
/**
 * 转换为Integer数组

 *
 * @param str 被转换的值
 * @return 结果
 */
Func.toIntArray(String str);
```

## toIntArray
```java
/**
 * 转换为Integer数组

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toIntArray(String split, String str);
```

## toIntList
```java
/**
 * 转换为Integer集合

 *
 * @param str 结果被转换的值
 * @return 结果
 */
Func.toIntList(String str);
```

## toIntList
```java
/**
 * 转换为Integer集合

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toIntList(String split, String str);
```

## firstInt
```java
/**
 * 获取第一位Integer数值
 *
 * @param str 被转换的值
 * @return 结果
 */
Func.firstInt(String str);
```

## firstInt
```java
/**
 * 获取第一位Integer数值
 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.firstInt(String split, String str);
```

## toLongArray
```java
/**
 * 转换为Long数组

 *
 * @param str 被转换的值
 * @return 结果
 */
Func.toLongArray(String str);
```

## toLongArray
```java
/**
 * 转换为Long数组

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toLongArray(String split, String str);
```

## toLongList
```java
/**
 * 转换为Long集合

 *
 * @param str 结果被转换的值
 * @return 结果
 */
Func.toLongList(String str);
```

## toLongList
```java
/**
 * 转换为Long集合

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toLongList(String split, String str);
```

## firstLong
```java
/**
 * 获取第一位Long数值
 *
 * @param str 被转换的值
 * @return 结果
 */
Func.firstLong(String str);
```

## firstLong
```java
/**
 * 获取第一位Long数值
 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.firstLong(String split, String str);
```

## toStrArray
```java
/**
 * 转换为String数组

 *
 * @param str 被转换的值
 * @return 结果
 */
Func.toStrArray(String str);
```

## toStrArray
```java
/**
 * 转换为String数组

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toStrArray(String split, String str);
```

## toStrList
```java
/**
 * 转换为String集合

 *
 * @param str 结果被转换的值
 * @return 结果
 */
Func.toStrList(String str);
```

## toStrList
```java
/**
 * 转换为String集合

 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.toStrList(String split, String str);
```

## firstStr
```java
/**
 * 获取第一位String数值
 *
 * @param str 被转换的值
 * @return 结果
 */
Func.firstStr(String str);
```

## firstStr
```java
/**
 * 获取第一位String数值
 *
 * @param split 分隔符
 * @param str   被转换的值
 * @return 结果
 */
Func.firstStr(String split, String str);
```

## to62String
```java
/**
 * 将 long 转短字符串 为 62 进制
 *
 * @param num 数字
 * @return 短字符串
 */
Func.to62String(long num);
```

## join
```java
/**
 * 将集合拼接成字符串，默认使用`,`拼接
 *
 * @param coll the {@code Collection} to convert
 * @return the delimited {@code String}
 */
Func.join(Collection<?> coll);
```

## join
```java
/**
 * 将集合拼接成字符串，默认指定分隔符
 *
 * @param coll  the {@code Collection} to convert
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
Func.join(Collection<?> coll, String delim);
```

## join
```java
/**
 * 将数组拼接成字符串，默认使用`,`拼接
 *
 * @param arr the array to display
 * @return the delimited {@code String}
 */
Func.join(Object[] arr);
```

## join
```java
/**
 * 将数组拼接成字符串，默认指定分隔符
 *
 * @param arr   the array to display
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
Func.join(Object[] arr, String delim);
```

## split
```java
/**
 * 切分字符串，不去除切分后每个元素两边的空白符，不去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @return 切分后的集合
 */
Func.split(CharSequence str, char separator);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @return 切分后的集合
 */
Func.splitTrim(CharSequence str, char separator);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @return 切分后的集合
 */
Func.splitTrim(CharSequence str, CharSequence separator);
```

## split
```java
/**
 * 分割 字符串
 *
 * @param str       字符串
 * @param delimiter 分割符
 * @return 字符串数组
 */
Func.split(String str, String delimiter);
```

## splitTrim
```java
/**
 * 分割 字符串 删除常见 空白符
 *
 * @param str       字符串
 * @param delimiter 分割符
 * @return 字符串数组
 */
Func.splitTrim(String str, String delimiter);
```

## simpleMatch
```java
/**
 * 字符串是否符合指定的 表达式
 *
 * <p>
 * pattern styles: "xxx*", "*xxx", "*xxx*" and "xxx*yyy"
 * </p>
 *
 * @param pattern 表达式
 * @param str     字符串
 * @return 是否匹配
 */
Func.simpleMatch(String pattern, String str);
```

## simpleMatch
```java
/**
 * 字符串是否符合指定的 表达式
 *
 * <p>
 * pattern styles: "xxx*", "*xxx", "*xxx*" and "xxx*yyy"
 * </p>
 *
 * @param patterns 表达式 数组
 * @param str      字符串
 * @return 是否匹配
 */
Func.simpleMatch(String[] patterns, String str);
```

## randomUUID
```java
/**
 * 生成uuid
 *
 * @return UUID
 */
Func.randomUUID();
```

## escapeHtml
```java
/**
 * 转义HTML用于安全过滤
 *
 * @param html html
 * @return {String}
 */
Func.escapeHtml(String html);
```

## random
```java
/**
 * 随机数生成
 *
 * @param count 字符长度
 * @return 随机数
 */
Func.random(int count);
```

## random
```java
/**
 * 随机数生成
 *
 * @param count      字符长度
 * @param randomType 随机数类别
 * @return 随机数
 */
Func.random(int count, RandomType randomType);
```

## md5Hex
```java
/**
 * 字符串序列化成 md5
 *
 * @param data Data to digest
 * @return MD5 digest as a hex string
 */
Func.md5Hex(String data);
```

## md5Hex
```java
/**
 * 数组序列化成 md5
 *
 * @param bytes the bytes to calculate the digest over
 * @return md5 digest string
 */
Func.md5Hex(byte[] bytes);
```

## sha1Hex
```java
/**
 * sha1Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
Func.sha1Hex(String data);
```

## sha1Hex
```java
/**
 * sha1Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
Func.sha1Hex(byte[] bytes);
```

## sha224Hex
```java
/**
 * SHA224Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
Func.sha224Hex(String data);
```

## sha224Hex
```java
/**
 * SHA224Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
Func.sha224Hex(byte[] bytes);
```

## sha256Hex
```java
/**
 * sha256Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
Func.sha256Hex(String data);
```

## sha256Hex
```java
/**
 * sha256Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
Func.sha256Hex(byte[] bytes);
```

## sha384Hex
```java
/**
 * sha384Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
Func.sha384Hex(String data);
```

## sha384Hex
```java
/**
 * sha384Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
Func.sha384Hex(byte[] bytes);
```

## sha512Hex
```java
/**
 * sha512Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
Func.sha512Hex(String data);
```

## sha512Hex
```java
/**
 * sha512Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
Func.sha512Hex(byte[] bytes);
```

## hmacMd5Hex
```java
/**
 * hmacMd5 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacMd5Hex(String data, String key);
```

## hmacMd5Hex
```java
/**
 * hmacMd5 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacMd5Hex(byte[] bytes, String key);
```

## hmacSha1Hex
```java
/**
 * hmacSha1 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacSha1Hex(String data, String key);
```

## hmacSha1Hex
```java
/**
 * hmacSha1 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacSha1Hex(byte[] bytes, String key);
```

## hmacSha224Hex
```java
/**
 * hmacSha224 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacSha224Hex(String data, String key);
```

## hmacSha224Hex
```java
/**
 * hmacSha224 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacSha224Hex(byte[] bytes, String key);
```

## hmacSha256Hex
```java
/**
 * hmacSha256 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacSha256Hex(String data, String key);
```

## hmacSha256Hex
```java
/**
 * hmacSha256 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacSha256Hex(byte[] bytes, String key);
```

## hmacSha384Hex
```java
/**
 * hmacSha384 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacSha384Hex(String data, String key);
```

## hmacSha384Hex
```java
/**
 * hmacSha384 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacSha384Hex(byte[] bytes, String key);
```

## hmacSha512Hex
```java
/**
 * hmacSha512 Hex
 *
 * @param data Data to digest
 * @param key  key
 * @return digest as a hex string
 */
Func.hmacSha512Hex(String data, String key);
```

## hmacSha512Hex
```java
/**
 * hmacSha512 Hex
 *
 * @param bytes Data to digest
 * @param key   key
 * @return digest as a hex string
 */
Func.hmacSha512Hex(byte[] bytes, String key);
```

## encodeHex
```java
/**
 * byte 数组序列化成 hex
 *
 * @param bytes bytes to encode
 * @return MD5 digest as a hex string
 */
Func.encodeHex(byte[] bytes);
```

## decodeHex
```java
/**
 * 字符串反序列化成 hex
 *
 * @param hexString String to decode
 * @return MD5 digest as a hex string
 */
Func.decodeHex(String hexString);
```

## encodeBase64
```java
/**
 * Base64编码
 *
 * @param value 字符串
 * @return {String}
 */
Func.encodeBase64(String value);
```

## encodeBase64
```java
/**
 * Base64编码
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Func.encodeBase64(String value, Charset charset);
```

## encodeBase64UrlSafe
```java
/**
 * Base64编码为URL安全
 *
 * @param value 字符串
 * @return {String}
 */
Func.encodeBase64UrlSafe(String value);
```

## encodeBase64UrlSafe
```java
/**
 * Base64编码为URL安全
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Func.encodeBase64UrlSafe(String value, Charset charset);
```

## decodeBase64
```java
/**
 * Base64解码
 *
 * @param value 字符串
 * @return {String}
 */
Func.decodeBase64(String value);
```

## decodeBase64
```java
/**
 * Base64解码
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Func.decodeBase64(String value, Charset charset);
```

## decodeBase64UrlSafe
```java
/**
 * Base64URL安全解码
 *
 * @param value 字符串
 * @return {String}
 */
Func.decodeBase64UrlSafe(String value);
```

## decodeBase64UrlSafe
```java
/**
 * Base64URL安全解码
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Func.decodeBase64UrlSafe(String value, Charset charset);
```

## closeQuietly
```java
/**
 * 关闭 Closeable
 *
 * @param closeable 自动关闭
 */
Func.closeQuietly(Closeable closeable);
```

## readToString
```java
/**
 * InputStream to String utf-8
 *
 * @param input the <code>InputStream</code> to read from
 * @return the requested String
 * @throws NullPointerException if the input is null
 */
Func.readToString(InputStream input);
```

## readToString
```java
/**
 * InputStream to String
 *
 * @param input   the <code>InputStream</code> to read from
 * @param charset the <code>Charset</code>
 * @return the requested String
 * @throws NullPointerException if the input is null
 */
Func.readToString(InputStream input, Charset charset);
```

## readToByteArray
```java
/**
 * InputStream to bytes 数组
 *
 * @param input InputStream
 * @return the requested byte array
 */
Func.readToByteArray(InputStream input);
```

## readToString
```java
/**
 * 读取文件为字符串
 *
 * @param file the file to read, must not be {@code null}
 * @return the file contents, never {@code null}
 */
Func.readToString(File file);
```

## readToString
```java
/**
 * 读取文件为字符串
 *
 * @param file     the file to read, must not be {@code null}
 * @param encoding the encoding to use, {@code null} means platform default
 * @return the file contents, never {@code null}
 */
Func.readToString(File file, Charset encoding);
```

## readToByteArray
```java
/**
 * 读取文件为 byte 数组
 *
 * @param file the file to read, must not be {@code null}
 * @return the file contents, never {@code null}
 */
Func.readToByteArray(File file);
```

## toJson
```java
/**
 * 将对象序列化成json字符串
 *
 * @param object javaBean
 * @return jsonString json字符串
 */
Func.toJson(Object object);
```

## toJsonAsBytes
```java
/**
 * 将对象序列化成 json byte 数组
 *
 * @param object javaBean
 * @return jsonString json字符串
 */
Func.toJsonAsBytes(Object object);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param jsonString jsonString
 * @return jsonString json字符串
 */
Func.readTree(String jsonString);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param in InputStream
 * @return jsonString json字符串
 */
Func.readTree(InputStream in);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param content content
 * @return jsonString json字符串
 */
Func.readTree(byte[] content);
```

## readTree
```java
/**
 * 将json字符串转成 JsonNode
 *
 * @param jsonParser JsonParser
 * @return jsonString json字符串
 */
Func.readTree(JsonParser jsonParser);
```

## readJson
```java
/**
 * 将json byte 数组反序列化成对象
 *
 * @param bytes     json bytes
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
Func.readJson(byte[] bytes, Class<T> valueType);
```

## readJson
```java
/**
 * 将json反序列化成对象
 *
 * @param jsonString jsonString
 * @param valueType  class
 * @param <T>        T 泛型标记
 * @return Bean
 */
Func.readJson(String jsonString, Class<T> valueType);
```

## readJson
```java
/**
 * 将json反序列化成对象
 *
 * @param in        InputStream
 * @param valueType class
 * @param <T>       T 泛型标记
 * @return Bean
 */
Func.readJson(InputStream in, Class<T> valueType);
```

## readJson
```java
/**
 * 将json反序列化成对象
 *
 * @param bytes         bytes
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
Func.readJson(byte[] bytes, TypeReference<?> typeReference);
```

## readJson
```java
/**
 * 将json反序列化成对象
 *
 * @param jsonString    jsonString
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
Func.readJson(String jsonString, TypeReference<?> typeReference);
```

## readJson
```java
/**
 * 将json反序列化成对象
 *
 * @param in            InputStream
 * @param typeReference 泛型类型
 * @param <T>           T 泛型标记
 * @return Bean
 */
Func.readJson(InputStream in, TypeReference<?> typeReference);
```

## urlEncode
```java
/**
 * url 编码
 *
 * @param source the String to be encoded
 * @return the encoded String
 */
Func.urlEncode(String source);
```

## urlEncode
```java
/**
 * url 编码
 *
 * @param source  the String to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded String
 */
Func.urlEncode(String source, Charset charset);
```

## urlDecode
```java
/**
 * url 解码
 *
 * @param source the encoded String
 * @return the decoded value
 * @throws IllegalArgumentException when the given source contains invalid encoded sequences
 * @see StringUtils#uriDecode(String, Charset)
 * @see java.net.URLDecoder#decode(String, String)
 */
Func.urlDecode(String source);
```

## urlDecode
```java
/**
 * url 解码
 *
 * @param source  the encoded String
 * @param charset the character encoding to use
 * @return the decoded value
 * @throws IllegalArgumentException when the given source contains invalid encoded sequences
 * @see StringUtils#uriDecode(String, Charset)
 * @see java.net.URLDecoder#decode(String, String)
 */
Func.urlDecode(String source, Charset charset);
```

## formatDateTime
```java
/**
 * 日期时间格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
Func.formatDateTime(Date date);
```

## formatDate
```java
/**
 * 日期格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
Func.formatDate(Date date);
```

## formatTime
```java
/**
 * 时间格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
Func.formatTime(Date date);
```

## format
```java
/**
 * 对象格式化 支持数字，date，java8时间
 *
 * @param object  格式化对象
 * @param pattern 表达式
 * @return 格式化后的字符串
 */
Func.format(Object object, String pattern);
```

## parseDate
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 表达式
 * @return 时间
 */
Func.parseDate(String dateStr, String pattern);
```

## parse
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param format  ConcurrentDateFormat
 * @return 时间
 */
Func.parse(String dateStr, ConcurrentDateFormat format);
```

## formatDateTime
```java
/**
 * 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
Func.formatDateTime(TemporalAccessor temporal);
```

## formatDate
```java
/**
 * 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
Func.formatDate(TemporalAccessor temporal);
```

## formatTime
```java
/**
 * 时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
Func.formatTime(TemporalAccessor temporal);
```

## parseDateTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
Func.parseDateTime(String dateStr, DateTimeFormatter formatter);
```

## parseDateTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
Func.parseDateTime(String dateStr);
```

## parseDate
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
Func.parseDate(String dateStr, DateTimeFormatter formatter);
```

## parseDate
```java
/**
 * 将字符串转换为日期
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
Func.parseDate(String dateStr);
```

## parseTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
Func.parseTime(String dateStr, DateTimeFormatter formatter);
```

## parseTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
Func.parseTime(String dateStr);
```

## between
```java
/**
 * 时间比较
 *
 * @param startInclusive the start instant, inclusive, not null
 * @param endExclusive   the end instant, exclusive, not null
 * @return a {@code Duration}, not null
 */
Func.between(Temporal startInclusive, Temporal endExclusive);
```

## between
```java
/**
 * 比较2个 时间差
 *
 * @param startDate 开始时间
 * @param endDate   结束时间
 * @return 时间间隔
 */
Func.between(Date startDate, Date endDate);
```

## convert
```java
/**
 * 对象类型转换
 *
 * @param source     the source object
 * @param targetType the target type
 * @param <T>        泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 *                                  or sourceType is {@code null} but source is not {@code null}
 */
Func.convert(Object source, Class<T> targetType);
```

## convert
```java
/**
 * 对象类型转换
 *
 * @param source     the source object
 * @param sourceType the source type
 * @param targetType the target type
 * @param <T>        泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 *                                  or sourceType is {@code null} but source is not {@code null}
 */
Func.convert(Object source, TypeDescriptor sourceType, TypeDescriptor targetType);
```

## convert
```java
/**
 * 对象类型转换
 *
 * @param source     the source object
 * @param targetType the target type
 * @param <T>        泛型标记
 * @return the converted value
 * @throws IllegalArgumentException if targetType is {@code null},
 *                                  or sourceType is {@code null} but source is not {@code null}
 */
Func.convert(Object source, TypeDescriptor targetType);
```

## getMethodParameter
```java
/**
 * 获取方法参数信息
 *
 * @param constructor    构造器
 * @param parameterIndex 参数序号
 * @return {MethodParameter}
 */
Func.getMethodParameter(Constructor<?> constructor, int parameterIndex);
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
Func.getMethodParameter(Method method, int parameterIndex);
```

## getAnnotation
```java
/**
 * 获取Annotation注解
 *
 * @param annotatedElement AnnotatedElement
 * @param annotationType   注解类
 * @param <A>              泛型标记
 * @return {Annotation}
 */
Func.getAnnotation(AnnotatedElement annotatedElement, Class<A> annotationType);
```

## getAnnotation
```java
/**
 * 获取Annotation，先找方法，没有则再找方法上的类
 *
 * @param method         Method
 * @param annotationType 注解类
 * @param <A>            泛型标记
 * @return {Annotation}
 */
Func.getAnnotation(Method method, Class<A> annotationType);
```

## getAnnotation
```java
/**
 * 获取Annotation，先找HandlerMethod，没有则再找对应的类
 *
 * @param handlerMethod  HandlerMethod
 * @param annotationType 注解类
 * @param <A>            泛型标记
 * @return {Annotation}
 */
Func.getAnnotation(HandlerMethod handlerMethod, Class<A> annotationType);
```

## newInstance
```java
/**
 * 实例化对象
 *
 * @param clazz 类
 * @param <T>   泛型标记
 * @return 对象
 */
Func.newInstance(Class<?> clazz);
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
Func.newInstance(String clazzStr);
```

## getProperty
```java
/**
 * 获取Bean的属性
 *
 * @param bean         bean
 * @param propertyName 属性名
 * @return 属性值
 */
Func.getProperty(Object bean, String propertyName);
```

## setProperty
```java
/**
 * 设置Bean属性
 *
 * @param bean         bean
 * @param propertyName 属性名
 * @param value        属性值
 */
Func.setProperty(Object bean, String propertyName, Object value);
```

## clone
```java
/**
 * 浅复制
 *
 * @param source 源对象
 * @param <T>    泛型标记
 * @return T
 */
Func.clone(T source);
```

## copy
```java
/**
 * 拷贝对象，支持 Map 和 Bean
 *
 * @param source 源对象
 * @param clazz  类名
 * @param <T>    泛型标记
 * @return T
 */
Func.copy(Object source, Class<T> clazz);
```

## copy
```java
/**
 * 拷贝对象，支持 Map 和 Bean
 *
 * @param source     源对象
 * @param targetBean 需要赋值的对象
 */
Func.copy(Object source, Object targetBean);
```

## copyNonNull
```java
/**
 * 拷贝对象，source 对象属性做非 null 判断
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param source     源对象
 * @param targetBean 需要赋值的对象
 */
Func.copyNonNull(Object source, Object targetBean);
```

## copyWithConvert
```java
/**
 * 拷贝对象，并对不同类型属性进行转换
 *
 * @param source 源对象
 * @param clazz  类名
 * @param <T>    泛型标记
 * @return T
 */
Func.copyWithConvert(Object source, Class<T> clazz);
```

## copy
```java
/**
 * 拷贝列表对象
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
Func.copy(Collection<?> sourceList, Class<T> targetClazz);
```

## copyWithConvert
```java
/**
 * 拷贝列表对象，并对不同类型属性进行转换
 *
 * <p>
 * 支持 map bean copy
 * </p>
 *
 * @param sourceList  源对象列表
 * @param targetClazz 转换成的类
 * @param <T>         泛型标记
 * @return List
 */
Func.copyWithConvert(Collection<?> sourceList, Class<T> targetClazz);
```

## copyProperties
```java
/**
 * 拷贝对象，扩展 Spring 的拷贝方法
 *
 * @param source the source bean
 * @param clazz  the target bean class
 * @param <T>    泛型标记
 * @return T
 * @throws BeansException if the copying failed
 */
Func.copyProperties(Object source, Class<T> clazz);
```

## copyProperties
```java
/**
 * 拷贝列表对象，扩展 Spring 的拷贝方法
 *
 * @param sourceList  the source list bean
 * @param targetClazz the target bean class
 * @param <T>         泛型标记
 * @return List
 * @throws BeansException if the copying failed
 */
Func.copyProperties(Collection<?> sourceList, Class<T> targetClazz);
```

## toMap
```java
/**
 * 将对象装成map形式
 *
 * @param bean 源对象
 * @return {Map}
 */
Func.toMap(Object bean);
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
Func.toBean(Map<String,Object> beanMap, Class<T> valueType);
```

