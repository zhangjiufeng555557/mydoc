#  继承自Spring StringUtils工具类，拓展封装
**类名：** `StringUtil`

## isBlank
```java
/**
 * Check whether the given {@code CharSequence} contains actual <em>text</em>.
 * <p>More specifically, this method returns {@code true} if the
 * {@code CharSequence} is not {@code null}, its length is greater than
 * 0, and it contains at least one non-whitespace character.
 * <pre class="code">
 * StringUtil.isBlank(null) = true
 * StringUtil.isBlank("") = true
 * StringUtil.isBlank(" ") = true
 * StringUtil.isBlank("12345") = false
 * StringUtil.isBlank(" 12345 ") = false
 * </pre>
 *
 * @param cs the {@code CharSequence} to check (may be {@code null})
 * @return {@code true} if the {@code CharSequence} is not {@code null},
 * its length is greater than 0, and it does not contain whitespace only
 * @see Character#isWhitespace
 */
StringUtil.isBlank(CharSequence cs);
```

## isNotBlank
```java
/**
 * <p>Checks if a CharSequence is not empty (""), not null and not whitespace only.</p>
 * <pre>
 * StringUtil.isNotBlank(null)	  = false
 * StringUtil.isNotBlank("")		= false
 * StringUtil.isNotBlank(" ")	   = false
 * StringUtil.isNotBlank("bob")	 = true
 * StringUtil.isNotBlank("  bob  ") = true
 * </pre>
 *
 * @param cs the CharSequence to check, may be null
 * @return {@code true} if the CharSequence is
 * not empty and not null and not whitespace
 * @see Character#isWhitespace
 */
StringUtil.isNotBlank(CharSequence cs);
```

## isAnyBlank
```java
/**
 * 有 任意 一个 Blank
 *
 * @param css CharSequence
 * @return boolean
 */
StringUtil.isAnyBlank(CharSequence css);
```

## isNoneBlank
```java
/**
 * 是否全非 Blank
 *
 * @param css CharSequence
 * @return boolean
 */
StringUtil.isNoneBlank(CharSequence css);
```

## isAllBlank
```java
/**
 * 是否全为 Blank
 *
 * @param css CharSequence
 * @return boolean
 */
StringUtil.isAllBlank(CharSequence css);
```

## isNumeric
```java
/**
 * 判断一个字符串是否是数字
 *
 * @param cs the CharSequence to check, may be null
 * @return {boolean}
 */
StringUtil.isNumeric(CharSequence cs);
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
StringUtil.format(String message, Map<String,Object> params);
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
StringUtil.format(String message, Object arguments);
```

## join
```java
/**
 * Convert a {@code Collection} into a delimited {@code String} (e.g., CSV).
 * <p>Useful for {@code toString()} implementations.
 *
 * @param coll the {@code Collection} to convert
 * @return the delimited {@code String}
 */
StringUtil.join(Collection<?> coll);
```

## join
```java
/**
 * Convert a {@code Collection} into a delimited {@code String} (e.g. CSV).
 * <p>Useful for {@code toString()} implementations.
 *
 * @param coll  the {@code Collection} to convert
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
StringUtil.join(Collection<?> coll, String delim);
```

## join
```java
/**
 * Convert a {@code String} array into a comma delimited {@code String}
 * (i.e., CSV).
 * <p>Useful for {@code toString()} implementations.
 *
 * @param arr the array to display
 * @return the delimited {@code String}
 */
StringUtil.join(Object[] arr);
```

## join
```java
/**
 * Convert a {@code String} array into a delimited {@code String} (e.g. CSV).
 * <p>Useful for {@code toString()} implementations.
 *
 * @param arr   the array to display
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
StringUtil.join(Object[] arr, String delim);
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
StringUtil.simpleMatch(String pattern, String str);
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
StringUtil.simpleMatch(String[] patterns, String str);
```

## randomUUID
```java
/**
 * 生成uuid
 *
 * @return UUID
 */
StringUtil.randomUUID();
```

## escapeHtml
```java
/**
 * 转义HTML用于安全过滤
 *
 * @param html html
 * @return {String}
 */
StringUtil.escapeHtml(String html);
```

## cleanChars
```java
/**
 * 清理字符串，清理出某些不可见字符
 *
 * @param txt 字符串
 * @return {String}
 */
StringUtil.cleanChars(String txt);
```

## random
```java
/**
 * 随机数生成
 *
 * @param count 字符长度
 * @return 随机数
 */
StringUtil.random(int count);
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
StringUtil.random(int count, RandomType randomType);
```

## indexedFormat
```java
/**
 * 有序的格式化文本，使用{number}做为占位符

 * 例：

 * 通常使用：format("this is {0} for {1}", "a", "b") =》 this is a for b

 *
 * @param pattern   文本格式
 * @param arguments 参数
 * @return 格式化后的文本
 */
StringUtil.indexedFormat(CharSequence pattern, Object arguments);
```

## format
```java
/**
 * 格式化文本，使用 {varName} 占位

 * map = {a: "aValue", b: "bValue"} format("{a} and {b}", map) ---=》 aValue and bValue
 *
 * @param template 文本模板，被替换的部分用 {key} 表示
 * @param map      参数值对
 * @return 格式化后的文本
 */
StringUtil.format(CharSequence template, Map<?,?> map);
```

## split
```java
/**
 * 切分字符串，不去除切分后每个元素两边的空白符，不去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @param limit     限制分片数，-1不限制
 * @return 切分后的集合
 */
StringUtil.split(CharSequence str, char separator, int limit);
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
StringUtil.splitTrim(String str, String delimiter);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @return 切分后的集合
 * @since 3.1.2
 */
StringUtil.splitTrim(CharSequence str, char separator);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @return 切分后的集合
 * @since 3.2.0
 */
StringUtil.splitTrim(CharSequence str, CharSequence separator);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @param limit     限制分片数，-1不限制
 * @return 切分后的集合
 * @since 3.1.0
 */
StringUtil.splitTrim(CharSequence str, char separator, int limit);
```

## splitTrim
```java
/**
 * 切分字符串，去除切分后每个元素两边的空白符，去除空白项
 *
 * @param str       被切分的字符串
 * @param separator 分隔符字符
 * @param limit     限制分片数，-1不限制
 * @return 切分后的集合
 * @since 3.2.0
 */
StringUtil.splitTrim(CharSequence str, CharSequence separator, int limit);
```

## split
```java
/**
 * 切分字符串，不限制分片数量
 *
 * @param str         被切分的字符串
 * @param separator   分隔符字符
 * @param isTrim      是否去除切分字符串后每个元素两边的空格
 * @param ignoreEmpty 是否忽略空串
 * @return 切分后的集合
 * @since 3.0.8
 */
StringUtil.split(CharSequence str, char separator, boolean isTrim, boolean ignoreEmpty);
```

