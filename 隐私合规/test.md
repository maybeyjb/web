
### 隐私合规

app商家不合规，就是你手机打开会请求权限，什么允许请求你的通讯录，什么请求你的位置。请求你的摄像头、麦克风。正确就是需要请求，如果没有请求那么就不合规。

 ![image-20250304210850535](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621179.png)

一些测试的工具mobsf(不是专门的测隐私合规的，可以测app)、appshark（静态分析）、appscan（动态分析）------ 所以这个比较好。https://appscan.ly.com/   

![image-20250304211028915](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621180.png)

不过用这个工具不能在模拟机中，只能在真机中，而且需要开root。

小程序也可以测，不过大部分都是app。

 这里演示的是mobsf：

##### 2

权限，个人信息等信息。

小程序直接跳转app，看是第一次还是已经在隐私政策中规定了。

权限弹窗。



![image-20250304231334253](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621181.png)

2、就是这种app(计算器)是没有必要获取位置

![image-20250304231445413](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621182.png)

![image-20250304231720972](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621183.png)

等这种字眼

![image-20250304231838355](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621184.png)

例子：

![image-20250304232202822](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621185.png)

![image-20250304232307239](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621186.png)

hook：就是你动态调试app时候，然后看着其调用的类

![image-20250304233233079](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621187.png)

或者要你的权限过了、就是此时是你第一次使用它，那么当时的场景你申请查询信用评估是不符合隐私合规：

![image-20250304232456903](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621188.png)

利用用户不看条款：

![image-20250304232605973](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621189.png)

位置权限：

![image-20250304232718548](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621190.png)

