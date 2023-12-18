#  DateTime 工具类
**类名：** `DateTimeUtil`

## formatDateTime
```java
/**
 * 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateTimeUtil.formatDateTime(TemporalAccessor temporal);
```

## formatDate
```java
/**
 * 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateTimeUtil.formatDate(TemporalAccessor temporal);
```

## formatTime
```java
/**
 * 时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateTimeUtil.formatTime(TemporalAccessor temporal);
```

## format
```java
/**
 * 日期格式化
 *
 * @param temporal 时间
 * @param pattern  表达式
 * @return 格式化后的时间
 */
DateTimeUtil.format(TemporalAccessor temporal, String pattern);
```

## parseDateTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 表达式
 * @return 时间
 */
DateTimeUtil.parseDateTime(String dateStr, String pattern);
```

## parseDateTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
DateTimeUtil.parseDateTime(String dateStr, DateTimeFormatter formatter);
```

## parseDateTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
DateTimeUtil.parseDateTime(String dateStr);
```

## parseDate
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 表达式
 * @return 时间
 */
DateTimeUtil.parseDate(String dateStr, String pattern);
```

## parseDate
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
DateTimeUtil.parseDate(String dateStr, DateTimeFormatter formatter);
```

## parseDate
```java
/**
 * 将字符串转换为日期
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
DateTimeUtil.parseDate(String dateStr);
```

## parseTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 时间正则
 * @return 时间
 */
DateTimeUtil.parseTime(String dateStr, String pattern);
```

## parseTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr   时间字符串
 * @param formatter DateTimeFormatter
 * @return 时间
 */
DateTimeUtil.parseTime(String dateStr, DateTimeFormatter formatter);
```

## parseTime
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @return 时间
 */
DateTimeUtil.parseTime(String dateStr);
```

## toInstant
```java
/**
 * 时间转 Instant
 *
 * @param dateTime 时间
 * @return Instant
 */
DateTimeUtil.toInstant(LocalDateTime dateTime);
```

## toDateTime
```java
/**
 * Instant 转 时间
 *
 * @param instant Instant
 * @return Instant
 */
DateTimeUtil.toDateTime(Instant instant);
```

## toDate
```java
/**
 * 转换成 date
 *
 * @param dateTime LocalDateTime
 * @return Date
 */
DateTimeUtil.toDate(LocalDateTime dateTime);
```

## between
```java
/**
 * 比较2个时间差，跨度比较小
 *
 * @param startInclusive 开始时间
 * @param endExclusive   结束时间
 * @return 时间间隔
 */
DateTimeUtil.between(Temporal startInclusive, Temporal endExclusive);
```

## between
```java
/**
 * 比较2个时间差，跨度比较大，年月日为单位
 *
 * @param startDate 开始时间
 * @param endDate   结束时间
 * @return 时间间隔
 */
DateTimeUtil.between(LocalDate startDate, LocalDate endDate);
```