## split
```java
/**
 * 切分字符串
 *
 * @param str         被切分的字符串
 * @param separator   分隔符字符
 * @param limit       限制分片数，-1不限制
 * @param isTrim      是否去除切分字符串后每个元素两边的空格
 * @param ignoreEmpty 是否忽略空串
 * @return 切分后的集合
 * @since 3.0.8
 */
StringUtil.split(CharSequence str, char separator, int limit, boolean isTrim, boolean ignoreEmpty);
```

## split
```java
/**
 * 切分字符串
 *
 * @param str         被切分的字符串
 * @param separator   分隔符字符
 * @param limit       限制分片数，-1不限制
 * @param isTrim      是否去除切分字符串后每个元素两边的空格
 * @param ignoreEmpty 是否忽略空串
 * @return 切分后的集合
 * @since 3.2.0
 */
StringUtil.split(CharSequence str, CharSequence separator, int limit, boolean isTrim, boolean ignoreEmpty);
```

## split
```java
/**
 * 切分字符串
 *
 * @param str       被切分的字符串
 * @param separator 分隔符
 * @return 字符串
 */
StringUtil.split(CharSequence str, CharSequence separator);
```

## split
```java
/**
 * 根据给定长度，将给定字符串截取为多个部分
 *
 * @param str 字符串
 * @param len 每一个小节的长度
 * @return 截取后的字符串数组
 * @see StrSpliter#splitByLength(String, int)
 */
StringUtil.split(CharSequence str, int len);
```

## contains
```java
/**
 * 指定字符是否在字符串中出现过
 *
 * @param str        字符串
 * @param searchChar 被查找的字符
 * @return 是否包含
 * @since 3.1.2
 */
StringUtil.contains(CharSequence str, char searchChar);
```

## containsAny
```java
/**
 * 查找指定字符串是否包含指定字符串列表中的任意一个字符串
 *
 * @param str      指定字符串
 * @param testStrs 需要检查的字符串数组
 * @return 是否包含任意一个字符串
 * @since 3.2.0
 */
StringUtil.containsAny(CharSequence str, CharSequence testStrs);
```

## getContainsStr
```java
/**
 * 查找指定字符串是否包含指定字符串列表中的任意一个字符串，如果包含返回找到的第一个字符串
 *
 * @param str      指定字符串
 * @param testStrs 需要检查的字符串数组
 * @return 被包含的第一个字符串
 * @since 3.2.0
 */
StringUtil.getContainsStr(CharSequence str, CharSequence testStrs);
```

## containsIgnoreCase
```java
/**
 * 是否包含特定字符，忽略大小写，如果给定两个参数都为<code>null</code>，返回true
 *
 * @param str     被检测字符串
 * @param testStr 被测试是否包含的字符串
 * @return 是否包含
 */
StringUtil.containsIgnoreCase(CharSequence str, CharSequence testStr);
```

## containsAnyIgnoreCase
```java
/**
 * 查找指定字符串是否包含指定字符串列表中的任意一个字符串

 * 忽略大小写
 *
 * @param str      指定字符串
 * @param testStrs 需要检查的字符串数组
 * @return 是否包含任意一个字符串
 * @since 3.2.0
 */
StringUtil.containsAnyIgnoreCase(CharSequence str, CharSequence testStrs);
```

## getContainsStrIgnoreCase
```java
/**
 * 查找指定字符串是否包含指定字符串列表中的任意一个字符串，如果包含返回找到的第一个字符串

 * 忽略大小写
 *
 * @param str      指定字符串
 * @param testStrs 需要检查的字符串数组
 * @return 被包含的第一个字符串
 * @since 3.2.0
 */
StringUtil.getContainsStrIgnoreCase(CharSequence str, CharSequence testStrs);
```

## sub
```java
/**
 * 改进JDK subString

 * index从0开始计算，最后一个字符为-1

 * 如果from和to位置一样，返回 "" 

 * 如果from或to为负数，则按照length从后向前数位置，如果绝对值大于字符串长度，则from归到0，to归到length

 * 如果经过修正的index中from大于to，则互换from和to example: 

 * abcdefgh 2 3 =》 c 

 * abcdefgh 2 -3 =》 cde 

 *
 * @param str       String
 * @param fromIndex 开始的index（包括）
 * @param toIndex   结束的index（不包括）
 * @return 字串
 */
StringUtil.sub(CharSequence str, int fromIndex, int toIndex);
```

## subBefore
```java
/**
 * 截取分隔字符串之前的字符串，不包括分隔字符串

 * 如果给定的字符串为空串（null或""）或者分隔字符串为null，返回原字符串

 * 如果分隔字符串为空串""，则返回空串，如果分隔字符串未找到，返回原字符串
 * <p>
 * 栗子：
 *
 * <pre>
 * StringUtil.subBefore(null, *)      = null
 * StringUtil.subBefore("", *)        = ""
 * StringUtil.subBefore("abc", "a")   = ""
 * StringUtil.subBefore("abcba", "b") = "a"
 * StringUtil.subBefore("abc", "c")   = "ab"
 * StringUtil.subBefore("abc", "d")   = "abc"
 * StringUtil.subBefore("abc", "")    = ""
 * StringUtil.subBefore("abc", null)  = "abc"
 * </pre>
 *
 * @param string          被查找的字符串
 * @param separator       分隔字符串（不包括）
 * @param isLastSeparator 是否查找最后一个分隔字符串（多次出现分隔字符串时选取最后一个），true为选取最后一个
 * @return 切割后的字符串
 * @since 3.1.1
 */
StringUtil.subBefore(CharSequence string, CharSequence separator, boolean isLastSeparator);
```

## subAfter
```java
/**
 * 截取分隔字符串之后的字符串，不包括分隔字符串

 * 如果给定的字符串为空串（null或""），返回原字符串

 * 如果分隔字符串为空串（null或""），则返回空串，如果分隔字符串未找到，返回空串
 * <p>
 * 栗子：
 *
 * <pre>
 * StringUtil.subAfter(null, *)      = null
 * StringUtil.subAfter("", *)        = ""
 * StringUtil.subAfter(*, null)      = ""
 * StringUtil.subAfter("abc", "a")   = "bc"
 * StringUtil.subAfter("abcba", "b") = "cba"
 * StringUtil.subAfter("abc", "c")   = ""
 * StringUtil.subAfter("abc", "d")   = ""
 * StringUtil.subAfter("abc", "")    = "abc"
 * </pre>
 *
 * @param string          被查找的字符串
 * @param separator       分隔字符串（不包括）
 * @param isLastSeparator 是否查找最后一个分隔字符串（多次出现分隔字符串时选取最后一个），true为选取最后一个
 * @return 切割后的字符串
 * @since 3.1.1
 */
StringUtil.subAfter(CharSequence string, CharSequence separator, boolean isLastSeparator);
```

