## Springboot 实现JAVA国际化
在SpringBoot中主要借助MessageSource来获取不同语言的value信息
springboot 默认使用org.springframework.web.servlet.i18n.AcceptHeaderLocaleResolver类来获取请求header中Accept-Language 来切换不同的语言
在spring容器启动时，会在上下文中寻找LocaleResolver本地化解析器，spring提供了3个本地化解析器和1个本地化拦截器：
### AcceptHeaderLocaleResolver
    根据HTTP报文头的Accept-Language参数确定本地化类型。如果没有显示定义本地化解析器，Spring MVC默认采用此解析器
### CookieLocaleResolver
    根据指定的Cookie值确定本地化类型。在spring配置文件中配置CookieLocaleResolver，DispatcherServlet自动识别并装配。客户端只要通过JavaScript更改clientLanguage这个cookie的值，就可以控制服务器返回相应的本地化页面。
### SessionLocaleResolver
    根据Session中特定的属性值确定本地化类型。SessionLocaleResolver会查找Session中属性名为SessionLocaleResolver.LOCALE_SESSION_ATTRIBUTE_NAME的属性，并将其转成Locale对象，作为客户端的本地化类型。在spring配置文件中加入以下代码即可。
    SessionLocaleResolver和CookieLocaleResolver的区别是：前者一般要求用户登录后生成相应的用户会话才有效，而后者只要浏览器有Cookie存在即可
### LocaleContextResolver
### LocaleChangeInterceptor
    从请求参数中获取本次请求对应的本地化类型。很多网站都允许通过一个参数控制网站的本地化，如 www.xxx.com?locale=zh_CN 返回对应中国大陆的本地化网页。Spring MVC 提供LocaleChangeInterceptor拦截器完成。
    LocaleChangeInterceptor在默认情况下通过locale请求参数获取本次请求对应的本地化类型，用户可以通过其paramName属性指定一个其他参数名。由于LocaleChangeInterceptor的主要任务是从请求中获取本地化类型并将其设置给真正的本地化解析器，所以在配置LocaleChangeInterceptor之前，必须在上下文中先配置一个本地化解析器。由于AcceptHeaderLocaleResolver是从请求报文头获取本地化信息的，不能被动更改，因此只能选择CookieLocaleResolver或SessionLocaleResolver


```java
public class LanguageConfig implements WebMvcConfigurer {

//	/**
//	 * 添加拦截器 自动获取链接上的lang字段 切换请求语言
//	 *
//	 * @param registry
//	 */
//	@Override
//	public void addInterceptors(InterceptorRegistry registry) {
//		LocaleChangeInterceptor interceptor = new LocaleChangeInterceptor();
//		interceptor.setParamName("lang");
//		registry.addInterceptor(interceptor);
//	}
//	/**
//	 * 初始化 设置默认语言信息  默认中文语言
//	 *
//	 * @return
//	 */
//	@Bean
//	LocaleResolver localeResolver() {
//		SessionLocaleResolver localeResolver = new SessionLocaleResolver();
//		localeResolver.setDefaultLocale(Locale.SIMPLIFIED_CHINESE);
//		return localeResolver;
//	}

	/**
	 * 获取请求头中的Accept-Language值 来改变国际化语言内容
	 *
	 * @return
	 */
	@Bean
	LocaleResolver localeResolver() {
		AcceptHeaderLocaleResolver acceptHeaderLocaleResolver = new AcceptHeaderLocaleResolver();
		acceptHeaderLocaleResolver.setDefaultLocale(Locale.SIMPLIFIED_CHINESE);
		return acceptHeaderLocaleResolver;
	}
}

```

