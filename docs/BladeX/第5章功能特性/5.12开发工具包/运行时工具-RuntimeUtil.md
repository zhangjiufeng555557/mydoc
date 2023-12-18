#  运行时工具类
**类名：** `RuntimeUtil`

## getPid
```java
/**
 * 获得当前进程的PID
 * <p>
 * 当失败时返回-1
 *
 * @return pid
 */
RuntimeUtil.getPid();
```

## getUpTime
```java
/**
 * 返回应用启动到现在的时间
 *
 * @return {Duration}
 */
RuntimeUtil.getUpTime();
```

## getJvmArguments
```java
/**
 * 返回输入的JVM参数列表
 *
 * @return jvm参数
 */
RuntimeUtil.getJvmArguments();
```

## getCpuNum
```java
/**
 * 获取CPU核数
 *
 * @return cpu count
 */
RuntimeUtil.getCpuNum();
```