## subBetween
```java
/**
 * 截取指定字符串中间部分，不包括标识字符串

 * <p>
 * 栗子：
 *
 * <pre>
 * StringUtil.subBetween("wx[b]yz", "[", "]") = "b"
 * StringUtil.subBetween(null, *, *)          = null
 * StringUtil.subBetween(*, null, *)          = null
 * StringUtil.subBetween(*, *, null)          = null
 * StringUtil.subBetween("", "", "")          = ""
 * StringUtil.subBetween("", "", "]")         = null
 * StringUtil.subBetween("", "[", "]")        = null
 * StringUtil.subBetween("yabcz", "", "")     = ""
 * StringUtil.subBetween("yabcz", "y", "z")   = "abc"
 * StringUtil.subBetween("yabczyabcz", "y", "z")   = "abc"
 * </pre>
 *
 * @param str    被切割的字符串
 * @param before 截取开始的字符串标识
 * @param after  截取到的字符串标识
 * @return 截取后的字符串
 * @since 3.1.1
 */
StringUtil.subBetween(CharSequence str, CharSequence before, CharSequence after);
```

## subBetween
```java
/**
 * 截取指定字符串中间部分，不包括标识字符串

 * <p>
 * 栗子：
 *
 * <pre>
 * StringUtil.subBetween(null, *)            = null
 * StringUtil.subBetween("", "")             = ""
 * StringUtil.subBetween("", "tag")          = null
 * StringUtil.subBetween("tagabctag", null)  = null
 * StringUtil.subBetween("tagabctag", "")    = ""
 * StringUtil.subBetween("tagabctag", "tag") = "abc"
 * </pre>
 *
 * @param str            被切割的字符串
 * @param beforeAndAfter 截取开始和结束的字符串标识
 * @return 截取后的字符串
 * @since 3.1.1
 */
StringUtil.subBetween(CharSequence str, CharSequence beforeAndAfter);
```

## removePrefix
```java
/**
 * 去掉指定前缀
 *
 * @param str    字符串
 * @param prefix 前缀
 * @return 切掉后的字符串，若前缀不是 preffix， 返回原字符串
 */
StringUtil.removePrefix(CharSequence str, CharSequence prefix);
```

## removePrefixIgnoreCase
```java
/**
 * 忽略大小写去掉指定前缀
 *
 * @param str    字符串
 * @param prefix 前缀
 * @return 切掉后的字符串，若前缀不是 prefix， 返回原字符串
 */
StringUtil.removePrefixIgnoreCase(CharSequence str, CharSequence prefix);
```

## removeSuffix
```java
/**
 * 去掉指定后缀
 *
 * @param str    字符串
 * @param suffix 后缀
 * @return 切掉后的字符串，若后缀不是 suffix， 返回原字符串
 */
StringUtil.removeSuffix(CharSequence str, CharSequence suffix);
```

## removeSufAndLowerFirst
```java
/**
 * 去掉指定后缀，并小写首字母
 *
 * @param str    字符串
 * @param suffix 后缀
 * @return 切掉后的字符串，若后缀不是 suffix， 返回原字符串
 */
StringUtil.removeSufAndLowerFirst(CharSequence str, CharSequence suffix);
```

## removeSuffixIgnoreCase
```java
/**
 * 忽略大小写去掉指定后缀
 *
 * @param str    字符串
 * @param suffix 后缀
 * @return 切掉后的字符串，若后缀不是 suffix， 返回原字符串
 */
StringUtil.removeSuffixIgnoreCase(CharSequence str, CharSequence suffix);
```

## firstCharToLower
```java
/**
 * 首字母变小写
 *
 * @param str 字符串
 * @return {String}
 */
StringUtil.firstCharToLower(String str);
```

## firstCharToUpper
```java
/**
 * 首字母变大写
 *
 * @param str 字符串
 * @return {String}
 */
StringUtil.firstCharToUpper(String str);
```

## subPre
```java
/**
 * 切割指定位置之前部分的字符串
 *
 * @param string  字符串
 * @param toIndex 切割到的位置（不包括）
 * @return 切割后的剩余的前半部分字符串
 */
StringUtil.subPre(CharSequence string, int toIndex);
```

## subSuf
```java
/**
 * 切割指定位置之后部分的字符串
 *
 * @param string    字符串
 * @param fromIndex 切割开始的位置（包括）
 * @return 切割后后剩余的后半部分字符串
 */
StringUtil.subSuf(CharSequence string, int fromIndex);
```

## indexOf
```java
/**
 * 指定范围内查找指定字符
 *
 * @param str        字符串
 * @param searchChar 被查找的字符
 * @return 位置
 */
StringUtil.indexOf(CharSequence str, char searchChar);
```

## indexOf
```java
/**
 * 指定范围内查找指定字符
 *
 * @param str        字符串
 * @param searchChar 被查找的字符
 * @param start      起始位置，如果小于0，从0开始查找
 * @return 位置
 */
StringUtil.indexOf(CharSequence str, char searchChar, int start);
```

## indexOf
```java
/**
 * 指定范围内查找指定字符
 *
 * @param str        字符串
 * @param searchChar 被查找的字符
 * @param start      起始位置，如果小于0，从0开始查找
 * @param end        终止位置，如果超过str.length()则默认查找到字符串末尾
 * @return 位置
 */
StringUtil.indexOf(CharSequence str, char searchChar, int start, int end);
```

## indexOfIgnoreCase
```java
/**
 * 指定范围内查找字符串，忽略大小写

 *
 * <pre>
 * StringUtil.indexOfIgnoreCase(null, *, *)          = -1
 * StringUtil.indexOfIgnoreCase(*, null, *)          = -1
 * StringUtil.indexOfIgnoreCase("", "", 0)           = 0
 * StringUtil.indexOfIgnoreCase("aabaabaa", "A", 0)  = 0
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 0)  = 2
 * StringUtil.indexOfIgnoreCase("aabaabaa", "AB", 0) = 1
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 3)  = 5
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 9)  = -1
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", -1) = 2
 * StringUtil.indexOfIgnoreCase("aabaabaa", "", 2)   = 2
 * StringUtil.indexOfIgnoreCase("abc", "", 9)        = -1
 * </pre>
 *
 * @param str       字符串
 * @param searchStr 需要查找位置的字符串
 * @return 位置
 * @since 3.2.1
 */
StringUtil.indexOfIgnoreCase(CharSequence str, CharSequence searchStr);
```

## indexOfIgnoreCase
```java
/**
 * 指定范围内查找字符串
 *
 * <pre>
 * StringUtil.indexOfIgnoreCase(null, *, *)          = -1
 * StringUtil.indexOfIgnoreCase(*, null, *)          = -1
 * StringUtil.indexOfIgnoreCase("", "", 0)           = 0
 * StringUtil.indexOfIgnoreCase("aabaabaa", "A", 0)  = 0
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 0)  = 2
 * StringUtil.indexOfIgnoreCase("aabaabaa", "AB", 0) = 1
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 3)  = 5
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", 9)  = -1
 * StringUtil.indexOfIgnoreCase("aabaabaa", "B", -1) = 2
 * StringUtil.indexOfIgnoreCase("aabaabaa", "", 2)   = 2
 * StringUtil.indexOfIgnoreCase("abc", "", 9)        = -1
 * </pre>
 *
 * @param str       字符串
 * @param searchStr 需要查找位置的字符串
 * @param fromIndex 起始位置
 * @return 位置
 * @since 3.2.1
 */
StringUtil.indexOfIgnoreCase(CharSequence str, CharSequence searchStr, int fromIndex);
```

