#  资源工具类
**类名：** `ResourceUtil`

## getResource
```java
/**
 * 获取资源
 * <p>
 * 支持一下协议：
 * <p>
 * 1. classpath:
 * 2. file:
 * 3. ftp:
 * 4. http: and https:
 * 5. classpath*:
 * 6. C:/dir1/ and /Users/lcm
 * </p>
 *
 * @param resourceLocation 资源路径
 * @return {Resource}
 * @throws IOException IOException
 */
ResourceUtil.getResource(String resourceLocation);
```

## isUrl
```java
/**
 * Return whether the given resource location is a URL:
 * either a special "classpath" pseudo URL or a standard URL.
 * @param resourceLocation the location String to check
 * @return whether the location qualifies as a URL
 * @see #CLASSPATH_URL_PREFIX
 * @see java.net.URL
 */
ResourceUtil.isUrl(String resourceLocation);
```

## getURL
```java
/**
 * Resolve the given resource location to a {@code java.net.URL}.
 * <p>Does not check whether the URL actually exists; simply returns
 * the URL that the given location would correspond to.
 * @param resourceLocation the resource location to resolve: either a
 * "classpath:" pseudo URL, a "file:" URL, or a plain file path
 * @return a corresponding URL object
 * @throws FileNotFoundException if the resource cannot be resolved to a URL
 */
ResourceUtil.getURL(String resourceLocation);
```

## getFile
```java
/**
 * Resolve the given resource location to a {@code java.io.File},
 * i.e. to a file in the file system.
 * <p>Does not check whether the file actually exists; simply returns
 * the File that the given location would correspond to.
 * @param resourceLocation the resource location to resolve: either a
 * "classpath:" pseudo URL, a "file:" URL, or a plain file path
 * @return a corresponding File object
 * @throws FileNotFoundException if the resource cannot be resolved to
 * a file in the file system
 */
ResourceUtil.getFile(String resourceLocation);
```

## getFile
```java
/**
 * Resolve the given resource URL to a {@code java.io.File},
 * i.e. to a file in the file system.
 * @param resourceUrl the resource URL to resolve
 * @return a corresponding File object
 * @throws FileNotFoundException if the URL cannot be resolved to
 * a file in the file system
 */
ResourceUtil.getFile(URL resourceUrl);
```

## getFile
```java
/**
 * Resolve the given resource URL to a {@code java.io.File},
 * i.e. to a file in the file system.
 * @param resourceUrl the resource URL to resolve
 * @param description a description of the original resource that
 * the URL was created for (for example, a class path location)
 * @return a corresponding File object
 * @throws FileNotFoundException if the URL cannot be resolved to
 * a file in the file system
 */
ResourceUtil.getFile(URL resourceUrl, String description);
```

## getFile
```java
/**
 * Resolve the given resource URI to a {@code java.io.File},
 * i.e. to a file in the file system.
 * @param resourceUri the resource URI to resolve
 * @return a corresponding File object
 * @throws FileNotFoundException if the URL cannot be resolved to
 * a file in the file system
 * @since 2.5
 */
ResourceUtil.getFile(URI resourceUri);
```

## getFile
```java
/**
 * Resolve the given resource URI to a {@code java.io.File},
 * i.e. to a file in the file system.
 * @param resourceUri the resource URI to resolve
 * @param description a description of the original resource that
 * the URI was created for (for example, a class path location)
 * @return a corresponding File object
 * @throws FileNotFoundException if the URL cannot be resolved to
 * a file in the file system
 * @since 2.5
 */
ResourceUtil.getFile(URI resourceUri, String description);
```

## isFileURL
```java
/**
 * Determine whether the given URL points to a resource in the file system,
 * i.e. has protocol "file", "vfsfile" or "vfs".
 * @param url the URL to check
 * @return whether the URL has been identified as a file system URL
 */
ResourceUtil.isFileURL(URL url);
```

## isJarURL
```java
/**
 * Determine whether the given URL points to a resource in a jar file.
 * i.e. has protocol "jar", "war, ""zip", "vfszip" or "wsjar".
 * @param url the URL to check
 * @return whether the URL has been identified as a JAR URL
 */
ResourceUtil.isJarURL(URL url);
```

## isJarFileURL
```java
/**
 * Determine whether the given URL points to a jar file itself,
 * that is, has protocol "file" and ends with the ".jar" extension.
 * @param url the URL to check
 * @return whether the URL has been identified as a JAR file URL
 * @since 4.1
 */
ResourceUtil.isJarFileURL(URL url);
```

## extractJarFileURL
```java
/**
 * Extract the URL for the actual jar file from the given URL
 * (which may point to a resource in a jar file or to a jar file itself).
 * @param jarUrl the original URL
 * @return the URL for the actual jar file
 * @throws MalformedURLException if no valid jar file URL could be extracted
 */
ResourceUtil.extractJarFileURL(URL jarUrl);
```

## extractArchiveURL
```java
/**
 * Extract the URL for the outermost archive from the given jar/war URL
 * (which may point to a resource in a jar file or to a jar file itself).
 * <p>In the case of a jar file nested within a war file, this will return
 * a URL to the war file since that is the one resolvable in the file system.
 * @param jarUrl the original URL
 * @return the URL for the actual jar file
 * @throws MalformedURLException if no valid jar file URL could be extracted
 * @since 4.1.8
 * @see #extractJarFileURL(URL)
 */
ResourceUtil.extractArchiveURL(URL jarUrl);
```

## toURI
```java
/**
 * Create a URI instance for the given URL,
 * replacing spaces with "%20" URI encoding first.
 * @param url the URL to convert into a URI instance
 * @return the URI instance
 * @throws URISyntaxException if the URL wasn't a valid URI
 * @see java.net.URL#toURI()
 */
ResourceUtil.toURI(URL url);
```

## toURI
```java
/**
 * Create a URI instance for the given location String,
 * replacing spaces with "%20" URI encoding first.
 * @param location the location String to convert into a URI instance
 * @return the URI instance
 * @throws URISyntaxException if the location wasn't a valid URI
 */
ResourceUtil.toURI(String location);
```

## useCachesIfNecessary
```java
/**
 * Set the {@link URLConnection#setUseCaches "useCaches"} flag on the
 * given connection, preferring {@code false} but leaving the
 * flag at {@code true} for JNLP based resources.
 * @param con the URLConnection to set the flag on
 */
ResourceUtil.useCachesIfNecessary(URLConnection con);
```

