#  日期工具类
**类名：** `DateUtil`

## now
```java
/**
 * 获取当前日期
 *
 * @return 当前日期
 */
DateUtil.now();
```

## plusYears
```java
/**
 * 添加年
 *
 * @param date       时间
 * @param yearsToAdd 添加的年数
 * @return 设置后的时间
 */
DateUtil.plusYears(Date date, int yearsToAdd);
```

## plusMonths
```java
/**
 * 添加月
 *
 * @param date        时间
 * @param monthsToAdd 添加的月数
 * @return 设置后的时间
 */
DateUtil.plusMonths(Date date, int monthsToAdd);
```

## plusWeeks
```java
/**
 * 添加周
 *
 * @param date       时间
 * @param weeksToAdd 添加的周数
 * @return 设置后的时间
 */
DateUtil.plusWeeks(Date date, int weeksToAdd);
```

## plusDays
```java
/**
 * 添加天
 *
 * @param date      时间
 * @param daysToAdd 添加的天数
 * @return 设置后的时间
 */
DateUtil.plusDays(Date date, long daysToAdd);
```

## plusHours
```java
/**
 * 添加小时
 *
 * @param date       时间
 * @param hoursToAdd 添加的小时数
 * @return 设置后的时间
 */
DateUtil.plusHours(Date date, long hoursToAdd);
```

## plusMinutes
```java
/**
 * 添加分钟
 *
 * @param date         时间
 * @param minutesToAdd 添加的分钟数
 * @return 设置后的时间
 */
DateUtil.plusMinutes(Date date, long minutesToAdd);
```

## plusSeconds
```java
/**
 * 添加秒
 *
 * @param date         时间
 * @param secondsToAdd 添加的秒数
 * @return 设置后的时间
 */
DateUtil.plusSeconds(Date date, long secondsToAdd);
```

## plusMillis
```java
/**
 * 添加毫秒
 *
 * @param date        时间
 * @param millisToAdd 添加的毫秒数
 * @return 设置后的时间
 */
DateUtil.plusMillis(Date date, long millisToAdd);
```

## plusNanos
```java
/**
 * 添加纳秒
 *
 * @param date       时间
 * @param nanosToAdd 添加的纳秒数
 * @return 设置后的时间
 */
DateUtil.plusNanos(Date date, long nanosToAdd);
```

## plus
```java
/**
 * 日期添加时间量
 *
 * @param date   时间
 * @param amount 时间量
 * @return 设置后的时间
 */
DateUtil.plus(Date date, TemporalAmount amount);
```

## minusYears
```java
/**
 * 减少年
 *
 * @param date  时间
 * @param years 减少的年数
 * @return 设置后的时间
 */
DateUtil.minusYears(Date date, int years);
```

## minusMonths
```java
/**
 * 减少月
 *
 * @param date   时间
 * @param months 减少的月数
 * @return 设置后的时间
 */
DateUtil.minusMonths(Date date, int months);
```

## minusWeeks
```java
/**
 * 减少周
 *
 * @param date  时间
 * @param weeks 减少的周数
 * @return 设置后的时间
 */
DateUtil.minusWeeks(Date date, int weeks);
```

## minusDays
```java
/**
 * 减少天
 *
 * @param date 时间
 * @param days 减少的天数
 * @return 设置后的时间
 */
DateUtil.minusDays(Date date, long days);
```

## minusHours
```java
/**
 * 减少小时
 *
 * @param date  时间
 * @param hours 减少的小时数
 * @return 设置后的时间
 */
DateUtil.minusHours(Date date, long hours);
```

## minusMinutes
```java
/**
 * 减少分钟
 *
 * @param date    时间
 * @param minutes 减少的分钟数
 * @return 设置后的时间
 */
DateUtil.minusMinutes(Date date, long minutes);
```

## minusSeconds
```java
/**
 * 减少秒
 *
 * @param date    时间
 * @param seconds 减少的秒数
 * @return 设置后的时间
 */
DateUtil.minusSeconds(Date date, long seconds);
```

## minusMillis
```java
/**
 * 减少毫秒
 *
 * @param date   时间
 * @param millis 减少的毫秒数
 * @return 设置后的时间
 */
DateUtil.minusMillis(Date date, long millis);
```

## minusNanos
```java
/**
 * 减少纳秒
 *
 * @param date  时间
 * @param nanos 减少的纳秒数
 * @return 设置后的时间
 */
DateUtil.minusNanos(Date date, long nanos);
```

## minus
```java
/**
 * 日期减少时间量
 *
 * @param date   时间
 * @param amount 时间量
 * @return 设置后的时间
 */
DateUtil.minus(Date date, TemporalAmount amount);
```

## formatDateTime
```java
/**
 * 日期时间格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
DateUtil.formatDateTime(Date date);
```

