#  Web通用工具
**类名：** `WebUtil`

## isBody
```java
/**
 * 判断是否ajax请求
 * spring ajax 返回含有 ResponseBody 或者 RestController注解
 *
 * @param handlerMethod HandlerMethod
 * @return 是否ajax请求
 */
WebUtil.isBody(HandlerMethod handlerMethod);
```

## getCookieVal
```java
/**
 * 读取cookie
 *
 * @param name cookie name
 * @return cookie value
 */
WebUtil.getCookieVal(String name);
```

## getCookieVal
```java
/**
 * 读取cookie
 *
 * @param request HttpServletRequest
 * @param name    cookie name
 * @return cookie value
 */
WebUtil.getCookieVal(HttpServletRequest request, String name);
```

## removeCookie
```java
/**
 * 清除 某个指定的cookie
 *
 * @param response HttpServletResponse
 * @param key      cookie key
 */
WebUtil.removeCookie(HttpServletResponse response, String key);
```

## setCookie
```java
/**
 * 设置cookie
 *
 * @param response        HttpServletResponse
 * @param name            cookie name
 * @param value           cookie value
 * @param maxAgeInSeconds maxage
 */
WebUtil.setCookie(HttpServletResponse response, String name, String value, int maxAgeInSeconds);
```

## getRequest
```java
/**
 * 获取 HttpServletRequest
 *
 * @return {HttpServletRequest}
 */
WebUtil.getRequest();
```

## renderJson
```java
/**
 * 返回json
 *
 * @param response HttpServletResponse
 * @param result   结果对象
 */
WebUtil.renderJson(HttpServletResponse response, Object result);
```

## renderJson
```java
/**
 * 返回json
 *
 * @param response    HttpServletResponse
 * @param result      结果对象
 * @param contentType contentType
 */
WebUtil.renderJson(HttpServletResponse response, Object result, String contentType);
```

## getIP
```java
/**
 * 获取ip
 *
 * @return {String}
 */
WebUtil.getIP();
```

## getIP
```java
/**
 * 获取ip
 *
 * @param request HttpServletRequest
 * @return {String}
 */
WebUtil.getIP(HttpServletRequest request);
```

## getHeader
```java
/**
 * 获取请求头的值
 *
 * @param name 请求头名称
 * @return 请求头
 */
WebUtil.getHeader(String name);
```

## getHeaders
```java
/**
 * 获取请求头的值
 *
 * @param name 请求头名称
 * @return 请求头
 */
WebUtil.getHeaders(String name);
```

## getHeaderNames
```java
/**
 * 获取所有的请求头
 *
 * @return 请求头集合
 */
WebUtil.getHeaderNames();
```

## getParameter
```java
/**
 * 获取请求参数
 *
 * @param name 请求参数名
 * @return 请求参数
 */
WebUtil.getParameter(String name);
```

## getRequestBody
```java
/**
 * 获取 request 请求体
 *
 * @param servletInputStream servletInputStream
 * @return body
 */
WebUtil.getRequestBody(ServletInputStream servletInputStream);
```

## getRequestContent
```java
/**
 * 获取 request 请求内容
 *
 * @param request request
 * @return {String}
 */
WebUtil.getRequestContent(HttpServletRequest request);
```

## setWebAppRootSystemProperty
```java
/**
 * Set a system property to the web application root directory.
 * The key of the system property can be defined with the "webAppRootKey"
 * context-param in {@code web.xml}. Default is "webapp.root".
 * <p>Can be used for tools that support substitution with {@code System.getProperty}
 * values, like log4j's "${key}" syntax within log file locations.
 * @param servletContext the servlet context of the web application
 * @throws IllegalStateException if the system property is already set,
 * or if the WAR file is not expanded
 * @see #WEB_APP_ROOT_KEY_PARAM
 * @see #DEFAULT_WEB_APP_ROOT_KEY
 * @see WebAppRootListener
 */
WebUtil.setWebAppRootSystemProperty(ServletContext servletContext);
```

## removeWebAppRootSystemProperty
```java
/**
 * Remove the system property that points to the web app root directory.
 * To be called on shutdown of the web application.
 * @param servletContext the servlet context of the web application
 * @see #setWebAppRootSystemProperty
 */
WebUtil.removeWebAppRootSystemProperty(ServletContext servletContext);
```

