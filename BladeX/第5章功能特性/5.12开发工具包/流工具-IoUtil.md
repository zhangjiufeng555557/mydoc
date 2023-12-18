#  流工具类
**类名：** `IoUtil`

## closeQuietly
```java
/**
 * closeQuietly
 *
 * @param closeable 自动关闭
 */
IoUtil.closeQuietly(Closeable closeable);
```

## readToString
```java
/**
 * InputStream to String utf-8
 *
 * @param input the <code>InputStream</code> to read from
 * @return the requested String
 */
IoUtil.readToString(InputStream input);
```

## readToString
```java
/**
 * InputStream to String
 *
 * @param input   the <code>InputStream</code> to read from
 * @param charset the <code>Charset</code>
 * @return the requested String
 */
IoUtil.readToString(InputStream input, Charset charset);
```

## readToByteArray
```java
/**
 */
IoUtil.readToByteArray(InputStream input);
```

## write
```java
/**
 * Writes chars from a <code>String</code> to bytes on an
 * <code>OutputStream</code> using the specified character encoding.
 * <p>
 * This method uses {@link String#getBytes(String)}.
 * </p>
 * @param data     the <code>String</code> to write, null ignored
 * @param output   the <code>OutputStream</code> to write to
 * @param encoding the encoding to use, null means platform default
 * @throws NullPointerException if output is null
 * @throws IOException          if an I/O error occurs
 */
IoUtil.write(String data, OutputStream output, Charset encoding);
```

## copyToByteArray
```java
/**
 * Copy the contents of the given InputStream into a new byte array.
 * Leaves the stream open when done.
 * @param in the stream to copy from (may be {@code null} or empty)
 * @return the new byte array that has been copied to (possibly empty)
 * @throws IOException in case of I/O errors
 */
IoUtil.copyToByteArray(InputStream in);
```

## copyToString
```java
/**
 * Copy the contents of the given InputStream into a String.
 * Leaves the stream open when done.
 * @param in the InputStream to copy from (may be {@code null} or empty)
 * @return the String that has been copied to (possibly empty)
 * @throws IOException in case of I/O errors
 */
IoUtil.copyToString(InputStream in, Charset charset);
```

## copy
```java
/**
 * Copy the contents of the given byte array to the given OutputStream.
 * Leaves the stream open when done.
 * @param in the byte array to copy from
 * @param out the OutputStream to copy to
 * @throws IOException in case of I/O errors
 */
IoUtil.copy(byte[] in, OutputStream out);
```

## copy
```java
/**
 * Copy the contents of the given String to the given output OutputStream.
 * Leaves the stream open when done.
 * @param in the String to copy from
 * @param charset the Charset
 * @param out the OutputStream to copy to
 * @throws IOException in case of I/O errors
 */
IoUtil.copy(String in, Charset charset, OutputStream out);
```

## copy
```java
/**
 * Copy the contents of the given InputStream to the given OutputStream.
 * Leaves both streams open when done.
 * @param in the InputStream to copy from
 * @param out the OutputStream to copy to
 * @return the number of bytes copied
 * @throws IOException in case of I/O errors
 */
IoUtil.copy(InputStream in, OutputStream out);
```

## copyRange
```java
/**
 * Copy a range of content of the given InputStream to the given OutputStream.
 * <p>If the specified range exceeds the length of the InputStream, this copies
 * up to the end of the stream and returns the actual number of copied bytes.
 * <p>Leaves both streams open when done.
 * @param in the InputStream to copy from
 * @param out the OutputStream to copy to
 * @param start the position to start copying from
 * @param end the position to end copying
 * @return the number of bytes copied
 * @throws IOException in case of I/O errors
 * @since 4.3
 */
IoUtil.copyRange(InputStream in, OutputStream out, long start, long end);
```

## drain
```java
/**
 * Drain the remaining content of the given InputStream.
 * Leaves the InputStream open when done.
 * @param in the InputStream to drain
 * @return the number of bytes read
 * @throws IOException in case of I/O errors
 * @since 4.3
 */
IoUtil.drain(InputStream in);
```

## emptyInput
```java
/**
 * Return an efficient empty {@link InputStream}.
 * @return a {@link ByteArrayInputStream} based on an empty byte array
 * @since 4.2.2
 */
IoUtil.emptyInput();
```

## nonClosing
```java
/**
 * Return a variant of the given {@link InputStream} where calling
 * {@link InputStream#close() close()} has no effect.
 * @param in the InputStream to decorate
 * @return a version of the InputStream that ignores calls to close
 */
IoUtil.nonClosing(InputStream in);
```

## nonClosing
```java
/**
 * Return a variant of the given {@link OutputStream} where calling
 * {@link OutputStream#close() close()} has no effect.
 * @param out the OutputStream to decorate
 * @return a version of the OutputStream that ignores calls to close
 */
IoUtil.nonClosing(OutputStream out);
```

## close
```java
/**
 */
IoUtil ioUtil = new IoUtil();
ioUtil.close();
```

## write
```java
/**
 */
IoUtil ioUtil = new IoUtil();
ioUtil.write(byte[] b, int off, int let);
```

## close
```java
/**
 */
IoUtil ioUtil = new IoUtil();
ioUtil.close();
```

