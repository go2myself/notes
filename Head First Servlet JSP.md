# Head First Servlet JSP #

服务器可能是物理主机（硬件），也可能指Web服务器应用（软件）。

浏览器就是一个软件，知道怎么与服务器通信，并将请求的HTML代码进行呈现。

![GET请求](http://i.imgur.com/hk0cAiH.png)

![POST请求](http://i.imgur.com/eLsTXzu.png)

端口表示在服务器硬件上运行的一个特定的软件逻辑连接，它们只是表示服务器应用的“逻辑”数而已，如果没有端口号，那么服务器就没办法知道客户想连哪个应用。

动态页面 辅助应用 servlet（java print出html） html中嵌入java jsp 

![](http://i.imgur.com/SfLYIY3.png)

![](http://i.imgur.com/YIzM329.png)

a.EJB实现原理： 就是把原来放到客户端实现的代码放到服务器端，并依靠RMI进行通信。

b.RMI实现原理 ：就是通过Java对象可序列化机制实现分布计算。

c.服务器集群： 就是通过RMI的通信，连接不同功能模块的服务器，以实现一个完整的功能。

![Web服务器体系结构](http://i.imgur.com/1JKWMdn.png)

servlet 的存在就是要为客户服务

[intellij在tomcat上部署web应用](http://www.it165.net/pro/html/201505/41042.html "部署到tomcat")

任何servlet都不会有多个实例（除了SingleThreadMode）

![](http://i.imgur.com/6tt8vwT.png)

servlet构造函数和init（） servletConfig和ServletContext

### GET和POST区别 ###
数据大小、安全性、书签问题、操作性质（单纯获取、除了获取可能是一个更新）

幂等 任意多次执行所产生的影响均与一次执行的影响相同（或者没有副作用） GET PUT HEAD

sendRedirect("foo/stuff.html")当前路径下
sendRedirect("/foo/stuff.html")根路径下

RequestDispather 分发到JSP
sendRedirect(String url) 重定向到一个新的url

ServletContext InitParameter 和 Attribute

属性有三个作用域：上下文，请求，会话**（Context，Request，HttpSession）**
只有请求属性是线程安全的
Servlet只有一个实例，但可能有多个线程来调用，在Servlet中不要发布非final状态变量，也不要逸出
### 会话ID ###
认证客户 媒介cookie 对于禁用cookie使用URL重写（URL编码，只在响应中调用此方法）