## indexOf
```java
/**
 * 指定范围内反向查找字符串
 *
 * @param str        字符串
 * @param searchStr  需要查找位置的字符串
 * @param fromIndex  起始位置
 * @param ignoreCase 是否忽略大小写
 * @return 位置
 * @since 3.2.1
 */
StringUtil.indexOf(CharSequence str, CharSequence searchStr, int fromIndex, boolean ignoreCase);
```

## lastIndexOfIgnoreCase
```java
/**
 * 指定范围内查找字符串，忽略大小写

 *
 * @param str       字符串
 * @param searchStr 需要查找位置的字符串
 * @return 位置
 * @since 3.2.1
 */
StringUtil.lastIndexOfIgnoreCase(CharSequence str, CharSequence searchStr);
```

## lastIndexOfIgnoreCase
```java
/**
 * 指定范围内查找字符串，忽略大小写

 *
 * @param str       字符串
 * @param searchStr 需要查找位置的字符串
 * @param fromIndex 起始位置，从后往前计数
 * @return 位置
 * @since 3.2.1
 */
StringUtil.lastIndexOfIgnoreCase(CharSequence str, CharSequence searchStr, int fromIndex);
```

## lastIndexOf
```java
/**
 * 指定范围内查找字符串

 *
 * @param str        字符串
 * @param searchStr  需要查找位置的字符串
 * @param fromIndex  起始位置，从后往前计数
 * @param ignoreCase 是否忽略大小写
 * @return 位置
 * @since 3.2.1
 */
StringUtil.lastIndexOf(CharSequence str, CharSequence searchStr, int fromIndex, boolean ignoreCase);
```

## ordinalIndexOf
```java
/**
 * 返回字符串 searchStr 在字符串 str 中第 ordinal 次出现的位置。

 * 此方法来自：Apache-Commons-Lang
 * <p>
 * 栗子（*代表任意字符）：
 *
 * <pre>
 * StringUtil.ordinalIndexOf(null, *, *)          = -1
 * StringUtil.ordinalIndexOf(*, null, *)          = -1
 * StringUtil.ordinalIndexOf("", "", *)           = 0
 * StringUtil.ordinalIndexOf("aabaabaa", "a", 1)  = 0
 * StringUtil.ordinalIndexOf("aabaabaa", "a", 2)  = 1
 * StringUtil.ordinalIndexOf("aabaabaa", "b", 1)  = 2
 * StringUtil.ordinalIndexOf("aabaabaa", "b", 2)  = 5
 * StringUtil.ordinalIndexOf("aabaabaa", "ab", 1) = 1
 * StringUtil.ordinalIndexOf("aabaabaa", "ab", 2) = 4
 * StringUtil.ordinalIndexOf("aabaabaa", "", 1)   = 0
 * StringUtil.ordinalIndexOf("aabaabaa", "", 2)   = 0
 * </pre>
 *
 * @param str       被检查的字符串，可以为null
 * @param searchStr 被查找的字符串，可以为null
 * @param ordinal   第几次出现的位置
 * @return 查找到的位置
 * @since 3.2.3
 */
StringUtil.ordinalIndexOf(String str, String searchStr, int ordinal);
```

## isSubEquals
```java
/**
 * 截取两个字符串的不同部分（长度一致），判断截取的子串是否相同

 * 任意一个字符串为null返回false
 *
 * @param str1       第一个字符串
 * @param start1     第一个字符串开始的位置
 * @param str2       第二个字符串
 * @param start2     第二个字符串开始的位置
 * @param length     截取长度
 * @param ignoreCase 是否忽略大小写
 * @return 子串是否相同
 * @since 3.2.1
 */
StringUtil.isSubEquals(CharSequence str1, int start1, CharSequence str2, int start2, int length, boolean ignoreCase);
```

## equals
```java
/**
 * 比较两个字符串（大小写敏感）。
 *
 * <pre>
 * equalsIgnoreCase(null, null)   = true
 * equalsIgnoreCase(null, &quot;abc&quot;)  = false
 * equalsIgnoreCase(&quot;abc&quot;, null)  = false
 * equalsIgnoreCase(&quot;abc&quot;, &quot;abc&quot;) = true
 * equalsIgnoreCase(&quot;abc&quot;, &quot;ABC&quot;) = true
 * </pre>
 *
 * @param str1 要比较的字符串1
 * @param str2 要比较的字符串2
 * @return 如果两个字符串相同，或者都是<code>null</code>，则返回<code>true</code>
 */
StringUtil.equals(CharSequence str1, CharSequence str2);
```

## equalsIgnoreCase
```java
/**
 * 比较两个字符串（大小写不敏感）。
 *
 * <pre>
 * equalsIgnoreCase(null, null)   = true
 * equalsIgnoreCase(null, &quot;abc&quot;)  = false
 * equalsIgnoreCase(&quot;abc&quot;, null)  = false
 * equalsIgnoreCase(&quot;abc&quot;, &quot;abc&quot;) = true
 * equalsIgnoreCase(&quot;abc&quot;, &quot;ABC&quot;) = true
 * </pre>
 *
 * @param str1 要比较的字符串1
 * @param str2 要比较的字符串2
 * @return 如果两个字符串相同，或者都是<code>null</code>，则返回<code>true</code>
 */
StringUtil.equalsIgnoreCase(CharSequence str1, CharSequence str2);
```

## equals
```java
/**
 * 比较两个字符串是否相等。
 *
 * @param str1       要比较的字符串1
 * @param str2       要比较的字符串2
 * @param ignoreCase 是否忽略大小写
 * @return 如果两个字符串相同，或者都是<code>null</code>，则返回<code>true</code>
 * @since 3.2.0
 */
StringUtil.equals(CharSequence str1, CharSequence str2, boolean ignoreCase);
```

## builder
```java
/**
 * 创建StringBuilder对象
 *
 * @return {String}Builder对象
 */
StringUtil.builder();
```

## builder
```java
/**
 * 创建StringBuilder对象
 *
 * @param capacity 初始大小
 * @return {String}Builder对象
 */
StringUtil.builder(int capacity);
```

## builder
```java
/**
 * 创建StringBuilder对象
 *
 * @param strs 初始字符串列表
 * @return {String}Builder对象
 */
StringUtil.builder(CharSequence strs);
```

## appendBuilder
```java
/**
 * 创建StringBuilder对象
 *
 * @param sb   初始StringBuilder
 * @param strs 初始字符串列表
 * @return {String}Builder对象
 */
StringUtil.appendBuilder(StringBuilder sb, CharSequence strs);
```

## getReader
```java
/**
 * 获得StringReader
 *
 * @param str 字符串
 * @return {String}Reader
 */
StringUtil.getReader(CharSequence str);
```

## getWriter
```java
/**
 * 获得StringWriter
 *
 * @return {String}Writer
 */
StringUtil.getWriter();
```