## getDefaultHtmlEscape
```java
/**
 * Return whether default HTML escaping is enabled for the web application,
 * i.e. the value of the "defaultHtmlEscape" context-param in {@code web.xml}
 * (if any).
 * <p>This method differentiates between no param specified at all and
 * an actual boolean value specified, allowing to have a context-specific
 * default in case of no setting at the global level.
 * @param servletContext the servlet context of the web application
 * @return whether default HTML escaping is enabled for the given application
 * ({@code null} = no explicit default)
 */
WebUtil.getDefaultHtmlEscape(ServletContext servletContext);
```

## getResponseEncodedHtmlEscape
```java
/**
 * Return whether response encoding should be used when HTML escaping characters,
 * thus only escaping XML markup significant characters with UTF-* encodings.
 * This option is enabled for the web application with a ServletContext param,
 * i.e. the value of the "responseEncodedHtmlEscape" context-param in {@code web.xml}
 * (if any).
 * <p>This method differentiates between no param specified at all and
 * an actual boolean value specified, allowing to have a context-specific
 * default in case of no setting at the global level.
 * @param servletContext the servlet context of the web application
 * @return whether response encoding is to be used for HTML escaping
 * ({@code null} = no explicit default)
 * @since 4.1.2
 */
WebUtil.getResponseEncodedHtmlEscape(ServletContext servletContext);
```

## getTempDir
```java
/**
 * Return the temporary directory for the current web application,
 * as provided by the servlet container.
 * @param servletContext the servlet context of the web application
 * @return the File representing the temporary directory
 */
WebUtil.getTempDir(ServletContext servletContext);
```

## getRealPath
```java
/**
 * Return the real path of the given path within the web application,
 * as provided by the servlet container.
 * <p>Prepends a slash if the path does not already start with a slash,
 * and throws a FileNotFoundException if the path cannot be resolved to
 * a resource (in contrast to ServletContext's {@code getRealPath},
 * which returns null).
 * @param servletContext the servlet context of the web application
 * @param path the path within the web application
 * @return the corresponding real path
 * @throws FileNotFoundException if the path cannot be resolved to a resource
 * @see javax.servlet.ServletContext#getRealPath
 */
WebUtil.getRealPath(ServletContext servletContext, String path);
```

## getSessionId
```java
/**
 * Determine the session id of the given request, if any.
 * @param request current HTTP request
 * @return the session id, or {@code null} if none
 */
WebUtil.getSessionId(HttpServletRequest request);
```

## getSessionAttribute
```java
/**
 * Check the given request for a session attribute of the given name.
 * Returns null if there is no session or if the session has no such attribute.
 * Does not create a new session if none has existed before!
 * @param request current HTTP request
 * @param name the name of the session attribute
 * @return the value of the session attribute, or {@code null} if not found
 */
WebUtil.getSessionAttribute(HttpServletRequest request, String name);
```

## getRequiredSessionAttribute
```java
/**
 * Check the given request for a session attribute of the given name.
 * Throws an exception if there is no session or if the session has no such
 * attribute. Does not create a new session if none has existed before!
 * @param request current HTTP request
 * @param name the name of the session attribute
 * @return the value of the session attribute, or {@code null} if not found
 * @throws IllegalStateException if the session attribute could not be found
 */
WebUtil.getRequiredSessionAttribute(HttpServletRequest request, String name);
```

## setSessionAttribute
```java
/**
 * Set the session attribute with the given name to the given value.
 * Removes the session attribute if value is null, if a session existed at all.
 * Does not create a new session if not necessary!
 * @param request current HTTP request
 * @param name the name of the session attribute
 * @param value the value of the session attribute
 */
WebUtil.setSessionAttribute(HttpServletRequest request, String name, Object value);
```

## getSessionMutex
```java
/**
 * Return the best available mutex for the given session:
 * that is, an object to synchronize on for the given session.
 * <p>Returns the session mutex attribute if available; usually,
 * this means that the HttpSessionMutexListener needs to be defined
 * in {@code web.xml}. Falls back to the HttpSession itself
 * if no mutex attribute found.
 * <p>The session mutex is guaranteed to be the same object during
 * the entire lifetime of the session, available under the key defined
 * by the {@code SESSION_MUTEX_ATTRIBUTE} constant. It serves as a
 * safe reference to synchronize on for locking on the current session.
 * <p>In many cases, the HttpSession reference itself is a safe mutex
 * as well, since it will always be the same object reference for the
 * same active logical session. However, this is not guaranteed across
 * different servlet containers; the only 100% safe way is a session mutex.
 * @param session the HttpSession to find a mutex for
 * @return the mutex object (never {@code null})
 * @see #SESSION_MUTEX_ATTRIBUTE
 * @see HttpSessionMutexListener
 */
WebUtil.getSessionMutex(HttpSession session);
```

