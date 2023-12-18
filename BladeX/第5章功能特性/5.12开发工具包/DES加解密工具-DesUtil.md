#  DES加解密处理工具
**类名：** `DesUtil`

## genDesKey
```java
/**
 * 生成 des 密钥
 *
 * @return 密钥
 */
DesUtil.genDesKey();
```

## encryptToHex
```java
/**
 * DES加密
 *
 * @param data     byte array
 * @param password 密钥
 * @return des hex
 */
DesUtil.encryptToHex(byte[] data, String password);
```

## encryptToHex
```java
/**
 * DES加密
 *
 * @param data     字符串内容
 * @param password 密钥
 * @return des hex
 */
DesUtil.encryptToHex(String data, String password);
```

## decryptFormHex
```java
/**
 * DES解密
 *
 * @param data     字符串内容
 * @param password 密钥
 * @return des context
 */
DesUtil.decryptFormHex(String data, String password);
```

## encryptToBase64
```java
/**
 * DES加密
 *
 * @param data     byte array
 * @param password 密钥
 * @return des hex
 */
DesUtil.encryptToBase64(byte[] data, String password);
```

## encryptToBase64
```java
/**
 * DES加密
 *
 * @param data     字符串内容
 * @param password 密钥
 * @return des hex
 */
DesUtil.encryptToBase64(String data, String password);
```

## decryptFormBase64
```java
/**
 * DES解密
 *
 * @param data     字符串内容
 * @param password 密钥
 * @return des context
 */
DesUtil.decryptFormBase64(byte[] data, String password);
```

## decryptFormBase64
```java
/**
 * DES解密
 *
 * @param data     字符串内容
 * @param password 密钥
 * @return des context
 */
DesUtil.decryptFormBase64(String data, String password);
```

## encrypt
```java
/**
 * DES加密
 *
 * @param data   内容
 * @param desKey 密钥
 * @return byte array
 */
DesUtil.encrypt(byte[] data, byte[] desKey);
```

## encrypt
```java
/**
 * DES加密
 *
 * @param data   内容
 * @param desKey 密钥
 * @return byte array
 */
DesUtil.encrypt(byte[] data, String desKey);
```

## decrypt
```java
/**
 * DES解密
 *
 * @param data   内容
 * @param desKey 密钥
 * @return byte array
 */
DesUtil.decrypt(byte[] data, byte[] desKey);
```

## decrypt
```java
/**
 * DES解密
 *
 * @param data   内容
 * @param desKey 密钥
 * @return byte array
 */
DesUtil.decrypt(byte[] data, String desKey);
```