## count
```java
/**
 * 统计指定内容中包含指定字符串的数量

 * 参数为 {@code null} 或者 "" 返回 {@code 0}.
 *
 * <pre>
 * StringUtil.count(null, *)       = 0
 * StringUtil.count("", *)         = 0
 * StringUtil.count("abba", null)  = 0
 * StringUtil.count("abba", "")    = 0
 * StringUtil.count("abba", "a")   = 2
 * StringUtil.count("abba", "ab")  = 1
 * StringUtil.count("abba", "xxx") = 0
 * </pre>
 *
 * @param content      被查找的字符串
 * @param strForSearch 需要查找的字符串
 * @return 查找到的个数
 */
StringUtil.count(CharSequence content, CharSequence strForSearch);
```

## count
```java
/**
 * 统计指定内容中包含指定字符的数量
 *
 * @param content       内容
 * @param charForSearch 被统计的字符
 * @return 包含数量
 */
StringUtil.count(CharSequence content, char charForSearch);
```

## underlineToHump
```java
/**
 * 下划线转驼峰
 *
 * @param para 字符串
 * @return {String}
 */
StringUtil.underlineToHump(String para);
```

## humpToUnderline
```java
/**
 * 驼峰转下划线
 *
 * @param para 字符串
 * @return {String}
 */
StringUtil.humpToUnderline(String para);
```

## lineToHump
```java
/**
 * 横线转驼峰
 *
 * @param para 字符串
 * @return {String}
 */
StringUtil.lineToHump(String para);
```

## humpToLine
```java
/**
 * 驼峰转横线
 *
 * @param para 字符串
 * @return {String}
 */
StringUtil.humpToLine(String para);
```

## isEmpty
```java
/**
 * Check whether the given object (possibly a {@code String}) is empty.
 * This is effectly a shortcut for {@code !hasLength(String)}.
 * <p>This method accepts any Object as an argument, comparing it to
 * {@code null} and the empty String. As a consequence, this method
 * will never return {@code true} for a non-null non-String object.
 * <p>The Object signature is useful for general attribute handling code
 * that commonly deals with Strings but generally has to iterate over
 * Objects since attributes may e.g. be primitive value objects as well.
 * <p><b>Note: If the object is typed to {@code String} upfront, prefer
 * {@link #hasLength(String)} or {@link #hasText(String)} instead.</b>
 * @param str the candidate object (possibly a {@code String})
 * @since 3.2.1
 * @see #hasLength(String)
 * @see #hasText(String)
 */
StringUtil.isEmpty(Object str);
```

## hasLength
```java
/**
 * Check that the given {@code CharSequence} is neither {@code null} nor
 * of length 0.
 * <p>Note: this method returns {@code true} for a {@code CharSequence}
 * that purely consists of whitespace.
 * <p><pre class="code">
 * StringUtils.hasLength(null) = false
 * StringUtils.hasLength("") = false
 * StringUtils.hasLength(" ") = true
 * StringUtils.hasLength("Hello") = true
 * </pre>
 * @param str the {@code CharSequence} to check (may be {@code null})
 * @return {@code true} if the {@code CharSequence} is not {@code null} and has length
 * @see #hasLength(String)
 * @see #hasText(CharSequence)
 */
StringUtil.hasLength(CharSequence str);
```

## hasLength
```java
/**
 * Check that the given {@code String} is neither {@code null} nor of length 0.
 * <p>Note: this method returns {@code true} for a {@code String} that
 * purely consists of whitespace.
 * @param str the {@code String} to check (may be {@code null})
 * @return {@code true} if the {@code String} is not {@code null} and has length
 * @see #hasLength(CharSequence)
 * @see #hasText(String)
 */
StringUtil.hasLength(String str);
```

## hasText
```java
/**
 * Check whether the given {@code CharSequence} contains actual <em>text</em>.
 * <p>More specifically, this method returns {@code true} if the
 * {@code CharSequence} is not {@code null}, its length is greater than
 * 0, and it contains at least one non-whitespace character.
 * <p><pre class="code">
 * StringUtils.hasText(null) = false
 * StringUtils.hasText("") = false
 * StringUtils.hasText(" ") = false
 * StringUtils.hasText("12345") = true
 * StringUtils.hasText(" 12345 ") = true
 * </pre>
 * @param str the {@code CharSequence} to check (may be {@code null})
 * @return {@code true} if the {@code CharSequence} is not {@code null},
 * its length is greater than 0, and it does not contain whitespace only
 * @see #hasText(String)
 * @see #hasLength(CharSequence)
 * @see Character#isWhitespace
 */
StringUtil.hasText(CharSequence str);
```

## hasText
```java
/**
 * Check whether the given {@code String} contains actual <em>text</em>.
 * <p>More specifically, this method returns {@code true} if the
 * {@code String} is not {@code null}, its length is greater than 0,
 * and it contains at least one non-whitespace character.
 * @param str the {@code String} to check (may be {@code null})
 * @return {@code true} if the {@code String} is not {@code null}, its
 * length is greater than 0, and it does not contain whitespace only
 * @see #hasText(CharSequence)
 * @see #hasLength(String)
 * @see Character#isWhitespace
 */
StringUtil.hasText(String str);
```

## containsWhitespace
```java
/**
 * Check whether the given {@code CharSequence} contains any whitespace characters.
 * @param str the {@code CharSequence} to check (may be {@code null})
 * @return {@code true} if the {@code CharSequence} is not empty and
 * contains at least 1 whitespace character
 * @see Character#isWhitespace
 */
StringUtil.containsWhitespace(CharSequence str);
```

## containsWhitespace
```java
/**
 * Check whether the given {@code String} contains any whitespace characters.
 * @param str the {@code String} to check (may be {@code null})
 * @return {@code true} if the {@code String} is not empty and
 * contains at least 1 whitespace character
 * @see #containsWhitespace(CharSequence)
 */
StringUtil.containsWhitespace(String str);
```

## trimWhitespace
```java
/**
 * Trim leading and trailing whitespace from the given {@code String}.
 * @param str the {@code String} to check
 * @return the trimmed {@code String}
 * @see java.lang.Character#isWhitespace
 */
StringUtil.trimWhitespace(String str);
```

## trimAllWhitespace
```java
/**
 * Trim <i>all</i> whitespace from the given {@code String}:
 * leading, trailing, and in between characters.
 * @param str the {@code String} to check
 * @return the trimmed {@code String}
 * @see java.lang.Character#isWhitespace
 */
StringUtil.trimAllWhitespace(String str);
```

## trimLeadingWhitespace
```java
/**
 * Trim leading whitespace from the given {@code String}.
 * @param str the {@code String} to check
 * @return the trimmed {@code String}
 * @see java.lang.Character#isWhitespace
 */
StringUtil.trimLeadingWhitespace(String str);
```

## trimTrailingWhitespace
```java
/**
 * Trim trailing whitespace from the given {@code String}.
 * @param str the {@code String} to check
 * @return the trimmed {@code String}
 * @see java.lang.Character#isWhitespace
 */
StringUtil.trimTrailingWhitespace(String str);
```

