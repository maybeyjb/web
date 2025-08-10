
# java组件

#### rce函数：

测试通过函数或者参数，url中是否存在这些函数类：

![image-20250225154400578](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621161.png)

​	RuntimeExec

![image-20250227152239421](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621162.png)

ScriptEngineManager  jdk1.8之前的、用处不大，jdk太老了/

![image-20250227152544064](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621163.png)

 Groovy

  ProcessBuilder

![image-20250227152903965](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621164.png)

  ProcessImpl

黑盒中就是看参数，url，功能点测试rce。

![image-20250227153311734](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621165.png)

####  jndi

java去远程调用rmi和loap协议调用出的rce

利用：

主要用jndi的jar包注入工具，利用工具远程生成一个恶意代码的.class文件，然后调用远程地址加载恶意语句注入。

![image-20250225160047242](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621166.png)

远程调用方法，远程加载.class文件调用执行

jndi是一个内置功能，是java的技术，里面的RMI：远程方法调用注册表	LDAP：轻量级目录访问协议  两个协议常用，不是作为漏洞打的，是作为java漏洞利用方法，利用这个jndi方法来实现漏洞。

就比如说log4j有漏洞，就用jndi注入测试他的rce。

![image-20250227154024165](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621167.png)

rmi和ldap的差异：

限制的java版本编号不同

高版本绕过：[如何绕过高版本JDK的限制进行JNDI注入利用 – KINGX](https://kingx.me/Restrictions-and-Bypass-of-JNDI-Manipulations-RCE.html)

需要分析代码和调用等问题。不过有工具

### 不安全组件

  log4j  基于Java的日志记录框架

logger.error    logger.info

![image-20250227172202499](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621168.png)

漏洞库	 https://avd.aliyun.com/search?q=Log4j

FastJson	json解析器，它可以解析JSON格式的字符串，支持将JavaBean序列化为JSON字符串，也可以从JSON字符串反序列化到JavaBean。

![image-20250227160345490](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621169.png)



靶场演示	配合aliyun漏洞库

shiro 数据包中的cookie中有remerberme   shiro  能够用于身份验证、授权、加密和会话管理。

XStream 反序列化：

![image-20250227161427943](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621170.png)

Log4j 记录日志的、一般会解析日志：

那黑盒一般测试：一般用dnslog带外测试是否存在可能注入点：

![image-20250227161821491](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621171.png)

#### Tmall_demo:

 项目：一个仿天猫的平台，进行审计找到fastjson漏洞

 ![image-20250227171325686](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621172.png)

然后再tmall里面找是否引用过fastjson的库和函数，直接全局搜索

![image-20250227171559745](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621173.png)

发现引用了fastjson的包，对应版本也有漏洞，然后还引用了对应的函数，那么就可以确定有洞：

![image-20250227171728213](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621174.png)

然后就找触发点、然后抓包：

![image-20250227172043052](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621175.png)

log4j：

![image-20250227172832245](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621176.png)

然后就抓到对应路径、触发点的数据包、更改文件名让其触发jndi注入：

![image-20250227172931104](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621177.png)

### 不回显

dnslog	dns协议一般是不会被限制的，是域名解析的。

![image-20250227173254287](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621178.png)

#业务设计




### url重定向：

 比如 https://weixin.qq.com?url=www.xiaodi8.com这种，www.xiaodi8.com的页面和weixin页面一样，实现钓鱼。

![image-20250304222552917](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621191.png)

黑盒思路：

![image-20250304222613534](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621192.png)

  制作钓鱼页面。

翻车到------- 

  隐私合规的结果

 资源拒绝服务

 ![image-20250226213857891](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621117.png)

就是对web资源的调用，占用他的资源。

 压缩包炸弹

### bilibili

burpjslinkfinder

前10介绍了几个好用的信息收集工具
