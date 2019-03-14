# Mock系统的基本构成

业务分层：

![](/assets/xmind-mock-server-service.png)

技术架构：![](/assets/mock-system.png)

Mock Server主要是由下面的部分构成：

1、服务器

2、基本路由（Mock Server系统使用的路由，用户授权等）

3、mock路由（处理Mock接口url的请求和响应）

4、mock路由解析器（读取接口配置并生成数据，是mock.js最重要的部分）

5、接口配置存储（存储用户添加的配置）