## trimLeadingCharacter
```java
/**
 * Trim all occurrences of the supplied leading character from the given {@code String}.
 * @param str the {@code String} to check
 * @param leadingCharacter the leading character to be trimmed
 * @return the trimmed {@code String}
 */
StringUtil.trimLeadingCharacter(String str, char leadingCharacter);
```

## trimTrailingCharacter
```java
/**
 * Trim all occurrences of the supplied trailing character from the given {@code String}.
 * @param str the {@code String} to check
 * @param trailingCharacter the trailing character to be trimmed
 * @return the trimmed {@code String}
 */
StringUtil.trimTrailingCharacter(String str, char trailingCharacter);
```

## startsWithIgnoreCase
```java
/**
 * Test if the given {@code String} starts with the specified prefix,
 * ignoring upper/lower case.
 * @param str the {@code String} to check
 * @param prefix the prefix to look for
 * @see java.lang.String#startsWith
 */
StringUtil.startsWithIgnoreCase(String str, String prefix);
```

## endsWithIgnoreCase
```java
/**
 * Test if the given {@code String} ends with the specified suffix,
 * ignoring upper/lower case.
 * @param str the {@code String} to check
 * @param suffix the suffix to look for
 * @see java.lang.String#endsWith
 */
StringUtil.endsWithIgnoreCase(String str, String suffix);
```

## substringMatch
```java
/**
 * Test whether the given string matches the given substring
 * at the given index.
 * @param str the original string (or StringBuilder)
 * @param index the index in the original string to start matching against
 * @param substring the substring to match at the given index
 */
StringUtil.substringMatch(CharSequence str, int index, CharSequence substring);
```

## countOccurrencesOf
```java
/**
 * Count the occurrences of the substring {@code sub} in string {@code str}.
 * @param str string to search in
 * @param sub string to search for
 */
StringUtil.countOccurrencesOf(String str, String sub);
```

## replace
```java
/**
 * Replace all occurrences of a substring within a string with another string.
 * @param inString {@code String} to examine
 * @param oldPattern {@code String} to replace
 * @param newPattern {@code String} to insert
 * @return a {@code String} with the replacements
 */
StringUtil.replace(String inString, String oldPattern, String newPattern);
```

## delete
```java
/**
 * Delete all occurrences of the given substring.
 * @param inString the original {@code String}
 * @param pattern the pattern to delete all occurrences of
 * @return the resulting {@code String}
 */
StringUtil.delete(String inString, String pattern);
```

## deleteAny
```java
/**
 * Delete any character in a given {@code String}.
 * @param inString the original {@code String}
 * @param charsToDelete a set of characters to delete.
 * E.g. "az\n" will delete 'a's, 'z's and new lines.
 * @return the resulting {@code String}
 */
StringUtil.deleteAny(String inString, String charsToDelete);
```

## quote
```java
/**
 * Quote the given {@code String} with single quotes.
 * @param str the input {@code String} (e.g. "myString")
 * @return the quoted {@code String} (e.g. "'myString'"),
 * or {@code null} if the input was {@code null}
 */
StringUtil.quote(String str);
```

## quoteIfString
```java
/**
 * Turn the given Object into a {@code String} with single quotes
 * if it is a {@code String}; keeping the Object as-is else.
 * @param obj the input Object (e.g. "myString")
 * @return the quoted {@code String} (e.g. "'myString'"),
 * or the input object as-is if not a {@code String}
 */
StringUtil.quoteIfString(Object obj);
```

## unqualify
```java
/**
 * Unqualify a string qualified by a '.' dot character. For example,
 * "this.name.is.qualified", returns "qualified".
 * @param qualifiedName the qualified name
 */
StringUtil.unqualify(String qualifiedName);
```

## unqualify
```java
/**
 * Unqualify a string qualified by a separator character. For example,
 * "this:name:is:qualified" returns "qualified" if using a ':' separator.
 * @param qualifiedName the qualified name
 * @param separator the separator
 */
StringUtil.unqualify(String qualifiedName, char separator);
```

## capitalize
```java
/**
 * Capitalize a {@code String}, changing the first letter to
 * upper case as per {@link Character#toUpperCase(char)}.
 * No other letters are changed.
 * @param str the {@code String} to capitalize
 * @return the capitalized {@code String}
 */
StringUtil.capitalize(String str);
```

## uncapitalize
```java
/**
 * Uncapitalize a {@code String}, changing the first letter to
 * lower case as per {@link Character#toLowerCase(char)}.
 * No other letters are changed.
 * @param str the {@code String} to uncapitalize
 * @return the uncapitalized {@code String}
 */
StringUtil.uncapitalize(String str);
```

## getFilename
```java
/**
 * Extract the filename from the given Java resource path,
 * e.g. {@code "mypath/myfile.txt" -> "myfile.txt"}.
 * @param path the file path (may be {@code null})
 * @return the extracted filename, or {@code null} if none
 */
StringUtil.getFilename(String path);
```

## getFilenameExtension
```java
/**
 * Extract the filename extension from the given Java resource path,
 * e.g. "mypath/myfile.txt" -> "txt".
 * @param path the file path (may be {@code null})
 * @return the extracted filename extension, or {@code null} if none
 */
StringUtil.getFilenameExtension(String path);
```

## stripFilenameExtension
```java
/**
 * Strip the filename extension from the given Java resource path,
 * e.g. "mypath/myfile.txt" -> "mypath/myfile".
 * @param path the file path
 * @return the path with stripped filename extension
 */
StringUtil.stripFilenameExtension(String path);
```

## applyRelativePath
```java
/**
 * Apply the given relative path to the given Java resource path,
 * assuming standard Java folder separation (i.e. "/" separators).
 * @param path the path to start from (usually a full file path)
 * @param relativePath the relative path to apply
 * (relative to the full file path above)
 * @return the full file path that results from applying the relative path
 */
StringUtil.applyRelativePath(String path, String relativePath);
```

## cleanPath
```java
/**
 * Normalize the path by suppressing sequences like "path/.." and
 * inner simple dots.
 * <p>The result is convenient for path comparison. For other uses,
 * notice that Windows separators ("\") are replaced by simple slashes.
 * @param path the original path
 * @return the normalized path
 */
StringUtil.cleanPath(String path);
```

## pathEquals
```java
/**
 * Compare two paths after normalization of them.
 * @param path1 first path for comparison
 * @param path2 second path for comparison
 * @return whether the two paths are equivalent after normalization
 */
StringUtil.pathEquals(String path1, String path2);
```

## uriDecode
```java
/**
 * Decode the given encoded URI component value. Based on the following rules:
 * <ul>
 * <li>Alphanumeric characters {@code "a"} through {@code "z"}, {@code "A"} through {@code "Z"},
 * and {@code "0"} through {@code "9"} stay the same.</li>
 * <li>Special characters {@code "-"}, {@code "_"}, {@code "."}, and {@code "*"} stay the same.</li>
 * <li>A sequence "{@code %<i>xy</i>}" is interpreted as a hexadecimal representation of the character.</li>
 * </ul>
 * @param source the encoded String
 * @param charset the character set
 * @return the decoded value
 * @throws IllegalArgumentException when the given source contains invalid encoded sequences
 * @since 5.0
 * @see java.net.URLDecoder#decode(String, String)
 */
StringUtil.uriDecode(String source, Charset charset);
```

