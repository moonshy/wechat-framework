微信公众平台SDK开发框架，封装了微信公众平台的接口，方便开发者快速构建微信公众号应用，专注于业务逻辑开发，提高开发效率
现在本项目全面支持Spring框架。

1. TokenProxy获取AccessToken方式;
   (1) DefaultTokenProxy,使用该方式，支持本机ConcurrentHashMap来缓存accessToken.
   Spring 配置：
   &lt;bean id="tokenProxy" class="com.richong.wechatframework.api.token.impl.DefaultTokenProxy"
             p:appid="${wechat.appid}" p:appSecret="${wechat.appsecret}"/&gt;
   (2) RedisTokenProxy,使用该方式，支持Redis分布式环境。
   Spring 配置：
   &lt;bean id="tokenProxy" class="com.richong.wechatframework.api.token.impl.RedisTokenProxy"
             p:appid="${wechat.appid}" p:appSecret="${wechat.appsecret}"/&gt;
   Maven 添加依赖：
   &lt;dependency&gt;
       &lt;groupId&gt;redis.clients&lt;/groupId&gt;
       &lt;artifactId&gt;jedis&lt;/artifactId&gt;
       &lt;version&gt;2.9.0&lt;/version&gt;
   &lt;/dependency&gt;
   &lt;dependency&gt;
       &lt;groupId&gt;org.springframework.data&lt;/groupId&gt;
       &lt;artifactId&gt;spring-data-redis&lt;/artifactId&gt;
       &lt;version&gt;1.7.2.RELEASE&lt;/version&gt;
   &lt;/dependency&gt;