## formatDateTimeMini
```java
/**
 * 日期时间格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
DateUtil.formatDateTimeMini(Date date);
```

## formatDate
```java
/**
 * 日期格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
DateUtil.formatDate(Date date);
```

## formatTime
```java
/**
 * 时间格式化
 *
 * @param date 时间
 * @return 格式化后的时间
 */
DateUtil.formatTime(Date date);
```

## format
```java
/**
 * 日期格式化
 *
 * @param date    时间
 * @param pattern 表达式
 * @return 格式化后的时间
 */
DateUtil.format(Date date, String pattern);
```

## formatDateTime
```java
/**
 * java8 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateUtil.formatDateTime(TemporalAccessor temporal);
```

## formatDateTimeMini
```java
/**
 * java8 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateUtil.formatDateTimeMini(TemporalAccessor temporal);
```

## formatDate
```java
/**
 * java8 日期时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateUtil.formatDate(TemporalAccessor temporal);
```

## formatTime
```java
/**
 * java8 时间格式化
 *
 * @param temporal 时间
 * @return 格式化后的时间
 */
DateUtil.formatTime(TemporalAccessor temporal);
```

## format
```java
/**
 * java8 日期格式化
 *
 * @param temporal 时间
 * @param pattern  表达式
 * @return 格式化后的时间
 */
DateUtil.format(TemporalAccessor temporal, String pattern);
```

## parse
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 表达式
 * @return 时间
 */
DateUtil.parse(String dateStr, String pattern);
```

## parse
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param format  ConcurrentDateFormat
 * @return 时间
 */
DateUtil.parse(String dateStr, ConcurrentDateFormat format);
```

## parse
```java
/**
 * 将字符串转换为时间
 *
 * @param dateStr 时间字符串
 * @param pattern 表达式
 * @return 时间
 */
DateUtil.parse(String dateStr, String pattern, TemporalQuery<T> query);
```

## toInstant
```java
/**
 * 时间转 Instant
 *
 * @param dateTime 时间
 * @return Instant
 */
DateUtil.toInstant(LocalDateTime dateTime);
```

## toDateTime
```java
/**
 * Instant 转 时间
 *
 * @param instant Instant
 * @return Instant
 */
DateUtil.toDateTime(Instant instant);
```

## toDate
```java
/**
 * 转换成 date
 *
 * @param dateTime LocalDateTime
 * @return Date
 */
DateUtil.toDate(LocalDateTime dateTime);
```

## toDate
```java
/**
 * 转换成 date
 *
 * @param localDate LocalDate
 * @return Date
 */
DateUtil.toDate(LocalDate localDate);
```

## toCalendar
```java
/**
 * Converts local date time to Calendar.
 */
DateUtil.toCalendar(LocalDateTime localDateTime);
```

## toMilliseconds
```java
/**
 * localDateTime 转换成毫秒数
 *
 * @param localDateTime LocalDateTime
 * @return long
 */
DateUtil.toMilliseconds(LocalDateTime localDateTime);
```

## toMilliseconds
```java
/**
 * localDate 转换成毫秒数
 *
 * @param localDate LocalDate
 * @return long
 */
DateUtil.toMilliseconds(LocalDate localDate);
```

## fromCalendar
```java
/**
 * 转换成java8 时间
 *
 * @param calendar 日历
 * @return LocalDateTime
 */
DateUtil.fromCalendar(Calendar calendar);
```

## fromInstant
```java
/**
 * 转换成java8 时间
 *
 * @param instant Instant
 * @return LocalDateTime
 */
DateUtil.fromInstant(Instant instant);
```

## fromDate
```java
/**
 * 转换成java8 时间
 *
 * @param date Date
 * @return LocalDateTime
 */
DateUtil.fromDate(Date date);
```

## fromMilliseconds
```java
/**
 * 转换成java8 时间
 *
 * @param milliseconds 毫秒数
 * @return LocalDateTime
 */
DateUtil.fromMilliseconds(long milliseconds);
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
DateUtil.between(Temporal startInclusive, Temporal endExclusive);
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
DateUtil.between(LocalDate startDate, LocalDate endDate);
```

## between
```java
/**
 * 比较2个 时间差
 *
 * @param startDate 开始时间
 * @param endDate   结束时间
 * @return 时间间隔
 */
DateUtil.between(Date startDate, Date endDate);
```

## secondToTime
```java
/**
 * 将秒数转换为日时分秒
 *
 * @param second 秒数
 * @return 时间
 */
DateUtil.secondToTime(Long second);
```

## today
```java
/**
 * 获取今天的日期
 *
 * @return 时间
 */
DateUtil.today();
```

## time
```java
/**
 * 获取今天的时间
 *
 * @return 时间
 */
DateUtil.time();
```

