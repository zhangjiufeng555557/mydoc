#  url处理工具类
**类名：** `UrlUtil`

## encodeURL
```java
/**
 * url 编码，同js decodeURIComponent
 *
 * @param source  url
 * @param charset 字符集
 * @return 编码后的url
 */
UrlUtil.encodeURL(String source, Charset charset);
```

## decodeURL
```java
/**
 * url 解码
 *
 * @param source  url
 * @param charset 字符集
 * @return 解码url
 */
UrlUtil.decodeURL(String source, Charset charset);
```

## getPath
```java
/**
 * 获取url路径
 *
 * @param uriStr 路径
 * @return url路径
 */
UrlUtil.getPath(String uriStr);
```

## encodeScheme
```java
/**
 * Encode the given URI scheme with the given encoding.
 * @param scheme the scheme to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded scheme
 */
UrlUtil.encodeScheme(String scheme, String encoding);
```

## encodeScheme
```java
/**
 * Encode the given URI scheme with the given encoding.
 * @param scheme the scheme to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded scheme
 * @since 5.0
 */
UrlUtil.encodeScheme(String scheme, Charset charset);
```

## encodeAuthority
```java
/**
 * Encode the given URI authority with the given encoding.
 * @param authority the authority to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded authority
 */
UrlUtil.encodeAuthority(String authority, String encoding);
```

## encodeAuthority
```java
/**
 * Encode the given URI authority with the given encoding.
 * @param authority the authority to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded authority
 * @since 5.0
 */
UrlUtil.encodeAuthority(String authority, Charset charset);
```

## encodeUserInfo
```java
/**
 * Encode the given URI user info with the given encoding.
 * @param userInfo the user info to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded user info
 */
UrlUtil.encodeUserInfo(String userInfo, String encoding);
```

## encodeUserInfo
```java
/**
 * Encode the given URI user info with the given encoding.
 * @param userInfo the user info to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded user info
 * @since 5.0
 */
UrlUtil.encodeUserInfo(String userInfo, Charset charset);
```

## encodeHost
```java
/**
 * Encode the given URI host with the given encoding.
 * @param host the host to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded host
 */
UrlUtil.encodeHost(String host, String encoding);
```

## encodeHost
```java
/**
 * Encode the given URI host with the given encoding.
 * @param host the host to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded host
 * @since 5.0
 */
UrlUtil.encodeHost(String host, Charset charset);
```

## encodePort
```java
/**
 * Encode the given URI port with the given encoding.
 * @param port the port to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded port
 */
UrlUtil.encodePort(String port, String encoding);
```

## encodePort
```java
/**
 * Encode the given URI port with the given encoding.
 * @param port the port to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded port
 * @since 5.0
 */
UrlUtil.encodePort(String port, Charset charset);
```

## encodePath
```java
/**
 * Encode the given URI path with the given encoding.
 * @param path the path to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded path
 */
UrlUtil.encodePath(String path, String encoding);
```

## encodePath
```java
/**
 * Encode the given URI path with the given encoding.
 * @param path the path to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded path
 * @since 5.0
 */
UrlUtil.encodePath(String path, Charset charset);
```

## encodePathSegment
```java
/**
 * Encode the given URI path segment with the given encoding.
 * @param segment the segment to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded segment
 */
UrlUtil.encodePathSegment(String segment, String encoding);
```

## encodePathSegment
```java
/**
 * Encode the given URI path segment with the given encoding.
 * @param segment the segment to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded segment
 * @since 5.0
 */
UrlUtil.encodePathSegment(String segment, Charset charset);
```

## encodeQuery
```java
/**
 * Encode the given URI query with the given encoding.
 * @param query the query to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded query
 */
UrlUtil.encodeQuery(String query, String encoding);
```

## encodeQuery
```java
/**
 * Encode the given URI query with the given encoding.
 * @param query the query to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded query
 * @since 5.0
 */
UrlUtil.encodeQuery(String query, Charset charset);
```

## encodeQueryParam
```java
/**
 * Encode the given URI query parameter with the given encoding.
 * @param queryParam the query parameter to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded query parameter
 */
UrlUtil.encodeQueryParam(String queryParam, String encoding);
```

## encodeQueryParam
```java
/**
 * Encode the given URI query parameter with the given encoding.
 * @param queryParam the query parameter to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded query parameter
 * @since 5.0
 */
UrlUtil.encodeQueryParam(String queryParam, Charset charset);
```

## encodeFragment
```java
/**
 * Encode the given URI fragment with the given encoding.
 * @param fragment the fragment to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded fragment
 */
UrlUtil.encodeFragment(String fragment, String encoding);
```

## encodeFragment
```java
/**
 * Encode the given URI fragment with the given encoding.
 * @param fragment the fragment to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded fragment
 * @since 5.0
 */
UrlUtil.encodeFragment(String fragment, Charset charset);
```

## encode
```java
/**
 * Variant of {@link #encode(String, Charset)} with a String charset.
 * @param source the String to be encoded
 * @param encoding the character encoding to encode to
 * @return the encoded String
 */
UrlUtil.encode(String source, String encoding);
```

## encode
```java
/**
 * Encode all characters that are either illegal, or have any reserved
 * meaning, anywhere within a URI, as defined in
 * <a href="https://tools.ietf.org/html/rfc3986">RFC 3986</a>.
 * This is useful to ensure that the given String will be preserved as-is
 * and will not have any o impact on the structure or meaning of the URI.
 * @param source the String to be encoded
 * @param charset the character encoding to encode to
 * @return the encoded String
 * @since 5.0
 */
UrlUtil.encode(String source, Charset charset);
```

## encodeUriVariables
```java
/**
 * Convenience method to apply {@link #encode(String, Charset)} to all
 * given URI variable values.
 * @param uriVariables the URI variable values to be encoded
 * @return the encoded String
 * @since 5.0
 */
UrlUtil.encodeUriVariables(Map<String,?> uriVariables);
```

## encodeUriVariables
```java
/**
 * Convenience method to apply {@link #encode(String, Charset)} to all
 * given URI variable values.
 * @param uriVariables the URI variable values to be encoded
 * @return the encoded String
 * @since 5.0
 */
UrlUtil.encodeUriVariables(Object uriVariables);
```

## decode
```java
/**
 * Decode the given encoded URI component.
 * <p>See {@link StringUtils#uriDecode(String, Charset)} for the decoding rules.
 * @param source the encoded String
 * @param encoding the character encoding to use
 * @return the decoded value
 * @throws IllegalArgumentException when the given source contains invalid encoded sequences
 * @see StringUtils#uriDecode(String, Charset)
 * @see java.net.URLDecoder#decode(String, String)
 */
UrlUtil.decode(String source, String encoding);
```

## decode
```java
/**
 * Decode the given encoded URI component.
 * <p>See {@link StringUtils#uriDecode(String, Charset)} for the decoding rules.
 * @param source the encoded String
 * @param charset the character encoding to use
 * @return the decoded value
 * @throws IllegalArgumentException when the given source contains invalid encoded sequences
 * @since 5.0
 * @see StringUtils#uriDecode(String, Charset)
 * @see java.net.URLDecoder#decode(String, String)
 */
UrlUtil.decode(String source, Charset charset);
```

## extractFileExtension
```java
/**
 * Extract the file extension from the given URI path.
 * @param path the URI path (e.g. "/products/index.html")
 * @return the extracted file extension (e.g. "html")
 * @since 4.3.2
 */
UrlUtil.extractFileExtension(String path);
```