## parseLocale
```java
/**
 * Parse the given {@code String} value into a {@link Locale}, accepting
 * the {@link Locale#toString} format as well as BCP 47 language tags.
 * @param localeValue the locale value: following either {@code Locale's}
 * {@code toString()} format ("en", "en_UK", etc), also accepting spaces as
 * separators (as an alternative to underscores), or BCP 47 (e.g. "en-UK")
 * as specified by {@link Locale#forLanguageTag} on Java 7+
 * @return a corresponding {@code Locale} instance, or {@code null} if none
 * @throws IllegalArgumentException in case of an invalid locale specification
 * @since 5.0.4
 * @see #parseLocaleString
 * @see Locale#forLanguageTag
 */
StringUtil.parseLocale(String localeValue);
```

## parseLocaleString
```java
/**
 * Parse the given {@code String} representation into a {@link Locale}.
 * <p>For many parsing scenarios, this is an inverse operation of
 * {@link Locale#toString Locale's toString}, in a lenient sense.
 * This method does not aim for strict {@code Locale} design compliance;
 * it is rather specifically tailored for typical Spring parsing needs.
 * <p><b>Note: This delegate does not accept the BCP 47 language tag format.
 * Please use {@link #parseLocale} for lenient parsing of both formats.</b>
 * @param localeString the locale {@code String}: following {@code Locale's}
 * {@code toString()} format ("en", "en_UK", etc), also accepting spaces as
 * separators (as an alternative to underscores)
 * @return a corresponding {@code Locale} instance, or {@code null} if none
 * @throws IllegalArgumentException in case of an invalid locale specification
 */
StringUtil.parseLocaleString(String localeString);
```

## toLanguageTag
```java
/**
 * Determine the RFC 3066 compliant language tag,
 * as used for the HTTP "Accept-Language" header.
 * @param locale the Locale to transform to a language tag
 * @return the RFC 3066 compliant language tag as {@code String}
 * @deprecated as of 5.0.4, in favor of {@link Locale#toLanguageTag()}
 */
StringUtil.toLanguageTag(Locale locale);
```

## parseTimeZoneString
```java
/**
 * Parse the given {@code timeZoneString} value into a {@link TimeZone}.
 * @param timeZoneString the time zone {@code String}, following {@link TimeZone#getTimeZone(String)}
 * but throwing {@link IllegalArgumentException} in case of an invalid time zone specification
 * @return a corresponding {@link TimeZone} instance
 * @throws IllegalArgumentException in case of an invalid time zone specification
 */
StringUtil.parseTimeZoneString(String timeZoneString);
```

## toStringArray
```java
/**
 * Copy the given {@link Collection} into a {@code String} array.
 * <p>The {@code Collection} must contain {@code String} elements only.
 * @param collection the {@code Collection} to copy
 * (potentially {@code null} or empty)
 * @return the resulting {@code String} array
 */
StringUtil.toStringArray(Collection<String> collection);
```

## toStringArray
```java
/**
 * Copy the given {@link Enumeration} into a {@code String} array.
 * <p>The {@code Enumeration} must contain {@code String} elements only.
 * @param enumeration the {@code Enumeration} to copy
 * (potentially {@code null} or empty)
 * @return the resulting {@code String} array
 */
StringUtil.toStringArray(Enumeration<String> enumeration);
```

## addStringToArray
```java
/**
 * Append the given {@code String} to the given {@code String} array,
 * returning a new array consisting of the input array contents plus
 * the given {@code String}.
 * @param array the array to append to (can be {@code null})
 * @param str the {@code String} to append
 * @return the new array (never {@code null})
 */
StringUtil.addStringToArray(String[] array, String str);
```

## concatenateStringArrays
```java
/**
 * Concatenate the given {@code String} arrays into one,
 * with overlapping array elements included twice.
 * <p>The order of elements in the original arrays is preserved.
 * @param array1 the first array (can be {@code null})
 * @param array2 the second array (can be {@code null})
 * @return the new array ({@code null} if both given arrays were {@code null})
 */
StringUtil.concatenateStringArrays(String[] array1, String[] array2);
```

## mergeStringArrays
```java
/**
 * Merge the given {@code String} arrays into one, with overlapping
 * array elements only included once.
 * <p>The order of elements in the original arrays is preserved
 * (with the exception of overlapping elements, which are only
 * included on their first occurrence).
 * @param array1 the first array (can be {@code null})
 * @param array2 the second array (can be {@code null})
 * @return the new array ({@code null} if both given arrays were {@code null})
 * @deprecated as of 4.3.15, in favor of manual merging via {@link LinkedHashSet}
 * (with every entry included at most once, even entries within the first array)
 */
StringUtil.mergeStringArrays(String[] array1, String[] array2);
```

## sortStringArray
```java
/**
 * Sort the given {@code String} array if necessary.
 * @param array the original array (potentially empty)
 * @return the array in sorted form (never {@code null})
 */
StringUtil.sortStringArray(String[] array);
```

## trimArrayElements
```java
/**
 * Trim the elements of the given {@code String} array,
 * calling {@code String.trim()} on each of them.
 * @param array the original {@code String} array (potentially empty)
 * @return the resulting array (of the same size) with trimmed elements
 */
StringUtil.trimArrayElements(String[] array);
```

## removeDuplicateStrings
```java
/**
 * Remove duplicate strings from the given array.
 * <p>As of 4.2, it preserves the original order, as it uses a {@link LinkedHashSet}.
 * @param array the {@code String} array (potentially empty)
 * @return an array without duplicates, in natural sort order
 */
StringUtil.removeDuplicateStrings(String[] array);
```

## split
```java
/**
 * Split a {@code String} at the first occurrence of the delimiter.
 * Does not include the delimiter in the result.
 * @param toSplit the string to split (potentially {@code null} or empty)
 * @param delimiter to split the string up with (potentially {@code null} or empty)
 * @return a two element array with index 0 being before the delimiter, and
 * index 1 being after the delimiter (neither element includes the delimiter);
 * or {@code null} if the delimiter wasn't found in the given input {@code String}
 */
StringUtil.split(String toSplit, String delimiter);
```

## splitArrayElementsIntoProperties
```java
/**
 * Take an array of strings and split each element based on the given delimiter.
 * A {@code Properties} instance is then generated, with the left of the delimiter
 * providing the key, and the right of the delimiter providing the value.
 * <p>Will trim both the key and value before adding them to the {@code Properties}.
 * @param array the array to process
 * @param delimiter to split each element using (typically the equals symbol)
 * @return a {@code Properties} instance representing the array contents,
 * or {@code null} if the array to process was {@code null} or empty
 */
StringUtil.splitArrayElementsIntoProperties(String[] array, String delimiter);
```