## getNativeRequest
```java
/**
 * Return an appropriate request object of the specified type, if available,
 * unwrapping the given request as far as necessary.
 * @param request the servlet request to introspect
 * @param requiredType the desired type of request object
 * @return the matching request object, or {@code null} if none
 * of that type is available
 */
WebUtil.getNativeRequest(ServletRequest request, Class<T> requiredType);
```

## getNativeResponse
```java
/**
 * Return an appropriate response object of the specified type, if available,
 * unwrapping the given response as far as necessary.
 * @param response the servlet response to introspect
 * @param requiredType the desired type of response object
 * @return the matching response object, or {@code null} if none
 * of that type is available
 */
WebUtil.getNativeResponse(ServletResponse response, Class<T> requiredType);
```

## isIncludeRequest
```java
/**
 * Determine whether the given request is an include request,
 * that is, not a top-level HTTP request coming in from the outside.
 * <p>Checks the presence of the "javax.servlet.include.request_uri"
 * request attribute. Could check any request attribute that is only
 * present in an include request.
 * @param request current servlet request
 * @return whether the given request is an include request
 */
WebUtil.isIncludeRequest(ServletRequest request);
```

## exposeErrorRequestAttributes
```java
/**
 * Expose the Servlet spec's error attributes as {@link javax.servlet.http.HttpServletRequest}
 * attributes under the keys defined in the Servlet 2.3 specification, for error pages that
 * are rendered directly rather than through the Servlet container's error page resolution:
 * {@code javax.servlet.error.status_code},
 * {@code javax.servlet.error.exception_type},
 * {@code javax.servlet.error.message},
 * {@code javax.servlet.error.exception},
 * {@code javax.servlet.error.request_uri},
 * {@code javax.servlet.error.servlet_name}.
 * <p>Does not override values if already present, to respect attribute values
 * that have been exposed explicitly before.
 * <p>Exposes status code 200 by default. Set the "javax.servlet.error.status_code"
 * attribute explicitly (before or after) in order to expose a different status code.
 * @param request current servlet request
 * @param ex the exception encountered
 * @param servletName the name of the offending servlet
 */
WebUtil.exposeErrorRequestAttributes(HttpServletRequest request, Throwable ex, String servletName);
```

## clearErrorRequestAttributes
```java
/**
 * Clear the Servlet spec's error attributes as {@link javax.servlet.http.HttpServletRequest}
 * attributes under the keys defined in the Servlet 2.3 specification:
 * {@code javax.servlet.error.status_code},
 * {@code javax.servlet.error.exception_type},
 * {@code javax.servlet.error.message},
 * {@code javax.servlet.error.exception},
 * {@code javax.servlet.error.request_uri},
 * {@code javax.servlet.error.servlet_name}.
 * @param request current servlet request
 */
WebUtil.clearErrorRequestAttributes(HttpServletRequest request);
```

## getCookie
```java
/**
 * Retrieve the first cookie with the given name. Note that multiple
 * cookies can have the same name but different paths or domains.
 * @param request current servlet request
 * @param name cookie name
 * @return the first cookie with the given name, or {@code null} if none is found
 */
WebUtil.getCookie(HttpServletRequest request, String name);
```

## hasSubmitParameter
```java
/**
 * Check if a specific input type="submit" parameter was sent in the request,
 * either via a button (directly with name) or via an image (name + ".x" or
 * name + ".y").
 * @param request current HTTP request
 * @param name name of the parameter
 * @return if the parameter was sent
 * @see #SUBMIT_IMAGE_SUFFIXES
 */
WebUtil.hasSubmitParameter(ServletRequest request, String name);
```

## findParameterValue
```java
/**
 * Obtain a named parameter from the given request parameters.
 * <p>See {@link #findParameterValue(java.util.Map, String)}
 * for a description of the lookup algorithm.
 * @param request current HTTP request
 * @param name the <i>logical</i> name of the request parameter
 * @return the value of the parameter, or {@code null}
 * if the parameter does not exist in given request
 */
WebUtil.findParameterValue(ServletRequest request, String name);
```

