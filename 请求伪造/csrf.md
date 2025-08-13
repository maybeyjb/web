# csrf

跨站请求伪造：

www.com 攻击者	    你是受害者

你登录支付宝，向xd用户转账，发送alipay.com数据包请求，这时你又访问了www.com  网站，而www.com 上也有一个付款的数据包请求，那么这样你就触发了www.com 的付款数据包。实现了对你的csrf攻击。

付款请求是：www.com 触发的		请求伪造：伪造的是alipay.com数据包

那么条件：需要请求伪造数据包	受害者需要触发（就是访问了www.com  网站）	能绕过防护

用户访问恶意网站，然后攻击者就可以利用受害者的身份， 对已经登陆的正常网站发送数据包，达到篡改信息、修改配置等功能

##  测试利用csrf

1、在新增管理员的的时候抓包	2、抓到数据包生成csrf的poc	3、如图所示

1：就是受害者发送的数据包请求		3：就是相当于攻击者构造恶意相同的数据包

![image-20250226222758969](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621120.png)

将最后生成的html复制为1.html文件，然后访问1.html：

注意：这里bp是将刚才抓到的包drop，而不是放回/。将1.html上传到服务器。在用刚才抓包的浏览器访问此地址，因为有用户登录凭证，这就相当于模拟的是诱导受害者点击你构造的数据包。

<img width="968" height="660" alt="image" src="https://github.com/user-attachments/assets/7319e067-7f4d-47cc-85e5-9619ec9540a5" />


点击后回到我们的添加管理员页面发现成功添加刚才的账户。

![image-20250226223401254](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621123.png)

这个过程就是csrf。

## 同源策略

   检测referer字段  就是对你的来源进行检测，是不是同一个来源。这就可以避免上面的受害者点击构造的数据包时候检测出你的referer字段不是本地的地址

检测referer是外部访问就会拦截：

<img width="654" height="1021" alt="image" src="https://github.com/user-attachments/assets/6c22cc95-17f2-4565-8fbb-1127019e79b3" />


当策略不是十分严谨的话、这种重复发，就是猜测他的策略只是要referer中存在host就行：

但是在实战中，注意这时候触发是让受害者点击的，那受害者总不可能自己抓包该referer，所以可以创建类似这种referer的文件名，让他访问。（当然实战中比较鸡肋）

<img width="1236" height="774" alt="image" src="https://github.com/user-attachments/assets/051b26df-1274-4838-8847-e7df37295dbe" />


还有一种可能将referer去掉。

  不太严谨的话。添加一段去掉referer 、配合他的代码逻辑就可能会绕过。置空来源

<meta name="referrer" content="no-referrer">

<img width="1367" height="933" alt="image" src="https://github.com/user-attachments/assets/b56a22c8-8526-4827-b232-55d664f4b26b" />


全部对比，就是绕过严谨。配合xss或者上传（就是保证数据包的来源一致）

这种是很严谨的要么就是你将构造的数据包上传到目标受害者的服务器上，然后这个构造的包referer就是本身服务器的ip了。

  xss配合csrf  就是写一段js代码，然后调用里面的数据包文件，问gpt让它给你写一个恶意的代码。也是绕过严谨的一种方法。

#### csrf -token 

token 验证身份用的。好比给每一个数据包一个随机编号的。相当于一种令牌。

绕过：复用token	删除token	置空：token=

是存在token验证的。

![image-20250226231325721](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621127.png)

## 总结：
csrf利用较难
防御：
同源策略、验证 HTTP Referer 字段	
在请求地址中添加 token 并验证	
绕过:
尝试置空csrf的token 或者尝试复用。
