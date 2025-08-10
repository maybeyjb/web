

#文件解析

### asp：

冷门语言，目前较少，主流是php java。

![image-20250311220054749](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621994.png)

 asp数据库是在网站路径下，是已经配置好了。目录下的mdb文件就是你的数据库，里面就是你的存储数据



![image-20250312133859662](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621995.png)

 打开网页演示。如果没有更改路径，就可以直接访问数据库文件下载。就是因为asp这种语言特性造成的，或者你可以将默认路径更改。

HTTP.SYS（CVE-2015-1635）   远程代码执行，就是让对方蓝屏，然后重启。

![image-20250311221526218](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621996.png)

直接用msf打，有这款漏洞专门的漏洞模块。

就是这种web页面，

![image-20250312134038112](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621997.png)

![image-20250312134143365](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621998.png)

 重新演示一遍

![image-20250312134356185](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621999.png)

### IIS短文件：

  基本是iis搭建的都可以尝试。

![image-20250311222441451](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621000.png)

![image-20250312135103610](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621001.png)

演示、用工具进行测试：

可以扫到网站目录下文件的前几位名字，比如说网站目录下有asdfghh文件夹，可以利用iis漏洞扫到存在asdfg....文件，一般都是前6位。

![image-20250312135051611](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621002.png)

### IIS 文件解析

一般都是IIS  6/7版本，常见6版本，7版本都是打补丁了，6 没有打。         一般都是配合文件上传

![image-20250311223211875](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621003.png)

  就是比如你上传是1.asp的后门，但是你可以将后门改为1.asp;.jpg这种文件，他还是可以解析你的1.asp后门，就是将你的1.asp;.jpg当成1.asp解析了，但是你在网站目录下看是1.asp;.jpg图片文件。

![image-20250312140248384](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621004.png)

还有一种是，文件夹。还是比如你上传1.asp的后门，但是放到了1.asp文件夹里，然后你的1.asp的后门改为1.jpg，这时候还是可以解析你的1.jsp为1.asp。也就是说将1.asp文件夹里面的文件都当成asp文件解析。

![image-20250312140253010](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621005.png)



### IIS写权限

![image-20250311224257731](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621006.png)

1h  IIS搭建的时候配置错误，导致可以写入文件。

https://cloud.tencent.com/developer/article/2050105

条件：

![image-20250312140614665](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621007.png)

![image-20250312140728058](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621008.png)



### sql-access：

数据库注入，access数据库注入，

![image-20250311224822166](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621009.png)

 sql注入

有时候你注入后，会返回404，这种有时候是代码逻辑的容错处理。就类似代码里的  try  exectp

![image-20250312141647221](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621010.png)

sqlmap直接跑。

 iis短文件。

![image-20250312143118088](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621011.png)



#php+sql



![image-20250220222643292](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621012.png)

![image-20250221213859480](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621013.png)

怎么判断是6位，order by 就行

这里判断的是2，4，5是注入点：

![image-20250221214917104](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621014.png)

![image-20250221215043145](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621015.png)

![image-20250221215548633](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621016.png)



![image-20250221211541336](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621017.png)

![image-20250221213433498](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621018.png)

### 跨库查询

![image-20250221220041287](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621019.png)



### 文件读

![image-20250220225859814](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621020.png)



![image-20250221222019801](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621021.png)

条件：1、当前数据库用户权限 	2、secure-file-priv设置 这里是对应的sql服务（MySQL5.7.26）的配置文件(my.ini)

![image-20250221222156924](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621022.png)

文件写：into outfile 条件和那个读一样：

![image-20250221223235480](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621023.png)



那么读写时候的路径是怎么确定的呢？比如说：D:\d\asdasd\ 你是怎么知道这个路径的：

1、有时候一些报错信息会有路径

2、读一些中间件的默认存储路径，获取web服务的路径，在写入shell到指定路径下。

![image-20250221224017903](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621024.png)

![image-20250221224644344](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621025.png)

### 单引号过滤

解决：单引号过滤绕过方式

SQL注入语句中用单引号就不要编码，编码就不用单引号（路径，表名，数据库名等）

![image-20250221225506726](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621026.png)












