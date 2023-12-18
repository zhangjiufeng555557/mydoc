#  Spring 工具类
**类名：** `SpringUtil`

## getBean
```java
/**
 * 获取bean
 *
 * @param clazz class类
 * @param <T>   泛型
 * @return T
 */
SpringUtil.getBean(Class<T> clazz);
```

## getBean
```java
/**
 * 获取bean
 *
 * @param beanId beanId
 * @param <T>    泛型
 * @return T
 */
SpringUtil.getBean(String beanId);
```

## getBean
```java
/**
 * 获取bean
 *
 * @param beanName bean名称
 * @param clazz    class类
 * @param <T>      泛型
 * @return T
 */
SpringUtil.getBean(String beanName, Class<T> clazz);
```

## getContext
```java
/**
 * 获取 ApplicationContext
 *
 * @return ApplicationContext
 */
SpringUtil.getContext();
```

## publishEvent
```java
/**
 * 发布事件
 *
 * @param event 事件
 */
SpringUtil.publishEvent(ApplicationEvent event);
```