## splitArrayElementsIntoProperties
```java
/**
 * Take an array of strings and split each element based on the given delimiter.
 * A {@code Properties} instance is then generated, with the left of the
 * delimiter providing the key, and the right of the delimiter providing the value.
 * <p>Will trim both the key and value before adding them to the
 * {@code Properties} instance.
 * @param array the array to process
 * @param delimiter to split each element using (typically the equals symbol)
 * @param charsToDelete one or more characters to remove from each element
 * prior to attempting the split operation (typically the quotation mark
 * symbol), or {@code null} if no removal should occur
 * @return a {@code Properties} instance representing the array contents,
 * or {@code null} if the array to process was {@code null} or empty
 */
StringUtil.splitArrayElementsIntoProperties(String[] array, String delimiter, String charsToDelete);
```

## tokenizeToStringArray
```java
/**
 * Tokenize the given {@code String} into a {@code String} array via a
 * {@link StringTokenizer}.
 * <p>Trims tokens and omits empty tokens.
 * <p>The given {@code delimiters} string can consist of any number of
 * delimiter characters. Each of those characters can be used to separate
 * tokens. A delimiter is always a single character; for multi-character
 * delimiters, consider using {@link #delimitedListToStringArray}.
 * @param str the {@code String} to tokenize (potentially {@code null} or empty)
 * @param delimiters the delimiter characters, assembled as a {@code String}
 * (each of the characters is individually considered as a delimiter)
 * @return an array of the tokens
 * @see java.util.StringTokenizer
 * @see String#trim()
 * @see #delimitedListToStringArray
 */
StringUtil.tokenizeToStringArray(String str, String delimiters);
```

## tokenizeToStringArray
```java
/**
 * Tokenize the given {@code String} into a {@code String} array via a
 * {@link StringTokenizer}.
 * <p>The given {@code delimiters} string can consist of any number of
 * delimiter characters. Each of those characters can be used to separate
 * tokens. A delimiter is always a single character; for multi-character
 * delimiters, consider using {@link #delimitedListToStringArray}.
 * @param str the {@code String} to tokenize (potentially {@code null} or empty)
 * @param delimiters the delimiter characters, assembled as a {@code String}
 * (each of the characters is individually considered as a delimiter)
 * @param trimTokens trim the tokens via {@link String#trim()}
 * @param ignoreEmptyTokens omit empty tokens from the result array
 * (only applies to tokens that are empty after trimming; StringTokenizer
 * will not consider subsequent delimiters as token in the first place).
 * @return an array of the tokens
 * @see java.util.StringTokenizer
 * @see String#trim()
 * @see #delimitedListToStringArray
 */
StringUtil.tokenizeToStringArray(String str, String delimiters, boolean trimTokens, boolean ignoreEmptyTokens);
```

## delimitedListToStringArray
```java
/**
 * Take a {@code String} that is a delimited list and convert it into a
 * {@code String} array.
 * <p>A single {@code delimiter} may consist of more than one character,
 * but it will still be considered as a single delimiter string, rather
 * than as bunch of potential delimiter characters, in contrast to
 * {@link #tokenizeToStringArray}.
 * @param str the input {@code String} (potentially {@code null} or empty)
 * @param delimiter the delimiter between elements (this is a single delimiter,
 * rather than a bunch individual delimiter characters)
 * @return an array of the tokens in the list
 * @see #tokenizeToStringArray
 */
StringUtil.delimitedListToStringArray(String str, String delimiter);
```

## delimitedListToStringArray
```java
/**
 * Take a {@code String} that is a delimited list and convert it into
 * a {@code String} array.
 * <p>A single {@code delimiter} may consist of more than one character,
 * but it will still be considered as a single delimiter string, rather
 * than as bunch of potential delimiter characters, in contrast to
 * {@link #tokenizeToStringArray}.
 * @param str the input {@code String} (potentially {@code null} or empty)
 * @param delimiter the delimiter between elements (this is a single delimiter,
 * rather than a bunch individual delimiter characters)
 * @param charsToDelete a set of characters to delete; useful for deleting unwanted
 * line breaks: e.g. "\r\n\f" will delete all new lines and line feeds in a {@code String}
 * @return an array of the tokens in the list
 * @see #tokenizeToStringArray
 */
StringUtil.delimitedListToStringArray(String str, String delimiter, String charsToDelete);
```

## commaDelimitedListToStringArray
```java
/**
 * Convert a comma delimited list (e.g., a row from a CSV file) into an
 * array of strings.
 * @param str the input {@code String} (potentially {@code null} or empty)
 * @return an array of strings, or the empty array in case of empty input
 */
StringUtil.commaDelimitedListToStringArray(String str);
```

## commaDelimitedListToSet
```java
/**
 * Convert a comma delimited list (e.g., a row from a CSV file) into a set.
 * <p>Note that this will suppress duplicates, and as of 4.2, the elements in
 * the returned set will preserve the original order in a {@link LinkedHashSet}.
 * @param str the input {@code String} (potentially {@code null} or empty)
 * @return a set of {@code String} entries in the list
 * @see #removeDuplicateStrings(String[])
 */
StringUtil.commaDelimitedListToSet(String str);
```

## collectionToDelimitedString
```java
/**
 * Convert a {@link Collection} to a delimited {@code String} (e.g. CSV).
 * <p>Useful for {@code toString()} implementations.
 * @param coll the {@code Collection} to convert (potentially {@code null} or empty)
 * @param delim the delimiter to use (typically a ",")
 * @param prefix the {@code String} to start each element with
 * @param suffix the {@code String} to end each element with
 * @return the delimited {@code String}
 */
StringUtil.collectionToDelimitedString(Collection<?> coll, String delim, String prefix, String suffix);
```

## collectionToDelimitedString
```java
/**
 * Convert a {@code Collection} into a delimited {@code String} (e.g. CSV).
 * <p>Useful for {@code toString()} implementations.
 * @param coll the {@code Collection} to convert (potentially {@code null} or empty)
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
StringUtil.collectionToDelimitedString(Collection<?> coll, String delim);
```

## collectionToCommaDelimitedString
```java
/**
 * Convert a {@code Collection} into a delimited {@code String} (e.g., CSV).
 * <p>Useful for {@code toString()} implementations.
 * @param coll the {@code Collection} to convert (potentially {@code null} or empty)
 * @return the delimited {@code String}
 */
StringUtil.collectionToCommaDelimitedString(Collection<?> coll);
```

## arrayToDelimitedString
```java
/**
 * Convert a {@code String} array into a delimited {@code String} (e.g. CSV).
 * <p>Useful for {@code toString()} implementations.
 * @param arr the array to display (potentially {@code null} or empty)
 * @param delim the delimiter to use (typically a ",")
 * @return the delimited {@code String}
 */
StringUtil.arrayToDelimitedString(Object[] arr, String delim);
```

## arrayToCommaDelimitedString
```java
/**
 * Convert a {@code String} array into a comma delimited {@code String}
 * (i.e., CSV).
 * <p>Useful for {@code toString()} implementations.
 * @param arr the array to display (potentially {@code null} or empty)
 * @return the delimited {@code String}
 */
StringUtil.arrayToCommaDelimitedString(Object[] arr);
```

