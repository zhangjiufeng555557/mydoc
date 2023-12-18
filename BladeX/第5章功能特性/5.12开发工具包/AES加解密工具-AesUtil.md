#  完全兼容微信所使用的AES加密工具类
**类名：** `AesUtil`

## genAesKey
```java
/**
 * 获取密钥
 *
 * @return {String}
 */
AesUtil.genAesKey();
```

## encrypt
```java
/**
 * 加密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.encrypt(String content, String aesTextKey);
```

## encrypt
```java
/**
 * 加密
 *
 * @param content    文本内容
 * @param charset    编码
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.encrypt(String content, Charset charset, String aesTextKey);
```

## encrypt
```java
/**
 * 加密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.encrypt(byte[] content, String aesTextKey);
```

## encryptToHex
```java
/**
 * hex加密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.encryptToHex(String content, String aesTextKey);
```

## encryptToHex
```java
/**
 * hex加密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.encryptToHex(byte[] content, String aesTextKey);
```

## encryptToBase64
```java
/**
 * Base64加密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.encryptToBase64(String content, String aesTextKey);
```

## encryptToBase64
```java
/**
 * Base64加密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.encryptToBase64(byte[] content, String aesTextKey);
```

## decryptFormHexToString
```java
/**
 * hex解密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.decryptFormHexToString(String content, String aesTextKey);
```

## decryptFormHex
```java
/**
 * hex解密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.decryptFormHex(String content, String aesTextKey);
```

## decryptFormHex
```java
/**
 * hex解密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.decryptFormHex(byte[] content, String aesTextKey);
```

## decryptFormBase64ToString
```java
/**
 * Base64解密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.decryptFormBase64ToString(String content, String aesTextKey);
```

## decryptFormBase64
```java
/**
 * Base64解密
 *
 * @param content    文本内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.decryptFormBase64(String content, String aesTextKey);
```

## decryptFormBase64
```java
/**
 * Base64解密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.decryptFormBase64(byte[] content, String aesTextKey);
```

## decryptToString
```java
/**
 * 解密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return {String}
 */
AesUtil.decryptToString(byte[] content, String aesTextKey);
```

## decrypt
```java
/**
 * 解密
 *
 * @param content    内容
 * @param aesTextKey 文本密钥
 * @return byte[]
 */
AesUtil.decrypt(byte[] content, String aesTextKey);
```

## encrypt
```java
/**
 * 解密
 *
 * @param content 内容
 * @param aesKey  密钥
 * @return byte[]
 */
AesUtil.encrypt(byte[] content, byte[] aesKey);
```

## decrypt
```java
/**
 * 加密
 *
 * @param encrypted 内容
 * @param aesKey    密钥
 * @return byte[]
 */
AesUtil.decrypt(byte[] encrypted, byte[] aesKey);
```