### 继承Springboot 原本的国际化内容缓存类AbstractResourceBasedMessageSource 自定义内容加载缓存 
```java

public abstract class LanguageResourceBundle extends AbstractResourceBasedMessageSource {

	/**
	 * 国际化语言 缓存集合
	 */
	protected static Map<Locale, Map<String, String>> LOCALE_MAP = new ConcurrentHashMap();

	/**
	 * 国际化语言翻译集合 初始化接口
	 *
	 * @return
	 */
	public abstract LanguageResourceBundle initialize();

	/**
	 * 通过缓存 获取对应key的语言翻译内容
	 *
	 * @param code
	 * @param locale
	 * @return
	 */
	@Override
	protected MessageFormat resolveCode(String code, Locale locale) {
		Optional<String> opt = Optional.ofNullable(LOCALE_MAP.get(locale).get(code));
		return opt.map(x -> new MessageFormat(x)).orElse(null);
	}
}
```
### 通过数据库加载国际化内容 并缓存到自定义内容缓存中
```java
@Component
public class LanguageCarbonOffsetResourceBundle extends LanguageResourceBundle {

    @Autowired
    private ICoLanguageService languageService;

    public LanguageCarbonOffsetResourceBundle initialize() {
        List<CoLanguageEntity> list = languageService.list();
        AssertUtil.isNull(list, WebSiteExceptionEnum.INIT_I18N_ERROR);
        super.LOCALE_MAP.putAll(list.stream().collect(Collectors.groupingBy(x -> {
            String[] codes = Func.split(x.getLangCode(), StringPool.UNDERSCORE);
            return new Locale(codes[0], codes.length > 1 ? codes[1] : "");
        }, Collectors.toMap(CoLanguageEntity::getTextKey, CoLanguageEntity::getTextValue))));
        return this;
    }
}
```
### 项目启动时调用国际化内容初始化接口 初始化内容
```java
@Configuration(proxyBeanMethods = false)
public class LanguageInitializeConfig {

    @Autowired
    private LanguageCarbonOffsetResourceBundle languageResourceBundle;

    @PostConstruct
    public void initSummaryDay() {
        languageResourceBundle.initialize();
    }

}
```
### 语言切换注解
```java
/**
 * 语言翻译注解
 */
@Documented
@Target({ElementType.METHOD, ElementType.FIELD})
@Retention(RetentionPolicy.RUNTIME)
public @interface Language {
}
```
### 语言切换
```java

@Slf4j
@Aspect
@Component
public class LanguageErrorAspect {

	@Autowired
	private LanguageResourceBundle resourceBundle;

	/**
	 * 切面整个异常处理类
	 */
	@Pointcut("execution(public * com.chy.core.log.error.ChyRestExceptionTranslator.*(..))")
	private void pointError() {
	}

	@Around("pointError()")
	public Object afterError(ProceedingJoinPoint joinPoint) {
		R result = null;
		Optional<String> msg;
		try {
			log.info("开始对异常抛出进行国际化处理");
			result = (R) joinPoint.proceed();
			msg = getMsg(result);
			if (!msg.isPresent()) {
				Object[] args = joinPoint.getArgs();
				// 非业务异常 且翻译失败的情况下 给异常添加默认中文信息
				if (args[0] instanceof SecureException) {
					msg = Optional.of(((SecureException) args[0]).getResultCode().getMessage());
				} else if (args[0] instanceof Throwable) {
					msg = Optional.of(ResultCode.INTERNAL_SERVER_ERROR.getMessage());
				}
			}
			result.setMsg(msg.orElse(result.getMsg()));
		} catch (Throwable e) {
			log.error("异常响应国际化处理时发生异常", e);
		}
		return result;
	}

	/**
	 * 对响应的异常信息 进行国际化翻译处理
	 *
	 * @param result
	 * @return
	 */
	@NotNull
	private Optional<String> getMsg(R result) {
		Optional<String> msg = Optional.empty();
		try {
			msg = Optional.ofNullable(resourceBundle.getMessage(result.getMsg(), null, LocaleContextHolder.getLocale()));
		} catch (Exception e) {
			log.info("未获取到异常信息对应翻译内容");
		}
		return msg;
	}
}
```
