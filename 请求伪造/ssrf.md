
# ssrf

服务端请求伪造，服务器从外网访问内网，攻击的是服务器，

好比给服务器搜索框里一个127.0.0.1地址，让服务器自己访问自己。让服务端请求自己的伪造。SSRF攻击的目标是从外网无法访问的内部系统。

让服务器自己访问自己，如果这个地址改为内网地址，那么服务器就会请求它自己的内网机器 ：

![image-20250226232318466](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621128.png)

 检测端口，相当于内网探针。

![image-20250226233450556](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621129.png)

#### 伪协议

 伪协议绕过1、127.0.01进制转换 	

![image-20250226233606809](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621130.png)

### ctf利用+绕过

![image-20250226233743583](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621131.png)

限制127.0.0.1，本地地址。

![image-20250226234041732](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621132.png)

![image-20250226234123338](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621133.png)



短地址：使用在线生成一个域名地址指向127.0.0.1、然后你访问内网这个地址就是访问127.0.0.1

![image-20250226234425520](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621134.png)

申请一个域名指向127.0.0.1、对方访问你的域名时候，就指向了127.0.0.1、就等于访问自身。

![image-20250226234545909](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621135.png)

![image-20250226234612432](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621136.png)

[127.0.0.1](http://ctf@127.0.0.1/)   和  ctf@[127.0.0.1](http://ctf@127.0.0.1/)  访问的地址是一样的：

![image-20250227122642950](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621137.png)

 重定向 

### gopher 协议

gopher 协议  可以攻击类似数据库这种不走http协议的。攻击redis mysql服务这些、上面有漏洞。http是访问不了的，这就需要gopher 协议。

![image-20250227133821287](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621138.png)

Gopherus-master工具，将你需要执行的语句换成gopher协议的语句（有点像内网中将一个协议数据包换成另一种协议的数据包）：       执行写后门文件进去

![image-20250227133115442](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621139.png)

msyql   这里需要在url编译一次，因为你给过去它会url解码一次。

![image-20250227133543939](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621140.png)

  打redies：	未演示，下来自己复现。

[SSRF中Redis的利用_ssrf redis-CSDN博客](https://blog.csdn.net/2301_80127209/article/details/135772773)

 ssrf无回显

正反向，nc反弹   dnslog   写一个文件到网站目录，看文件是否存在。

#### 黑盒思路

这种就可能存在ssrf：

![image-20250227134543744](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621141.png)

![image-20250227134633669](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621142.png)

## 总结：
ssrf攻击的目标是从外网无法访问的内部系统。
防御：
禁用不需要的协议，只允许访问HTTP和HTTPS请求； 禁止跳转	
限制不能访问内网IP，防止对内网进行攻击；设置URL白名单或者限制内网IP
屏蔽或者过滤返回的详细信息；
绕过：
自然就是和防御对立了，127.0.0.1换成16/8进制，短域名等。
<img width="634" height="390" alt="image" src="https://github.com/user-attachments/assets/5af3343e-42e9-4ba3-b199-b4b4a3d15fd3" />


