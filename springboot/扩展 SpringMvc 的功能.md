# 扩展 SpringMvc 的功能

> springboot  2 版本之前，扩展 SpringMvc 的功能用一个类去继承 ==WebMvcConfigurerAdapter== 即可

在 springboot 2 版本之后， ==WebMvcConfigurerAdapter== 已经过时了，所有不建议使用该类了

如果还想扩展 SpringMvc 的功能有以下几种方法

* 继承于 ==WebMvcConfigurationSupport== 类 （**不推荐**）
  * 因为继承该类后会导致 springboot 原先对 SpringMvc 的自动配置失效

* 实现 ==WebMvcConfigurer== 类 （**推荐**）
  * 实现该类后原先的自动配置依然存在效果









