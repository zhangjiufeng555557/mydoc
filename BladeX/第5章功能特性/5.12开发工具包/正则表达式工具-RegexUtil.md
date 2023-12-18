#  正则表达式工具
**类名：** `RegexUtil`

## match
```java
/**
 * 编译传入正则表达式和字符串去匹配,忽略大小写
 *
 * @param regex        正则
 * @param beTestString 字符串
 * @return {boolean}
 */
RegexUtil.match(String regex, String beTestString);
```

## find
```java
/**
 * 编译传入正则表达式在字符串中寻找，如果匹配到则为true
 *
 * @param regex        正则
 * @param beTestString 字符串
 * @return {boolean}
 */
RegexUtil.find(String regex, String beTestString);
```

## findResult
```java
/**
 * 编译传入正则表达式在字符串中寻找，如果找到返回第一个结果
 * 找不到返回null
 *
 * @param regex         正则
 * @param beFoundString 字符串
 * @return {boolean}
 */
RegexUtil.findResult(String regex, String beFoundString);
```

