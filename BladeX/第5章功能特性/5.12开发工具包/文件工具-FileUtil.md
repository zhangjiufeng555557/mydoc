#  文件工具类
**类名：** `FileUtil`

## accept
```java
/**
 */
FileUtil fileUtil = new FileUtil();
fileUtil.accept(File pathname);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param path 路径
 * @return 文件集合
 */
FileUtil.list(String path);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param path   路径
 * @param fileNamePattern 文件名 * 号
 * @return 文件集合
 */
FileUtil.list(String path, String fileNamePattern);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param path   路径
 * @param filter 文件过滤
 * @return 文件集合
 */
FileUtil.list(String path, FileFilter filter);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param file 文件
 * @return 文件集合
 */
FileUtil.list(File file);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param file   文件
 * @param fileNamePattern Spring AntPathMatcher 规则
 * @return 文件集合
 */
FileUtil.list(File file, String fileNamePattern);
```

## list
```java
/**
 * 扫描目录下的文件
 *
 * @param file   文件
 * @param filter 文件过滤
 * @return 文件集合
 */
FileUtil.list(File file, FileFilter filter);
```

## getFileExtension
```java
/**
 * 获取文件后缀名
 * @param fullName 文件全名
 * @return {String}
 */
FileUtil.getFileExtension(String fullName);
```

## getNameWithoutExtension
```java
/**
 * 获取文件名，去除后缀名
 * @param file 文件
 * @return {String}
 */
FileUtil.getNameWithoutExtension(String file);
```

## getTempDirPath
```java
/**
 * Returns the path to the system temporary directory.
 *
 * @return the path to the system temporary directory.
 */
FileUtil.getTempDirPath();
```

## getTempDir
```java
/**
 * Returns a {@link File} representing the system temporary directory.
 *
 * @return the system temporary directory.
 */
FileUtil.getTempDir();
```

## readToString
```java
/**
 * Reads the contents of a file into a String.
 * The file is always closed.
 *
 * @param file the file to read, must not be {@code null}
 * @return the file contents, never {@code null}
 */
FileUtil.readToString(File file);
```

## readToString
```java
/**
 * Reads the contents of a file into a String.
 * The file is always closed.
 *
 * @param file     the file to read, must not be {@code null}
 * @param encoding the encoding to use, {@code null} means platform default
 * @return the file contents, never {@code null}
 */
FileUtil.readToString(File file, Charset encoding);
```

## readToByteArray
```java
/**
 * Reads the contents of a file into a String.
 * The file is always closed.
 *
 * @param file     the file to read, must not be {@code null}
 * @return the file contents, never {@code null}
 */
FileUtil.readToByteArray(File file);
```

## writeToFile
```java
/**
 * Writes a String to a file creating the file if it does not exist.
 *
 * @param file the file to write
 * @param data the content to write to the file
 */
FileUtil.writeToFile(File file, String data);
```

## writeToFile
```java
/**
 * Writes a String to a file creating the file if it does not exist.
 *
 * @param file   the file to write
 * @param data   the content to write to the file
 * @param append if {@code true}, then the String will be added to the
 *               end of the file rather than overwriting
 */
FileUtil.writeToFile(File file, String data, boolean append);
```

## writeToFile
```java
/**
 * Writes a String to a file creating the file if it does not exist.
 *
 * @param file     the file to write
 * @param data     the content to write to the file
 * @param encoding the encoding to use, {@code null} means platform default
 */
FileUtil.writeToFile(File file, String data, Charset encoding);
```

## writeToFile
```java
/**
 * Writes a String to a file creating the file if it does not exist.
 *
 * @param file     the file to write
 * @param data     the content to write to the file
 * @param encoding the encoding to use, {@code null} means platform default
 * @param append   if {@code true}, then the String will be added to the
 *                 end of the file rather than overwriting
 */
FileUtil.writeToFile(File file, String data, Charset encoding, boolean append);
```

## toFile
```java
/**
 * 转成file
 * @param multipartFile MultipartFile
 * @param file File
 */
FileUtil.toFile(MultipartFile multipartFile, File file);
```

## toFile
```java
/**
 * 转成file
 * @param in InputStream
 * @param file File
 */
FileUtil.toFile(InputStream in, File file);
```

## moveFile
```java
/**
 * Moves a file.
 * <p>
 * When the destination file is on another file system, do a "copy and delete".
 *
 * @param srcFile  the file to be moved
 * @param destFile the destination file
 * @throws NullPointerException if source or destination is {@code null}
 * @throws IOException          if source or destination is invalid
 * @throws IOException          if an IO error occurs moving the file
 */
FileUtil.moveFile(File srcFile, File destFile);
```

## deleteQuietly
```java
/**
 * Deletes a file, never throwing an exception. If file is a directory, delete it and all sub-directories.
 * <p>
 * The difference between File.delete() and this method are:
 * <ul>
 * <li>A directory to be deleted does not have to be empty.</li>
 * <li>No exceptions are thrown when a file or directory cannot be deleted.</li>
 * </ul>
 *
 * @param file file or directory to delete, can be {@code null}
 * @return {@code true} if the file or directory was deleted, otherwise
 * {@code false}
 */
FileUtil.deleteQuietly(File file);
```

## copy
```java
/**
 * Copy the contents of the given input File to the given output File.
 * @param in the file to copy from
 * @param out the file to copy to
 * @return the number of bytes copied
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(File in, File out);
```

## copy
```java
/**
 * Copy the contents of the given byte array to the given output File.
 * @param in the byte array to copy from
 * @param out the file to copy to
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(byte[] in, File out);
```

## copyToByteArray
```java
/**
 * Copy the contents of the given input File into a new byte array.
 * @param in the file to copy from
 * @return the new byte array that has been copied to
 * @throws IOException in case of I/O errors
 */
FileUtil.copyToByteArray(File in);
```

## copy
```java
/**
 * Copy the contents of the given InputStream to the given OutputStream.
 * Closes both streams when done.
 * @param in the stream to copy from
 * @param out the stream to copy to
 * @return the number of bytes copied
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(InputStream in, OutputStream out);
```

## copy
```java
/**
 * Copy the contents of the given byte array to the given OutputStream.
 * Closes the stream when done.
 * @param in the byte array to copy from
 * @param out the OutputStream to copy to
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(byte[] in, OutputStream out);
```

## copyToByteArray
```java
/**
 * Copy the contents of the given InputStream into a new byte array.
 * Closes the stream when done.
 * @param in the stream to copy from (may be {@code null} or empty)
 * @return the new byte array that has been copied to (possibly empty)
 * @throws IOException in case of I/O errors
 */
FileUtil.copyToByteArray(InputStream in);
```

## copy
```java
/**
 * Copy the contents of the given Reader to the given Writer.
 * Closes both when done.
 * @param in the Reader to copy from
 * @param out the Writer to copy to
 * @return the number of characters copied
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(Reader in, Writer out);
```

## copy
```java
/**
 * Copy the contents of the given String to the given output Writer.
 * Closes the writer when done.
 * @param in the String to copy from
 * @param out the Writer to copy to
 * @throws IOException in case of I/O errors
 */
FileUtil.copy(String in, Writer out);
```

## copyToString
```java
/**
 * Copy the contents of the given Reader into a String.
 * Closes the reader when done.
 * @param in the reader to copy from (may be {@code null} or empty)
 * @return the String that has been copied to (possibly empty)
 * @throws IOException in case of I/O errors
 */
FileUtil.copyToString(Reader in);
```

