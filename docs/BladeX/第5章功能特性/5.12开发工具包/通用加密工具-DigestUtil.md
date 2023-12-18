#  通用加密工具类继承Spring DigestUtils拓展封装
**类名：** `DigestUtil`

## md5Hex
```java
/**
 * Calculates the MD5 digest and returns the value as a 32 character hex string.
 *
 * @param data Data to digest
 * @return MD5 digest as a hex string
 */
DigestUtil.md5Hex(String data);
```

## md5Hex
```java
/**
 * Return a hexadecimal string representation of the MD5 digest of the given bytes.
 *
 * @param bytes the bytes to calculate the digest over
 * @return a hexadecimal digest string
 */
DigestUtil.md5Hex(byte[] bytes);
```

## sha1Hex
```java
/**
 * sha1Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha1Hex(String data);
```

## sha1Hex
```java
/**
 * sha1Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha1Hex(byte[] bytes);
```

## sha224Hex
```java
/**
 * SHA224Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha224Hex(String data);
```

## sha224Hex
```java
/**
 * SHA224Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha224Hex(byte[] bytes);
```

## sha256Hex
```java
/**
 * sha256Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha256Hex(String data);
```

## sha256Hex
```java
/**
 * sha256Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha256Hex(byte[] bytes);
```

## sha384Hex
```java
/**
 * sha384Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha384Hex(String data);
```

## sha384Hex
```java
/**
 * sha384Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha384Hex(byte[] bytes);
```

## sha512Hex
```java
/**
 * sha512Hex
 *
 * @param data Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha512Hex(String data);
```

## sha512Hex
```java
/**
 * sha512Hex
 *
 * @param bytes Data to digest
 * @return digest as a hex string
 */
DigestUtil.sha512Hex(byte[] bytes);
```

## digestHex
```java
/**
 * digest Hex
 *
 * @param algorithm 算法
 * @param bytes     Data to digest
 * @return digest as a hex string
 */
DigestUtil.digestHex(String algorithm, byte[] bytes);
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
DigestUtil.hmacMd5Hex(String data, String key);
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
DigestUtil.hmacMd5Hex(byte[] bytes, String key);
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
DigestUtil.hmacSha1Hex(String data, String key);
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
DigestUtil.hmacSha1Hex(byte[] bytes, String key);
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
DigestUtil.hmacSha224Hex(String data, String key);
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
DigestUtil.hmacSha224Hex(byte[] bytes, String key);
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
DigestUtil.hmacSha256Hex(String data, String key);
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
DigestUtil.hmacSha256Hex(byte[] bytes, String key);
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
DigestUtil.hmacSha384Hex(String data, String key);
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
DigestUtil.hmacSha384Hex(byte[] bytes, String key);
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
DigestUtil.hmacSha512Hex(String data, String key);
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
DigestUtil.hmacSha512Hex(byte[] bytes, String key);
```

## digestHMacHex
```java
/**
 * digest HMac Hex
 *
 * @param algorithm 算法
 * @param bytes     Data to digest
 * @return digest as a hex string
 */
DigestUtil.digestHMacHex(String algorithm, byte[] bytes, String key);
```

## encodeHex
```java
/**
 * encode Hex
 *
 * @param bytes Data to Hex
 * @return bytes as a hex string
 */
DigestUtil.encodeHex(byte[] bytes);
```

## decodeHex
```java
/**
 * decode Hex
 *
 * @param hexStr Hex string
 * @return decode hex to bytes
 */
DigestUtil.decodeHex(String hexStr);
```

## slowEquals
```java
/**
 * 比较字符串，避免字符串因为过长，产生耗时
 *
 * @param a String
 * @param b String
 * @return 是否相同
 */
DigestUtil.slowEquals(String a, String b);
```

## slowEquals
```java
/**
 * 比较 byte 数组，避免字符串因为过长，产生耗时
 *
 * @param a byte array
 * @param b byte array
 * @return 是否相同
 */
DigestUtil.slowEquals(byte[] a, byte[] b);
```

## hex
```java
/**
 * 自定义加密 将前端传递的密码再次加密
 *
 * @param data 数据
 * @return {String}
 */
DigestUtil.hex(String data);
```

## encrypt
```java
/**
 * 用户密码加密规则 先MD5再SHA1
 *
 * @param data 数据
 * @return {String}
 */
DigestUtil.encrypt(String data);
```

