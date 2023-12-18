#  Base64工具
**类名：** `Base64Util`

## encode
```java
/**
 * 编码
 *
 * @param value 字符串
 * @return {String}
 */
Base64Util.encode(String value);
```

## encode
```java
/**
 * 编码
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Base64Util.encode(String value, java.nio.charset.Charset charset);
```

## encodeUrlSafe
```java
/**
 * 编码URL安全
 *
 * @param value 字符串
 * @return {String}
 */
Base64Util.encodeUrlSafe(String value);
```

## encodeUrlSafe
```java
/**
 * 编码URL安全
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Base64Util.encodeUrlSafe(String value, java.nio.charset.Charset charset);
```

## decode
```java
/**
 * 解码
 *
 * @param value 字符串
 * @return {String}
 */
Base64Util.decode(String value);
```

## decode
```java
/**
 * 解码
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Base64Util.decode(String value, java.nio.charset.Charset charset);
```

## decodeUrlSafe
```java
/**
 * 解码URL安全
 *
 * @param value 字符串
 * @return {String}
 */
Base64Util.decodeUrlSafe(String value);
```

## decodeUrlSafe
```java
/**
 * 解码URL安全
 *
 * @param value   字符串
 * @param charset 字符集
 * @return {String}
 */
Base64Util.decodeUrlSafe(String value, java.nio.charset.Charset charset);
```

## encode
```java
/**
 * Base64-encode the given byte array.
 * @param src the original byte array
 * @return the encoded byte array
 */
Base64Util.encode(byte[] src);
```

## decode
```java
/**
 * Base64-decode the given byte array.
 * @param src the encoded byte array
 * @return the original byte array
 */
Base64Util.decode(byte[] src);
```

## encodeUrlSafe
```java
/**
 * Base64-encode the given byte array using the RFC 4648
 * "URL and Filename Safe Alphabet".
 * @param src the original byte array
 * @return the encoded byte array
 * @since 4.2.4
 */
Base64Util.encodeUrlSafe(byte[] src);
```

## decodeUrlSafe
```java
/**
 * Base64-decode the given byte array using the RFC 4648
 * "URL and Filename Safe Alphabet".
 * @param src the encoded byte array
 * @return the original byte array
 * @since 4.2.4
 */
Base64Util.decodeUrlSafe(byte[] src);
```

## encodeToString
```java
/**
 * Base64-encode the given byte array to a String.
 * @param src the original byte array
 * @return the encoded byte array as a UTF-8 String
 */
Base64Util.encodeToString(byte[] src);
```

## decodeFromString
```java
/**
 * Base64-decode the given byte array from an UTF-8 String.
 * @param src the encoded UTF-8 String
 * @return the original byte array
 */
Base64Util.decodeFromString(String src);
```

## encodeToUrlSafeString
```java
/**
 * Base64-encode the given byte array to a String using the RFC 4648
 * "URL and Filename Safe Alphabet".
 * @param src the original byte array
 * @return the encoded byte array as a UTF-8 String
 */
Base64Util.encodeToUrlSafeString(byte[] src);
```

## decodeFromUrlSafeString
```java
/**
 * Base64-decode the given byte array from an UTF-8 String using the RFC 4648
 * "URL and Filename Safe Alphabet".
 * @param src the encoded UTF-8 String
 * @return the original byte array
 */
Base64Util.decodeFromUrlSafeString(String src);
```