## findParameterValue
```java
/**
 * Obtain a named parameter from the given request parameters.
 * <p>This method will try to obtain a parameter value using the
 * following algorithm:
 * <ol>
 * <li>Try to get the parameter value using just the given <i>logical</i> name.
 * This handles parameters of the form <tt>logicalName = value</tt>. For normal
 * parameters, e.g. submitted using a hidden HTML form field, this will return
 * the requested value.</li>
 * <li>Try to obtain the parameter value from the parameter name, where the
 * parameter name in the request is of the form <tt>logicalName_value = xyz</tt>
 * with "_" being the configured delimiter. This deals with parameter values
 * submitted using an HTML form submit button.</li>
 * <li>If the value obtained in the previous step has a ".x" or ".y" suffix,
 * remove that. This handles cases where the value was submitted using an
 * HTML form image button. In this case the parameter in the request would
 * actually be of the form <tt>logicalName_value.x = 123</tt>. </li>
 * </ol>
 * @param parameters the available parameter map
 * @param name the <i>logical</i> name of the request parameter
 * @return the value of the parameter, or {@code null}
 * if the parameter does not exist in given request
 */
WebUtil.findParameterValue(Map<String,?> parameters, String name);
```

## getParametersStartingWith
```java
/**
 * Return a map containing all parameters with the given prefix.
 * Maps single values to String and multiple values to String array.
 * <p>For example, with a prefix of "spring_", "spring_param1" and
 * "spring_param2" result in a Map with "param1" and "param2" as keys.
 * @param request the HTTP request in which to look for parameters
 * @param prefix the beginning of parameter names
 * (if this is null or the empty string, all parameters will match)
 * @return map containing request parameters <b>without the prefix</b>,
 * containing either a String or a String array as values
 * @see javax.servlet.ServletRequest#getParameterNames
 * @see javax.servlet.ServletRequest#getParameterValues
 * @see javax.servlet.ServletRequest#getParameterMap
 */
WebUtil.getParametersStartingWith(ServletRequest request, String prefix);
```

## parseMatrixVariables
```java
/**
 * Parse the given string with matrix variables. An example string would look
 * like this {@code "q1=a;q1=b;q2=a,b,c"}. The resulting map would contain
 * keys {@code "q1"} and {@code "q2"} with values {@code ["a","b"]} and
 * {@code ["a","b","c"]} respectively.
 * @param matrixVariables the unparsed matrix variables string
 * @return a map with matrix variable names and values (never {@code null})
 * @since 3.2
 */
WebUtil.parseMatrixVariables(String matrixVariables);
```

## isValidOrigin
```java
/**
 * Check the given request origin against a list of allowed origins.
 * A list containing "*" means that all origins are allowed.
 * An empty list means only same origin is allowed.
 *
 * <p><strong>Note:</strong> as of 5.1 this method ignores
 * {@code "Forwarded"} and {@code "X-Forwarded-*"} headers that specify the
 * client-originated address. Consider using the {@code ForwardedHeaderFilter}
 * to extract and use, or to discard such headers.
 *
 * @return {@code true} if the request origin is valid, {@code false} otherwise
 * @since 4.1.5
 * @see <a href="https://tools.ietf.org/html/rfc6454">RFC 6454: The Web Origin Concept</a>
 */
WebUtil.isValidOrigin(HttpRequest request, Collection<String> allowedOrigins);
```

## isSameOrigin
```java
/**
 * Check if the request is a same-origin one, based on {@code Origin}, {@code Host},
 * {@code Forwarded}, {@code X-Forwarded-Proto}, {@code X-Forwarded-Host} and
 * {@code X-Forwarded-Port} headers.
 *
 * <p><strong>Note:</strong> as of 5.1 this method ignores
 * {@code "Forwarded"} and {@code "X-Forwarded-*"} headers that specify the
 * client-originated address. Consider using the {@code ForwardedHeaderFilter}
 * to extract and use, or to discard such headers.
 *
 * @return {@code true} if the request is a same-origin one, {@code false} in case
 * of cross-origin request
 * @since 4.2
 */
WebUtil.isSameOrigin(HttpRequest request);
```

