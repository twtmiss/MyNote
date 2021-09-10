### Spring 框架处理 HTTP 请求的流程

![image-20210406110103140](/Users/twtmiss/Library/Application Support/typora-user-images/image-20210406110103140.png)

- 前置分发器 DispatcherServlet 接收到 HTTP 请求之后，将查找适当的控制器 Controller 来处理请求，它通过解析 HTTP 请求的 URL 获得 URI，再根据该 URI 从处理器映射 HandlerMapping 当中获得该请求对应的处理器 Handler 和处理器拦截器 HandlerInterceptor，最后以 HandlerExecutionChain 形式返回。
- 前置分发器 DispatcherServlet 根据获得的处理器 Handler 选择合适的适配器 HandlerAdapter。如果成功获得适配器 HandlerAdapter，在调用处理器 Handler 之前其拦截器的方法 preHandler() 优先执行。
- 方法 preHandler() 提取 HTTP 请求中的数据填充到处理器 Handler 的入参当中，然后开始调用处理器 Handler（即控制器 Controller）相关方法。
- 控制器 Controller 执行完成之后，向前置分发器 DispatcherServlet 返回一个模型与视图名对象 ModelAndView 。
- 前置分发器 DispatchServlet 根据模型与视图名对象 ModelAndView 选择适合的视图解析器 ViewResolver，前提该视图解析器必须已经注册至 Spring IOC 容器当中。
- 视图解析器 ViewResolver 将根据 ModelAndView 里面指定的视图名称获得特定的视图 View。
- 前置分发器 DispatchServlet 将模型数据填充进视图当中，然后将渲染结果返回给客户端。