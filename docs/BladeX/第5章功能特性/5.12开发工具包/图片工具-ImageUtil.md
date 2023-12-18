#  图片工具类
**类名：** `ImageUtil`

## toByteArray
```java
/**
 * 转换输入流到byte
 *
 * @param src  源
 * @param type 类型
 * @return byte[]
 * @throws IOException 异常
 */
ImageUtil.toByteArray(BufferedImage src, String type);
```

## readImage
```java
/**
 * 获取图像内容
 *
 * @param srcImageFile 文件路径
 * @return BufferedImage
 */
ImageUtil.readImage(String srcImageFile);
```

## readImage
```java
/**
 * 获取图像内容
 *
 * @param srcImageFile 文件
 * @return BufferedImage
 */
ImageUtil.readImage(File srcImageFile);
```

## readImage
```java
/**
 * 获取图像内容
 *
 * @param srcInputStream 输入流
 * @return BufferedImage
 */
ImageUtil.readImage(InputStream srcInputStream);
```

## readImage
```java
/**
 * 获取图像内容
 *
 * @param url URL地址
 * @return BufferedImage
 */
ImageUtil.readImage(URL url);
```

## zoomScale
```java
/**
 * 缩放图像（按比例缩放）
 *
 * @param src    源图像
 * @param output 输出流
 * @param type   类型
 * @param scale  缩放比例
 * @param flag   缩放选择:true 放大; false 缩小;
 */
ImageUtil.zoomScale(BufferedImage src, OutputStream output, String type, double scale, boolean flag);
```

## zoomFixed
```java
/**
 * 缩放图像（按高度和宽度缩放）
 *
 * @param src       源图像
 * @param output    输出流
 * @param type      类型
 * @param height    缩放后的高度
 * @param width     缩放后的宽度
 * @param bb        比例不对时是否需要补白：true为补白; false为不补白;
 * @param fillColor 填充色，null时为Color.WHITE
 */
ImageUtil.zoomFixed(BufferedImage src, OutputStream output, String type, int height, int width, boolean bb, Color fillColor);
```

## crop
```java
/**
 * 图像裁剪(按指定起点坐标和宽高切割)
 *
 * @param src    源图像
 * @param output 切片后的图像地址
 * @param type   类型
 * @param x      目标切片起点坐标X
 * @param y      目标切片起点坐标Y
 * @param width  目标切片宽度
 * @param height 目标切片高度
 */
ImageUtil.crop(BufferedImage src, OutputStream output, String type, int x, int y, int width, int height);
```

## sliceWithNumber
```java
/**
 * 图像切割（指定切片的行数和列数）
 *
 * @param src   源图像地址
 * @param mos   切片目标文件夹
 * @param type  类型
 * @param prows 目标切片行数。默认2，必须是范围 [1, 20] 之内
 * @param pcols 目标切片列数。默认2，必须是范围 [1, 20] 之内
 */
ImageUtil.sliceWithNumber(BufferedImage src, IMultiOutputStream mos, String type, int prows, int pcols);
```

## sliceWithSize
```java
/**
 * 图像切割（指定切片的宽度和高度）
 *
 * @param src         源图像地址
 * @param mos         切片目标文件夹
 * @param type        类型
 * @param pdestWidth  目标切片宽度。默认200
 * @param pdestHeight 目标切片高度。默认150
 */
ImageUtil.sliceWithSize(BufferedImage src, IMultiOutputStream mos, String type, int pdestWidth, int pdestHeight);
```

## convert
```java
/**
 * 图像类型转换：GIF-JPG、GIF-PNG、PNG-JPG、PNG-GIF(X)、BMP-PNG
 *
 * @param src        源图像地址
 * @param formatName 包含格式非正式名称的 String：如JPG、JPEG、GIF等
 * @param output     目标图像地址
 */
ImageUtil.convert(BufferedImage src, OutputStream output, String formatName);
```

## gray
```java
/**
 * 彩色转为黑白
 *
 * @param src    源图像地址
 * @param output 目标图像地址
 * @param type      类型
 */
ImageUtil.gray(BufferedImage src, OutputStream output, String type);
```

## textStamp
```java
/**
 * 给图片添加文字水印
 *
 * @param src      源图像
 * @param output   输出流
 * @param type      类型
 * @param text     水印文字
 * @param font     水印的字体
 * @param color    水印的字体颜色
 * @param position 水印位置 {@link ImagePosition}
 * @param x        修正值
 * @param y        修正值
 * @param alpha    透明度：alpha 必须是范围 [0.0, 1.0] 之内（包含边界值）的一个浮点数字
 */
ImageUtil.textStamp(BufferedImage src, OutputStream output, String type, String text, Font font, Color color, int position, int x, int y, float alpha);
```

## imageStamp
```java
/**
 * 给图片添加图片水印
 *
 * @param src      源图像
 * @param output   输出流
 * @param type      类型
 * @param stamp    水印图片
 * @param position 水印位置 {@link ImagePosition}
 * @param x        修正值
 * @param y        修正值
 * @param alpha    透明度：alpha 必须是范围 [0.0, 1.0] 之内（包含边界值）的一个浮点数字
 */
ImageUtil.imageStamp(BufferedImage src, OutputStream output, String type, BufferedImage stamp, int position, int x, int y, float alpha);
```

## calcTextWidth
```java
/**
 * 计算text的长度（一个中文算两个字符）
 *
 * @param text text
 * @return int
 */
ImageUtil.calcTextWidth(String text);
```

## defaultString
```java
/**
 * 默认字符串
 * @param str 字符串
 * @param defaultStr 默认值
 * @return
 */
ImageUtil.defaultString(String str, String defaultStr);
```

