#  RSA加、解密工具
**类名：** `RsaUtil`

## genKeyPair
```java
/**
 * 获取 KeyPair
 *
 * @return KeyPair
 */
RsaUtil.genKeyPair();
```

## genKeyPair
```java
/**
 * 获取 KeyPair
 *
 * @param keySize key size
 * @return KeyPair
 */
RsaUtil.genKeyPair(int keySize);
```

## generatePrivateKey
```java
/**
 * 生成RSA私钥
 *
 * @param modulus N特征值
 * @param exponent d特征值
 * @return {@link PrivateKey}
 */
RsaUtil.generatePrivateKey(String modulus, String exponent);
```

## generatePrivateKey
```java
/**
 * 生成RSA私钥
 *
 * @param modulus N特征值
 * @param exponent d特征值
 * @return {@link PrivateKey}
 */
RsaUtil.generatePrivateKey(BigInteger modulus, BigInteger exponent);
```

## generatePublicKey
```java
/**
 * 生成RSA公钥
 *
 * @param modulus N特征值
 * @param exponent e特征值
 * @return {@link PublicKey}
 */
RsaUtil.generatePublicKey(String modulus, String exponent);
```

## generatePublicKey
```java
/**
 * 生成RSA公钥
 *
 * @param modulus N特征值
 * @param exponent e特征值
 * @return {@link PublicKey}
 */
RsaUtil.generatePublicKey(BigInteger modulus, BigInteger exponent);
```

## getPublicKey
```java
/**
 * 得到公钥
 *
 * @param base64PubKey 密钥字符串（经过base64编码）
 * @return PublicKey
 */
RsaUtil.getPublicKey(String base64PubKey);
```

## getPublicKeyToBase64
```java
/**
 * 得到公钥字符串
 *
 * @param base64PubKey 密钥字符串（经过base64编码）
 * @return PublicKey String
 */
RsaUtil.getPublicKeyToBase64(String base64PubKey);
```

## getPrivateKey
```java
/**
 * 得到私钥
 *
 * @param base64PriKey 密钥字符串（经过base64编码）
 * @return PrivateKey
 */
RsaUtil.getPrivateKey(String base64PriKey);
```

## getKeyString
```java
/**
 * 得到密钥字符串（经过base64编码）
 *
 * @param key key
 * @return base 64 编码后的 key
 */
RsaUtil.getKeyString(Key key);
```

## getPrivateKeyToBase64
```java
/**
 * 得到私钥 base64
 *
 * @param base64PriKey 密钥字符串（经过base64编码）
 * @return PrivateKey String
 */
RsaUtil.getPrivateKeyToBase64(String base64PriKey);
```

## encrypt
```java
/**
 * 共要加密
 *
 * @param base64PublicKey base64 的公钥
 * @param data            待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encrypt(String base64PublicKey, byte[] data);
```

## encrypt
```java
/**
 * 共要加密
 *
 * @param publicKey 公钥
 * @param data      待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encrypt(PublicKey publicKey, byte[] data);
```

## encryptByPrivateKey
```java
/**
 * 私钥加密，用于 qpp 内，公钥解密
 *
 * @param base64PrivateKey base64 的私钥
 * @param data             待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encryptByPrivateKey(String base64PrivateKey, byte[] data);
```

## encryptByPrivateKeyToBase64
```java
/**
 * 私钥加密，加密成 base64 字符串，用于 qpp 内，公钥解密
 *
 * @param base64PrivateKey base64 的私钥
 * @param data             待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encryptByPrivateKeyToBase64(String base64PrivateKey, byte[] data);
```

## encryptByPrivateKey
```java
/**
 * 私钥加密，用于 qpp 内，公钥解密
 *
 * @param privateKey 私钥
 * @param data       待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encryptByPrivateKey(PrivateKey privateKey, byte[] data);
```

## encryptToBase64
```java
/**
 * 公钥加密
 *
 * @param base64PublicKey base64 公钥
 * @param data            待加密的内容
 * @return 加密后的内容
 */
RsaUtil.encryptToBase64(String base64PublicKey, String data);
```

## decrypt
```java
/**
 * 解密
 *
 * @param base64PrivateKey base64 私钥
 * @param data             数据
 * @return 解密后的数据
 */
RsaUtil.decrypt(String base64PrivateKey, byte[] data);
```

## decryptByPublicKey
```java
/**
 * 解密
 *
 * @param base64publicKey base64 公钥
 * @param data            数据
 * @return 解密后的数据
 */
RsaUtil.decryptByPublicKey(String base64publicKey, byte[] data);
```

## decrypt
```java
/**
 * 解密
 *
 * @param privateKey privateKey
 * @param data       数据
 * @return 解密后的数据
 */
RsaUtil.decrypt(PrivateKey privateKey, byte[] data);
```

## decryptByPublicKey
```java
/**
 * 解密
 *
 * @param publicKey PublicKey
 * @param data      数据
 * @return 解密后的数据
 */
RsaUtil.decryptByPublicKey(PublicKey publicKey, byte[] data);
```

## decryptByPublicKeyFromBase64
```java
/**
 * base64 数据解密
 *
 * @param base64PublicKey base64 公钥
 * @param base64Data      base64数据
 * @return 解密后的数据
 */
RsaUtil.decryptByPublicKeyFromBase64(String base64PublicKey, byte[] base64Data);
```

## decryptFromBase64
```java
/**
 * base64 数据解密
 *
 * @param base64PrivateKey base64 私钥
 * @param base64Data       base64数据
 * @return 解密后的数据
 */
RsaUtil.decryptFromBase64(String base64PrivateKey, String base64Data);
```

## decryptFromBase64
```java
/**
 * base64 数据解密
 *
 * @param base64PrivateKey base64 私钥
 * @param base64Data       base64数据
 * @return 解密后的数据
 */
RsaUtil.decryptFromBase64(String base64PrivateKey, byte[] base64Data);
```

## decryptByPublicKeyFromBase64
```java
/**
 * base64 数据解密
 *
 * @param base64PublicKey base64 公钥
 * @param base64Data      base64数据
 * @return 解密后的数据
 */
RsaUtil.decryptByPublicKeyFromBase64(String base64PublicKey, String base64Data);
```

