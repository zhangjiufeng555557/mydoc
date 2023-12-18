#  xpath解析xml
**类名：** `XmlUtil`

## of
```java
/**
 * 转换工具类
 *
 * @param inputStream inputStream
 * @return XmlUtil
 */
XmlUtil.of(InputStream inputStream);
```

## of
```java
/**
 * 转换工具类
 *
 * @param xmlStr xmlStr
 * @return XmlUtil
 */
XmlUtil.of(String xmlStr);
```

## getString
```java
/**
 * 获取String
 *
 * @param expression 路径
 * @return {String}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getString(String expression);
```

## getBoolean
```java
/**
 * 获取Boolean
 *
 * @param expression 路径
 * @return {String}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getBoolean(String expression);
```

## getNumber
```java
/**
 * 获取Number
 *
 * @param expression 路径
 * @return {Number}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNumber(String expression);
```

## getNode
```java
/**
 * 获取某个节点
 *
 * @param expression 路径
 * @return {Node}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNode(String expression);
```

## getNodeList
```java
/**
 * 获取子节点
 *
 * @param expression 路径
 * @return NodeList
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNodeList(String expression);
```

## getString
```java
/**
 * 获取String
 *
 * @param node       节点
 * @param expression 相对于node的路径
 * @return {String}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getString(Object node, String expression);
```

## getBoolean
```java
/**
 * 获取
 *
 * @param node       节点
 * @param expression 相对于node的路径
 * @return {String}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getBoolean(Object node, String expression);
```

## getNumber
```java
/**
 * 获取
 *
 * @param node       节点
 * @param expression 相对于node的路径
 * @return {Number}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNumber(Object node, String expression);
```

## getNode
```java
/**
 * 获取某个节点
 *
 * @param node       节点
 * @param expression 路径
 * @return {Node}
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNode(Object node, String expression);
```

## getNodeList
```java
/**
 * 获取子节点
 *
 * @param node       节点
 * @param expression 相对于node的路径
 * @return NodeList
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.getNodeList(Object node, String expression);
```

## toMap
```java
/**
 * 针对没有嵌套节点的简单处理
 *
 * @return map集合
 */
XmlUtil xmlUtil = new XmlUtil();
xmlUtil.toMap();
```

