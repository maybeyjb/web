# xss

跨站脚本攻击

前端js代码接受输入数据，输出显示数据后解析执行。需要受害者触发。     浏览器前端解析输入的js代码，js代码会执行恶意的命令。

  弹窗，或者加载其他网站，跨站。

非持续性：	这种是攻击者发给你（受害者），诱导你点击进入跨站。（有点像钓鱼）

![image-20250226172156031](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621110.png)



#### 持续性：

存储型   持续性攻击：一般在留言板。插入后，当目标访问时候就会执行。

实战中利用的地方一般在交互式的地方比较多。

就比如管理员点开看你留言的盗取cookie的js前端语句时候，然后就被盗用cookie了。

#### dom型:

   对网页有操作，主要是针对网页的dom树，比如前端页面的url，标签这些。

![image-20250226180833292](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621111.png)

js里的语句是你要攻击的语句，一般写alert是方便演示，还可以将js改为盗取cookie的

  标签绕过：

需要绕过<img>标签

![image-20250226181842491](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621112.png)

[xss 常用标签及绕过姿势总结 - FreeBuf网络安全行业门户](https://www.freebuf.com/articles/web/340080.html)

![image-20250226181923209](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621113.png)

#### 演示

反射型	过滤了<script>	存在输入输出的地方。

![image-20250226182348180](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621114.png)

script被过滤

<img width="1299" height="1044" alt="image" src="https://github.com/user-attachments/assets/dd408536-d4e1-4802-bebf-e84d5123e080" />


#### 存储型

   这里实战技术就将这个语句写成盗用cookie的一些恶意语句。这里演示就只写一个弹窗。

<img width="1233" height="1142" alt="image" src="https://github.com/user-attachments/assets/c323798c-40fc-4f33-9fb7-8da20daed093" />

​	dom型      
![image-20250226213857891](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621117.png)

案例2：

![image-20250226214223782](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621118.png)

  后台里面计划任务写后门，然后用js写一个别人访问计划任务就会创建后门

小皮面板xss的rce

  跨站产生的地方

要注意存在输入输出。

# xss***



#### svg：

打开是一张图片，存在跨站。

![image-20250315231154976](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621119.png)

可以配合文件上传，

配合pdf和swf文件。

swf
