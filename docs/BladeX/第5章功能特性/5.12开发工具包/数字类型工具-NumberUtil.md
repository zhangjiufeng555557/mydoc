#  数字类型工具类
**类名：** `NumberUtil`

## toInt
```java
/**
 * <p>Convert a <code>String</code> to an <code>int</code>, returning
 * <code>zero</code> if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, <code>zero</code> is returned.</p>
 *
 * <pre>
 *   NumberUtil.toInt(null) = 0
 *   NumberUtil.toInt("")   = 0
 *   NumberUtil.toInt("1")  = 1
 * </pre>
 *
 * @param str the string to convert, may be null
 * @return the int represented by the string, or <code>zero</code> if
 * conversion fails
 */
NumberUtil.toInt(String str);
```

## toInt
```java
/**
 * <p>Convert a <code>String</code> to an <code>int</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   NumberUtil.toInt(null, 1) = 1
 *   NumberUtil.toInt("", 1)   = 1
 *   NumberUtil.toInt("1", 0)  = 1
 * </pre>
 *
 * @param str          the string to convert, may be null
 * @param defaultValue the default value
 * @return the int represented by the string, or the default if conversion fails
 */
NumberUtil.toInt(String str, int defaultValue);
```

## toLong
```java
/**
 * <p>Convert a <code>String</code> to a <code>long</code>, returning
 * <code>zero</code> if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, <code>zero</code> is returned.</p>
 *
 * <pre>
 *   NumberUtil.toLong(null) = 0L
 *   NumberUtil.toLong("")   = 0L
 *   NumberUtil.toLong("1")  = 1L
 * </pre>
 *
 * @param str the string to convert, may be null
 * @return the long represented by the string, or <code>0</code> if
 * conversion fails
 */
NumberUtil.toLong(String str);
```

## toLong
```java
/**
 * <p>Convert a <code>String</code> to a <code>long</code>, returning a
 * default value if the conversion fails.</p>
 *
 * <p>If the string is <code>null</code>, the default value is returned.</p>
 *
 * <pre>
 *   NumberUtil.toLong(null, 1L) = 1L
 *   NumberUtil.toLong("", 1L)   = 1L
 *   NumberUtil.toLong("1", 0L)  = 1L
 * </pre>
 *
 * @param str          the string to convert, may be null
 * @param defaultValue the default value
 * @return the long represented by the string, or the default if conversion fails
 */
NumberUtil.toLong(String str, long defaultValue);
```

## toDouble
```java
/**
 * <p>Convert a <code>String</code> to a <code>Double</code>
 *
 * @param value value
 * @return double value
 */
NumberUtil.toDouble(String value);
```

## toDouble
```java
/**
 * <p>Convert a <code>String</code> to a <code>Double</code>
 *
 * @param value value
 * @param defaultValue 默认值
 * @return double value
 */
NumberUtil.toDouble(String value, Double defaultValue);
```

## toFloat
```java
/**
 * <p>Convert a <code>String</code> to a <code>Double</code>
 *
 * @param value value
 * @return double value
 */
NumberUtil.toFloat(String value);
```

## toFloat
```java
/**
 * <p>Convert a <code>String</code> to a <code>Double</code>
 *
 * @param value value
 * @param defaultValue 默认值
 * @return double value
 */
NumberUtil.toFloat(String value, Float defaultValue);
```

## to62String
```java
/**
 * 将 long 转短字符串 为 62 进制
 *
 * @param i 数字
 * @return 短字符串
 */
NumberUtil.to62String(long i);
```

## convertNumberToTargetClass
```java
/**
 * Convert the given number into an instance of the given target class.
 * @param number the number to convert
 * @param targetClass the target class to convert to
 * @return the converted number
 * @throws IllegalArgumentException if the target class is not supported
 * (i.e. not a standard Number subclass as included in the JDK)
 * @see java.lang.Byte
 * @see java.lang.Short
 * @see java.lang.Integer
 * @see java.lang.Long
 * @see java.math.BigInteger
 * @see java.lang.Float
 * @see java.lang.Double
 * @see java.math.BigDecimal
 */
NumberUtil.convertNumberToTargetClass(Number number, Class<T> targetClass);
```

## parseNumber
```java
/**
 * Parse the given {@code text} into a {@link Number} instance of the given
 * target class, using the corresponding {@code decode} / {@code valueOf} method.
 * <p>Trims all whitespace (leading, trailing, and in between characters) from
 * the input {@code String} before attempting to parse the number.
 * <p>Supports numbers in hex format (with leading "0x", "0X", or "#") as well.
 * @param text the text to convert
 * @param targetClass the target class to parse into
 * @return the parsed number
 * @throws IllegalArgumentException if the target class is not supported
 * (i.e. not a standard Number subclass as included in the JDK)
 * @see Byte#decode
 * @see Short#decode
 * @see Integer#decode
 * @see Long#decode
 * @see #decodeBigInteger(String)
 * @see Float#valueOf
 * @see Double#valueOf
 * @see java.math.BigDecimal#BigDecimal(String)
 */
NumberUtil.parseNumber(String text, Class<T> targetClass);
```

## parseNumber
```java
/**
 * Parse the given {@code text} into a {@link Number} instance of the
 * given target class, using the supplied {@link NumberFormat}.
 * <p>Trims the input {@code String} before attempting to parse the number.
 * @param text the text to convert
 * @param targetClass the target class to parse into
 * @param numberFormat the {@code NumberFormat} to use for parsing (if
 * {@code null}, this method falls back to {@link #parseNumber(String, Class)})
 * @return the parsed number
 * @throws IllegalArgumentException if the target class is not supported
 * (i.e. not a standard Number subclass as included in the JDK)
 * @see java.text.NumberFormat#parse
 * @see #convertNumberToTargetClass
 * @see #parseNumber(String, Class)
 */
NumberUtil.parseNumber(String text, Class<T> targetClass, NumberFormat numberFormat);
```

