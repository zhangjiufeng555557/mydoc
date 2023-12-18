#  hex 工具，编解码全用 byte
**类名：** `HexUtil`

## encode
```java
/**
 * encode Hex
 *
 * @param data data to hex
 * @return hex bytes
 */
HexUtil.encode(byte[] data);
```

## encode
```java
/**
 * encode Hex
 *
 * @param data        data to hex
 * @param toLowerCase 是否小写
 * @return hex bytes
 */
HexUtil.encode(byte[] data, boolean toLowerCase);
```

## encodeToString
```java
/**
 * encode Hex
 *
 * @param data        Data to Hex
 * @param toLowerCase 是否小写
 * @return bytes as a hex string
 */
HexUtil.encodeToString(byte[] data, boolean toLowerCase);
```

## encodeToString
```java
/**
 * encode Hex
 *
 * @param data Data to Hex
 * @return bytes as a hex string
 */
HexUtil.encodeToString(byte[] data);
```

## encodeToString
```java
/**
 * encode Hex
 *
 * @param data Data to Hex
 * @return bytes as a hex string
 */
HexUtil.encodeToString(String data);
```

## decode
```java
/**
 * decode Hex
 *
 * @param data Hex data
 * @return decode hex to bytes
 */
HexUtil.decode(String data);
```

## decodeToString
```java
/**
 * encode Hex
 *
 * @param data Data to Hex
 * @return bytes as a hex string
 */
HexUtil.decodeToString(String data);
```

## decode
```java
/**
 * decode Hex
 *
 * @param data Hex data
 * @return decode hex to bytes
 */
HexUtil.decode(byte[] data);
```

