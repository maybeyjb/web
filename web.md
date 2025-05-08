

# 41：文件解析

### asp：

冷门语言，目前较少，主流是php java。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/8063c925-fb63-4e98-8ba6-f7ceae56c5d4" />


 asp数据库是在网站路径下，是已经配置好了。目录下的mdb文件就是你的数据库，里面就是你的存储数据



<img width="420" alt="image" src="https://github.com/user-attachments/assets/8238b1a2-5461-4f0c-9c7d-ba520f4d3843" />

打开网页演示。如果没有更改路径，就可以直接访问数据库文件下载。就是因为asp这种语言特性造成的，或者你可以将默认路径更改。

HTTP.SYS（CVE-2015-1635）   远程代码执行，就是让对方蓝屏，然后重启。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c313f021-d212-4ccb-92b6-7f4276bd6c82" />


直接用msf打，有这款漏洞专门的漏洞模块。

就是这种web页面，

<img width="420" alt="image" src="https://github.com/user-attachments/assets/19e9a690-44fd-4c10-a221-8dbf58b062be" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/0435282e-fc3e-4a69-bd69-81f604603fb0" />


  重新演示一遍

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a7324d87-5660-4468-90dd-b8fec02a30f4" />


### IIS短文件：

  基本是iis搭建的都可以尝试。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/39afb124-f422-446e-a14c-cf67f6a7d7e8" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/5dba698e-1add-4fb4-96e2-71b432254db5" />


演示、用工具进行测试：

可以扫到网站目录下文件的前几位名字，比如说网站目录下有asdfghh文件夹，可以利用iis漏洞扫到存在asdfg....文件，一般都是前6位。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/75386bf3-49b0-4f6d-b558-77306422a9bf" />


### IIS 文件解析

一般都是IIS  6/7版本，常见6版本，7版本都是打补丁了，6 没有打。         一般都是配合文件上传

<img width="420" alt="image" src="https://github.com/user-attachments/assets/58de154d-1b55-4baf-b70d-98f5fa558afc" />


  就是比如你上传是1.asp的后门，但是你可以将后门改为1.asp;.jpg这种文件，他还是可以解析你的1.asp后门，就是将你的1.asp;.jpg当成1.asp解析了，但是你在网站目录下看是1.asp;.jpg图片文件。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/dd602bdf-985f-4ee1-b432-c61496269464" />


还有一种是，文件夹。还是比如你上传1.asp的后门，但是放到了1.asp文件夹里，然后你的1.asp的后门改为1.jpg，这时候还是可以解析你的1.jsp为1.asp。也就是说将1.asp文件夹里面的文件都当成asp文件解析。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/5693096f-c057-47da-b802-69b78f11a72e" />




### IIS写权限

<img width="420" alt="image" src="https://github.com/user-attachments/assets/9ed23299-51df-4d37-b339-b503d70d1f24" />


IIS搭建的时候配置错误，导致可以写入文件。

https://cloud.tencent.com/developer/article/2050105

条件：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c55891cd-7c0b-462a-bd0e-9cab6e2fc89a" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/07a5e0ee-e2f7-44ee-aaf9-8b06fb3053f2" />




### sql-access：

数据库注入，access数据库注入，

<img width="420" alt="image" src="https://github.com/user-attachments/assets/aaab2b1e-349c-4b53-9f03-0c8cc0991ddf" />


  sql注入

有时候你注入后，会返回404，这种有时候是代码逻辑的容错处理。就类似代码里的  try  exectp

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c820c969-a51a-4195-9b26-3672853ff38d" />


 sqlmap直接跑。

 iis短文件。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a5c06ccf-630b-42a6-8a71-c3b44cab24e2" />



# 42:php+sql



<img width="420" alt="image" src="https://github.com/user-attachments/assets/bb79cd70-55b0-4abb-bfc2-9bc26b37abea" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/ec1433d7-a4e2-494e-a195-e05cb05d87bd" />


怎么判断是6位，order by 就行

这里判断的是2，4，5是注入点：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/8e62b3d8-13b3-4271-96e8-d57b0a21279d" />




<img width="420" alt="image" src="https://github.com/user-attachments/assets/a5ebf612-1b62-41f7-ac4a-c526fe476d88" />






<img width="420" alt="image" src="https://github.com/user-attachments/assets/eafdd2d8-0c85-4906-9e66-1dfd805dc570" />


### 跨库查询

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c233aca0-7982-4813-9a3a-43b9622a16fe" />




### 文件读

<img width="420" alt="image" src="https://github.com/user-attachments/assets/cd45efba-9559-4860-aefb-fc630d1d5a35" />




<img width="420" alt="image" src="https://github.com/user-attachments/assets/62158d24-fed9-4a69-84ff-3dfc334d383b" />


条件：1、当前数据库用户权限 	2、secure-file-priv设置 这里是对应的sql服务（MySQL5.7.26）的配置文件(my.ini)

<img width="420" alt="image" src="https://github.com/user-attachments/assets/35f8657e-800c-455f-94ad-2ab3baaf4ab3" />


文件写：into outfile 条件和那个读一样：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/fb7684ad-891b-409a-a6ba-9da176999596" />




那么读写时候的路径是怎么确定的呢？比如说：D:\develop\phpstudy\phpstudy_pro\WWW\demo01  你是怎么知道这个路径的：

1、有时候一些报错信息会有路径

2、读一些中间件的默认存储路径，获取web服务的路径，在写入shell到指定路径下。
<img width="420" alt="image" src="https://github.com/user-attachments/assets/7661c1be-ffbd-46b8-8067-1f96ceb75690" />


<img width="214" alt="image" src="https://github.com/user-attachments/assets/cc63a29d-b0d8-4c57-923c-4bf6d0b992c0" />

### 单引号过滤

解决：单引号过滤绕过方式

SQL注入语句中用单引号就不要编码，编码就不用单引号（路径，表名，数据库名等）

<img width="420" alt="image" src="https://github.com/user-attachments/assets/2cf65c3f-bc8c-4ae8-959d-b0d8972b8cea" />





# 43:sql：

绕过这种()的：



<img width="420" alt="image" src="https://github.com/user-attachments/assets/e1b3da40-0511-4677-b408-bd6d924ae746" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/ae371ef4-35f6-477e-817a-f01d63a12c4c" />




有些注入点：

比如是上传文件，文件的名字会保存到数据库，这时候也会有sql注入的条件。

MYSQL-数据请求方法：

GET POST SERVER FILES HTTP头等。

这种是get的，post穿不了：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/fa0a54df-0af9-42ed-a740-98322d090802" />


post：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/3dc39851-358b-423a-931b-9c9a3fc24fdb" />


r就是对get post cookie都可以传

<img width="420" alt="image" src="https://github.com/user-attachments/assets/1d411499-a6dd-428b-a0f6-5b8252ee42a5" />


cookie传参

<img width="420" alt="image" src="https://github.com/user-attachments/assets/bf4790b3-0aff-48ca-84e4-597b442ea06b" />

这里注入后发现长度变化，存在注入。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/14fc59d2-3e8e-4374-bc64-e7416faa30d7" />


#### $_SERVER：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d538bb02-14bc-4953-82c7-440ff1c8cf7c" />


```
$_SERVER['HTTP_X_FORWARDED_FOR'];
这儿的也可以改为sql注入语句。
```

<img width="420" alt="image" src="https://github.com/user-attachments/assets/3eb74c45-638c-4abd-bdbe-cb7c489481e3" />


```
$_SERVER['HTTP_REFERER']; //访问来源 Referer
```



<img width="420" alt="image" src="https://github.com/user-attachments/assets/93682ec9-b17b-4633-8695-1e875818026f" />


抓包也发现这里的refer是baidu，是用baidu来跳转到method.php的

<img width="420" alt="image" src="https://github.com/user-attachments/assets/322a0e96-704c-4b42-9a67-5359e5b08562" />

#### 演示：

利用$_SERVER['HTTP_X_FORWARDED_FOR'];进行注入、xff注入：

X-FORWARDED-FOR：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/fd4b7591-9d71-4649-b43e-bf37c17d1bf0" />

<img width="420" alt="image" src="https://github.com/user-attachments/assets/ebf43b97-010d-45ab-bd96-83f14c20cae2" />


2、

IP配置到代码中 那就不是产生注入了，但这种可以绕过，就是让ip为127.0.0.1：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/7f2971bc-0f35-4cbb-9215-7b32e6f98dc3" />

  

得看网站是不是xff头绕过， 其他的具体对待分析。

那么难道Ip都能绕过吗，不是，是只有这种php的HTTP_X_FORWARDED_FOR能绕过，换一个函数或者或一个语言，就可能绕不了。

#### 请求格式

MYSQL-数据请求格式

base64的，那么对应的注入语句也应该是base64注入：
<img width="420" alt="image" src="https://github.com/user-attachments/assets/732ee775-b3ca-4027-a5ac-62b4294d7410" />


json：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d72b04f8-de11-4da9-bd7b-2c1daf812b9b" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/fd707959-bcc4-48c5-a46f-1cef4f7928d0" />


# 44：sql

### 增删改查

查select	增insert into  	删 delete	改update 

查是对数据进行操作,	增删改是对结果，就是看最后的结果，对数据内容不关心，关心的是增加成功没有。所以引出盲注。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e811bd19-9bc6-4cf5-9cdc-2c1484c0e8de" />


### 盲注：

正常注入：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/48ab9cd5-51cf-4ce9-9062-8415da95992a" />


没有回显的话：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/24214442-1722-4faa-bcba-6fb9acd5232b" />

所以就需要采用盲注

#### 布尔

	

布尔盲注：逻辑判断、就是猜数据库的名，条件：需要有回显

常用函数：regexp,like,ascii,left,ord,mid

<img width="420" alt="image" src="https://github.com/user-attachments/assets/03855a46-76e6-4e8f-adee-a36ec2bf754e" />


判断正确就正常回显，判断错误就无回显、判断数据库名前两位是不是dd	（demo01）：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b0c2694a-a9f1-4703-b41d-09c323120c47" />





####  延时

 延时注入 延时判断  不需要回显	 

条件：没有

 if   ,   sleep

<img width="336" alt="image" src="https://github.com/user-attachments/assets/9b0b6042-5426-4bba-83fc-435b0063a55f" />


延时注入：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/4e30f648-582d-4203-ac0c-319008a96a4c" />




####  报错

 报错注入：报错回显   

条件：需要对面做了报错处理

​<img width="420" alt="image" src="https://github.com/user-attachments/assets/72d5e1d9-d247-4a24-9002-fd61dadb908a" />


floor，updatexml，extractvalue	报错注入函数很多

<img width="420" alt="image" src="https://github.com/user-attachments/assets/8cc44e8a-29d5-42d8-8dd8-661cb433c6fc" />


文件上传怎么导致的xss注入，就是将文件名改成注入语句。

利用insert插入语句。

测试

<img width="420" alt="image" src="https://github.com/user-attachments/assets/17e7d752-db9f-495d-b893-d94f29cb89a7" />


源码分析这里是有报错处理函数的：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/8e7cdb35-2044-4b8e-9b43-64540264702e" />


报错注入、注意：这里id是没有1的，所以如果是1 and  就不会执行and后面的sql语句，所以这里是1 or

<img width="420" alt="image" src="https://github.com/user-attachments/assets/0413b276-1105-4e12-8c04-bdfbdc004881" />


### cms：

搭建cms演示。 

<img width="420" alt="image" src="https://github.com/user-attachments/assets/701c7711-23e0-4df8-8de6-347a16622e80" />

发现调用处在r=contact的发表言论这里，插入报错语句：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f9c44181-c0b7-4f0b-9769-a74d2a9e47e9" />




 kkcms

delete注入：数据包里有时候空格要换成%20，   而且对单引号过滤了，需要绕过：ascis 码绕过  这里看看16进制能不能绕过。

判断注入，找到调用的路径为admin/cms_usergroup.php?

<img width="420" alt="image" src="https://github.com/user-attachments/assets/941d91f7-5d90-4654-b901-0ce79f676578" />


进行注入，参数为get['del']：这里需要进行url编码，因为是在url框中的。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/342676f3-c948-4528-9617-d948789345a9" />


而且对单引号过滤 了，ascii绕过。ord就是转换用的。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c88d2c9b-ddb8-4997-b875-03b23e57a905" />


16进制也可以。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e84d4fec-86c7-4821-97a2-2abe961045a1" />


# 45：sql

### 二次注入

条件；注入条件：插入时有转义函数或配置，后续有利用插入的数据

<img width="420" alt="image" src="https://github.com/user-attachments/assets/07643841-3450-4f5d-b157-a4c0877e5a35" />


就是先插进去sql语句，二次数据库调用的时候引发sql注入。

演示二次注入

注册用户时候用户名带有sql语句：



然后登录注册的用户后点击更改密码，发现执行注入语句：
<img width="420" alt="image" src="https://github.com/user-attachments/assets/511b1650-ff4a-4843-b006-88723156f140" />


就是在你更改密码的时候，会对你的账户进行确认，确认你当前的用户名，此时产生注入。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/3bc430f7-b72b-4024-a4c9-3cf4229fed30" />

 开启转义函数

<img width="420" alt="image" src="https://github.com/user-attachments/assets/4372aade-573c-44c7-9225-fed65ae6577d" />


转义函数这会对单引号进行 / 处理

<img width="420" alt="image" src="https://github.com/user-attachments/assets/5a633553-aa99-424e-a7ac-446ef2a4dcb6" />


所以如果没有转义或魔术函数，就无法注入  addslashes() 	gcp()

不然你的注入语句不是字符串，或者就报错执行不了。这种函数其实是防止sql注入的，但是二次注入却利用到它。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f1591958-27e2-49a4-9aba-ce7e51a5df1f" />

cms演示  前端限制长度，更改

插入（sql语句）   +	 查看(调用插入的sql语言)	=	 二次注入



这里先插入：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e719ed6a-9798-4cf7-a3f3-138f58c809cc" />

在查看个人简历的时候就执行了sql语句，那么就成功进行二次注入。



###  堆叠注入

   mysqli_query()
在工具中：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/0287f167-0ded-4767-84fb-eaa87065278e" />


在注入中运行不行：

因为mysqli_query 是不支持多条sql语句执行，

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f197509a-5238-4621-a5f7-038478e3ae58" />


```
mysqli_multi_query支持多条sql语句。
```
<img width="420" alt="image" src="https://github.com/user-attachments/assets/7248e0e4-346e-4ab6-bc08-61170d69e9fc" />


支持还要看数据库类型支不支持。

ctf

dnslog  带外注入   	concat() 拼接符、带外的条件多

条件：ROOT高权限且支持load_file()   （高权限+那个开关）

能这样不如直接读取文件了。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/eefd5922-3160-4031-a433-ab7471848a16" />


## Mysql提权(讲得不错)：

<img width="378" alt="image" src="https://github.com/user-attachments/assets/210fac4d-2620-424a-9189-e37cb3af8d06" />


1、udf提权

[数据库提权系统---Mysql-udf提权 - 墨天轮 (modb.pro)](https://www.modb.pro/db/134200)

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f2df293f-bb38-42e6-970c-8a64ba8ea698" />


udf：就是自己定义的函数，一般都是dll文件，是c、c++写的。

利用ll这种动态链接库，可以调用cmd，实现的提权

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c8f413f0-5a6c-4a75-8857-8efc31dbdf43" />



条件： 	目录一般都是mysql安装目录

<img width="420" alt="image" src="https://github.com/user-attachments/assets/0cc508fe-ec63-49a7-a751-4234f109950c" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/766c44e8-db94-4d7d-a000-b2b94790155f" />

上传dll，sqlmap是自带dll文件的，我们只需通过webshell或者hex上传、

这里演示是通过hex上传：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/83dc77b6-2fe7-4dd5-b7c0-2f70ee56aa43" />


这里上传hex，可能会不允许上传，因为secure_file_priv设置的为null。就是禁止写入，所以需要设置为secure_file_priv=

<img width="420" alt="image" src="https://github.com/user-attachments/assets/86eceb23-729b-4565-a941-1423a4087c47" />


导出hex后，在新建一个表，导入上面导出的txt文件内容到表里面作为一个c的变量。也就是说此时c变量的值是udf.dll文件的hex值：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/5b9615c5-4a15-4b21-89a1-f07508f64bf8" />


然后在将对应的c值导到对应路径文件下，这里导出的对应路径文件需要用语法查。

然后查出来的路径如果没有对应文件就新建一个，路径保持一致、mysql索引目录

<img width="420" alt="image" src="https://github.com/user-attachments/assets/5b21156b-fccc-4cc8-81fe-5167049a0ced" />


下来就是利用导入的dll文件了。

1、4、创建一个函数(cmdshell)，用来执行udf.dll文件	5、利用自己创建的函数执行cmd命令

<img width="420" alt="image" src="https://github.com/user-attachments/assets/ad2ac87b-aacd-436d-a85e-6b8dcccdc597" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/c23cfd95-cf94-45f2-b62a-5c054196a879" />




[MYSQL数据库提权的几种方法——提权教程-CSDN博客](https://blog.csdn.net/weixin_40412037/article/details/112541157?ops_request_misc=%7B%22request%5Fid%22%3A%2204790aa6f51eeaec1d4d4ca72e5fe0e8%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=04790aa6f51eeaec1d4d4ca72e5fe0e8&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~baidu_landing_v2~default-1-112541157-null-null.142^v101^pc_search_result_base9&utm_term=mysql提权的几种方式&spm=1018.2226.3001.4187)

mof提权：mof也是windows系统的一个文件nullevt.mof、用mysql的root权限了以后，然后使用root权限去执行我们上传的mof。隔了一定时间以后这个mof就会被执行，这个mof当中有一段是vbs脚本，这个vbs大多数的是cmd的添加管理员用户的命令。

主要：用sql语句将系统当中默认的nullevt.mof给替换掉，让系统执行我们这个恶意的mof文件，来添加admin账户。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/da71f21b-0cde-4279-8dec-256605caa739" />


 启动项重启提权：

导出自定义bat或vbs到启动目录配合重启执行

自己写一个.bat文件里面是你的恶意命令、通过文件上传上传adduser.bat文件到网站根目录、在通过sql命令写入到启动项中、bat在对方重启后就会自启动执行恶意命令。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/25c569e5-0abd-49e2-ad2a-ba83981e139a" />


# 46：sqlmap  

 演示	sqlmap扫目标时候会自动创建一个目录用来保存你的注入结果。

使用默认字典猜库，mysql5.0后面会有information表，不用爆破。access数据库就是需要用字典进行爆破。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/75706f79-108d-41a4-a22d-4b96fac70ed7" />


扫到这种就是可能有sql注入点的：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a1e174e0-770d-42d0-8789-1e868d90fc10" />


高权限。

[1. sqlmap超详细笔记+思维导图 - bmjoker - 博客园 (cnblogs.com)](https://www.cnblogs.com/bmjoker/p/9326258.html)

--is-dba      #是否是数据库管理员 

  post注入  ：  --data + 参数

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e775342e-726e-40aa-9a16-9cae2a157d57" />


### 数据包-r

  数据包注入，整个数据包保存位txt文件放到sqlmap目录下在txt文件中的注入点加   *     直接  -r  + 目标数据包文件。

一般建议使用数据包进行注入，因为sqlmap注入时候，会用自己的请求头注入，但是有的数据包会识别，这时候就可能因为请求不同导致没有注入。所以用目标自身的数据包就成功几率大。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/edeb678f-1283-4a51-a852-874788e0dba4" />



然后保存到sqlmap目录下：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d7db8d7b-644b-4e10-a716-8e6f858086e2" />

当注入点为json数据注入不了，所以最好还是将目标的整个数据包拿出来进行注入。

### tamper
 tamper	base64编码注入

sqlmap自带tamper脚本目录，里面有py文件，针对一些加密编码，绕过一些过滤这些。  只需要后面加上--tamper= 对应脚本名称，即可。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c74458de-4ba6-4ff5-b2b8-ecd849999967" />

自己编写tamper脚本，针对一些过滤。

这里是过滤了一些关键字过滤。 主要是用到py的replace函数，设计绕过，就是处理替换字符串。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/179b0ef1-0af4-4fb8-aeda-d8d13ed3dc85" />

 -v参数  提升注入等级、就会注入http头，cookie、注入的参数变多了。然后自身也会用一些绕过姿势尝试。
<img width="420" alt="image" src="https://github.com/user-attachments/assets/92576fab-9dfe-4fab-b67b-4514f1c8f39a" />

 加代理，配合bp

47



# 48: 文件上传

apache 换行解析漏洞

 docker拉取环境	

apache对应版本搭建的web服务，存在文件上传功能，两个配合着进行拿shell。

### 没看完















49



# 50：文件包含

包含的，就是方便开发使用：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/735e8af3-0d75-41f2-b506-eefcffe7851f" />


就是产生在你s调用包含文件的时候，比如php里面的 include 'config.php' ，这样就方便直接调用config.php里面的文件，就不需要你在重新写一遍config.php里的代码，但是如果这里的config.php可以控制，就容易产生问题。

PHP：include、require、include_once、require_once等

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d6ffcab7-2bc6-4fd6-b0a6-53ffb3a4ca82" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/a3b3e4f5-fe80-434e-8441-d0c0d26349c0" />


 演示   远程文件包含	条件：远程包含开关开启	只需要改远程文件，实现远程rce

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f09b7f13-7f04-4f5b-893e-0d99a3ba9142" />



那么显然：漏洞的成因：1、使用了文件包含函数	2、包含的文件是可控的

自然，上面file后面也可以是一个远程的地址文件，实现远程代码执行。也就是远程文件包含：

需要先开启远程包含或者代码中为on
<img width="420" alt="image" src="https://github.com/user-attachments/assets/f6295a83-bb0c-409b-bf6a-2fc2d09b5735" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/52b450e5-4e62-465b-83ff-6b3241ebe0c5" />


但是还是比较鸡肋，因为在php高版本以上都是关的。

  利用

本地包含：1、有文件 利用 	2、无文件利用

有文件利用：（有文件上传点）

<?php eval($_post['pass']);?> 

那就直接上传我们的后门文件。





#### 无文件利用

无文件利用（也就是说没有上传文件点） ：

1、伪协议 	2、文件读取       ，  3、文件写入 	代码执行	

1、配合文件上传

2、无文件包含日志

3、无文件包含SESSION

4、无文件支持伪协议利用

文件读取：file是需要绝对路径	php只需要相对路径，进行base64编码，这里是规则。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/7329bd4c-e0f9-499d-b578-c81156620515" />


 演示

1、发现可能 存在文件读取

<img width="420" alt="image" src="https://github.com/user-attachments/assets/5828b80b-dcb1-4c92-b6d8-35d2740d37cc" />

  ctf

利用日志包含，日志记录功能。 

这里过滤了php字段，就用data协议：
<img width="420" alt="image" src="https://github.com/user-attachments/assets/67778571-182b-4e82-b6f7-cd48c49f50ab" />


既过滤data又过滤了php，这里就用到日志包含：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/7cf91737-0e99-4c04-a81c-4a49ed0ec29f" />


并且发现这里的日志会记录一会ua头等信息，就尝试能不能写入ua头里的shell，从而拿shell：

![image-20250315183455001](E:\新建文件夹\新建文件夹\typora学习笔记软件\缓存\image-20250315183455001.png)

SESSION包含：

利用session，访问会自己存储到默认路径下，那么就利用这点，实现包含.

  session 每次访问网站时，会自动产生对应的seesion	但是访问完会删除session文件，清空。所以这里就是条件竞争，一直发包让其将session里面的语句写入。这样：

![image-20250312220659445](E:\新建文件夹\新建文件夹\typora学习笔记软件\缓存\image-20250312220659445.png)

![image-20250315220829611](E:\新建文件夹\新建文件夹\typora学习笔记软件\缓存\image-20250315220829611.png)

就是条件竞争，一直发包让其写入，然后客户端一直访问网站，让服务器触发发的包：

![image-20250315221134839](E:\新建文件夹\新建文件夹\typora学习笔记软件\缓存\image-20250315221134839.png)
xss

跨站脚本攻击

前端js代码接受输入数据，输出显示数据后解析执行。需要受害者触发。     浏览器前端解析输入的js代码，js代码会执行恶意的命令。

弹窗，或者加载其他网站，跨站。

非持续性：	这种是攻击者发给你（受害者），诱导你点击进入跨站。（有点像钓鱼）

<img width="420" alt="image" src="https://github.com/user-attachments/assets/3058d5fb-a650-431a-9530-322d03fa56eb" />




#### 持续性：

存储型   持续性攻击：一般在留言板。插入后，当目标访问时候就会执行。

实战中利用的地方一般在交互式的地方比较多。

就比如管理员点开看你留言的盗取cookie的js前端语句时候，然后就被盗用cookie了。

#### dom型:

  对网页有操作，主要是针对网页的dom树，比如前端页面的url，标签这些。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b9a77237-e537-43c1-bf7b-46b2b00a6f1c" />


js里的语句是你要攻击的语句，一般写alert是方便演示，还可以将js改为盗取cookie的

标签绕过：

需要绕过<img>标签

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d455bb61-f9aa-4ce1-b3c1-c5d72c9bddd3" />


[xss 常用标签及绕过姿势总结 - FreeBuf网络安全行业门户](https://www.freebuf.com/articles/web/340080.html)

<img width="420" alt="image" src="https://github.com/user-attachments/assets/720cb3fd-0943-4603-9d77-7280fa255714" />


#### 演示

反射型	过滤了<script>	存在输入输出的地方。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/223bc75e-1287-4587-8b4b-6a037c6f660d" />


<script>被过滤

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f851a4be-63eb-4e81-b9ec-edce6b8aca31" />


#### 存储型

这里实战技术就将这个语句写成盗用cookie的一些恶意语句。这里演示就只写一个弹窗。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/4845a184-f6d7-4e83-a430-ee68081a834c" />


dom型      
<img width="420" alt="image" src="https://github.com/user-attachments/assets/40611f9d-f0e4-4581-b85d-9426fd8c2339" />


案例2：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/227c7baf-542a-4bdb-9564-9c93f845727a" />




后台里面计划任务写后门，然后用js写一个别人访问计划任务就会创建后门

小皮面板xss的rce

 跨站产生的地方

要注意存在输入输出。

# 53：xss***



#### svg：

打开是一张图片，存在跨站。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b3f77503-f004-46ff-bbae-7bac0e3cba6e" />


可以配合文件上传，

配合pdf和swf文件。

swf
# 56：csrf

跨站请求伪造：

www.com 攻击者	    你是受害者

你登录支付宝，向xd用户转账，发送alipay.com数据包请求，这时你又访问了www.com  网站，而www.com 上也有一个付款的数据包请求，那么这样你就触发了www.com 的付款数据包。实现了对你的csrf攻击。

付款请求是：www.com 触发的		请求伪造：伪造的是alipay.com数据包

那么条件：需要请求伪造数据包	受害者需要触发（就是访问了www.com  网站）	能绕过防护

用户访问恶意网站，然后攻击者就可以利用受害者的身份， 对已经登陆的正常网站发送数据包，达到篡改信息、修改配置等功能

测试csrf

1、在新增管理员的的时候抓包	2、抓到数据包生成csrf的poc	3、如图所示

1：就是受害者发送的数据包请求		3：就是相当于攻击者构造恶意相同的数据包

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b64acd59-9b38-4afa-abff-f965b5849fd4" />

将最后生成的html复制为1.html文件，然后访问1.html：

注意：这里bp是将刚才抓到的包drop，而不是放回/。将1.html上传到服务器。在用刚才抓包的浏览器访问此地址，因为有用户登录凭证，这就相当于模拟的是诱导受害者点击你构造的数据包。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/7a1d0921-5494-4c36-b128-992d48096444" />

点击后回到我们的添加管理员页面发现成功添加刚才的账户。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/df5b872e-97bf-48a9-9ff9-64a947fb2e04" />


这个过程就是csrf。

#### 同源策略

 检测referer字段  就是对你的来源进行检测，是不是同一个来源。这就可以避免上面的受害者点击构造的数据包时候检测出你的referer字段不是本地的地址

检测referer是外部访问就会拦截：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a72fd74b-bfc0-4fa2-93ab-7fd62ae7c585" />


 当策略不是十分严谨的话、这种重复发，就是猜测他的策略只是要referer中存在host就行：

但是在实战中，注意这时候触发是让受害者点击的，那受害者总不可能自己抓包该referer，所以可以创建类似这种referer的文件名，让他访问。（当然实战中比较鸡肋）

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c0331cea-364b-4005-8058-1779417cbf06" />


还有一种可能将referer去掉。

不太严谨的话。添加一段去掉referer 、配合他的代码逻辑就可能会绕过。置空来源

<meta name="referrer" content="no-referrer">

<img width="420" alt="image" src="https://github.com/user-attachments/assets/f5b84cf6-b5d8-4246-b038-8cb0ee618d01" />


全部对比，就是绕过严谨。配合xss或者上传（就是保证数据包的来源一致）

这种是很严谨的要么就是你将构造的数据包上传到目标受害者的服务器上，然后这个构造的包referer就是本身服务器的ip了。

xss配合csrf  就是写一段js代码，然后调用里面的数据包文件，问gpt让它给你写一个恶意的代码。也是绕过严谨的一种方法。

#### csrf -token 

token 验证身份用的。好比给每一个数据包一个随机编号的。相当于一种令牌。

绕过：复用token	删除token	置空：token=

是存在token验证的。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/902c82a3-862d-4d33-8414-8b62beb26a92" />


# 57：ssrf

服务端请求伪造，服务器从外网访问内网，攻击的是服务器，

好比给服务器搜索框里一个127.0.0.1地址，让服务器自己访问自己。让服务端请求自己的伪造。SSRF攻击的目标是从外网无法访问的内部系统。

让服务器自己访问自己，如果这个地址改为内网地址，那么服务器就会请求它自己的内网机器 ：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d423ddf4-f93d-48ba-822f-c57c096d04dc" />

 检测端口，相当于内网探针。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/608629b0-372a-4e76-85ba-b8a1031fd433" />


#### 伪协议

 伪协议绕过1、127.0.01进制转换 	

<img width="420" alt="image" src="https://github.com/user-attachments/assets/ed2496b8-2854-468a-a54c-fc365b695828" />


### ctf

<img width="420" alt="image" src="https://github.com/user-attachments/assets/cba0edca-5d64-4a31-8ed8-d230fd3869e3" />

限制127.0.0.1，本地地址。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/439a31c6-d840-4efc-b07e-e4785e4fd2de" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/dc59042e-c586-410a-be0d-17c936b4b888" />



短地址：使用在线生成一个域名地址指向127.0.0.1、然后你访问内网这个地址就是访问127.0.0.1

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b7dde1e9-63d4-4ed5-b583-160b583cd94d" />


申请一个域名指向127.0.0.1、对方访问你的域名时候，就指向了127.0.0.1、就等于访问自身。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/63a2a7bf-9e58-467e-a31c-655906c59e32" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/a0fb0e5f-58f6-4248-bce2-630b2147b61b" />

[127.0.0.1](http://ctf@127.0.0.1/)   和  ctf@[127.0.0.1](http://ctf@127.0.0.1/)  访问的地址是一样的：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b3547682-5ab6-42b5-9520-169d947b5ee2" />

 重定向 

### gopher 协议

 gopher 协议  可以攻击类似数据库这种不走http协议的。攻击redis mysql服务这些、上面有漏洞。http是访问不了的，这就需要gopher 协议。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/82ab6d35-72de-4b4d-bdd6-bdfa32589beb" />


Gopherus-master工具，将你需要执行的语句换成gopher协议的语句（有点像内网中将一个协议数据包换成另一种协议的数据包）：       执行写后门文件进去

<img width="420" alt="image" src="https://github.com/user-attachments/assets/92f37313-09fb-4d52-868e-4edf0a9a9387" />


msyql   这里需要在url编译一次，因为你给过去它会url解码一次。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/bbc8ddf7-a793-4e5d-8b3c-fa93793fd008" />

  打redies：	未演示，下来自己复现。

[SSRF中Redis的利用_ssrf redis-CSDN博客](https://blog.csdn.net/2301_80127209/article/details/135772773)

 ssrf无回显

正反向，nc反弹   dnslog   写一个文件到网站目录，看文件是否存在。

#### 黑盒思路

  

这种就可能存在ssrf：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/aaf3049a-c5b9-467c-a250-91c3ef2b9fb4" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/a36ee5ce-be0b-4bd8-b94f-619f386dcb5d" />



# 66：java  

两个靶场，javasec   

 配置注意。
 cors跨域资源共享--太鸡肋了，危害较低。

java里面操作数据库的。
​			

### jdbc

java里面的sql注入代审，语句拼接。危险写法和安全写法。原生态的。	

1看有没有用这两个方法，2看有没有使用下面的安全写法。有1无2，那就可以尝试jdbc注入

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a632ad78-8dae-49bf-abd4-410c98eea5a2" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/6dba7d03-407f-4021-b2a0-5e4a10df8994" />




### mybatis

  就是java里的数据库操作。常用的。

1看是不是用$  2看是不是用order by 、like 、in 这些语句

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e4043209-92b8-4562-80ab-e7502823db3f" />


java里面看sql是否有sql注入，那么就看是mybatis还是jdbc，然后看是$# 这些字符，预编译字符，进行排查有没有一些拼接之类的。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/4fbfbaab-ece3-4227-8285-0401142f5d11" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/32bb61db-6ed4-41dd-88ff-577f32c7f7e6" />


----翻车---

搭建靶场  java的网校靶场

黑盒就是，点测

白盒：先看pom.xml  看是用的jdbc还是mybatis来处理数据操作（还有以一个hibernate），这三个都是java里面操作数据库的。关注$#这些， 搜${   或者%${     或者   （${	主要还是$符号  然后不看jsp这些html带啊吗，关注java

#为安全写法，主要关注点位$不安全写法：

先打开源码发现有引用mybatis，然后猜测有没有引用sql的不安全写法。2、发现存在，这里一般不关注jsp，这类静态文件	3、定位到变量	4、看引用的id为什么，继续向上查找引用id的路由。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/8e00164d-3ca6-4f92-b94a-30371b9ed65d" />


1、查找引用id的	2、关注一些controller文件	3、定位	4、在delete模块	5、admin路径（路由）下

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d05d8dbd-b6cd-40d5-bc93-2d56232af207" />


分析发现可能存在sql注入，用sqlmap跑

找到了对应路由，这里不能直接访问，是找出来的，根据上面的delete提醒找到：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a4f31a88-da30-4dcc-acb5-15f84a350b06" />


将抓到的数据包测试，在将发送的articelid参数注入点加上，直接就sqlmap跑、：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/3747edb6-0b53-4c36-8659-a0d590b0d8e0" />


这里注意：复制数据包时候是选原始在复制：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d030466d-98c7-42b6-9edf-cd3a6d5825d1" />


### xml实体注入：

	
<img width="420" alt="image" src="https://github.com/user-attachments/assets/06bacb34-43cf-427e-9478-19ee356a5bec" />




<img width="420" alt="image" src="https://github.com/user-attachments/assets/0982c5b3-04df-4015-acaa-d09a055da7ce" />


黑盒就是看数据包是不是xml格式，然后插入dns外带试一下。



### SSTI模板注入



SSTI模版         spring boot 框架的。不同框架。	ognl jstl  是一些过时框架的。	ssti的几个可能有漏洞的模板

<img width="420" alt="image" src="https://github.com/user-attachments/assets/1fbe3003-6d54-400d-8bcb-20f299d1d21e" />


就是模板，将别人的模板中的参数，插入自己的语句，然后实现rce。就比如有的页面，lang=en 然后就是英文页面，lang=cn  就是中文页面，这时候你就尝试改lang后面的参数，看能不能实现rce

参数就是让你渲染别的页面，这页面就是模板，参数可以替换成自己的命令,实现rce。lang参数直接改之类的。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/77ac0b7e-a143-424c-ab33-3efa8c5c35c1" />




<img width="420" alt="image" src="https://github.com/user-attachments/assets/79bb7425-cce8-4d55-9f88-4c22a9cb6f9a" />


### SPEL表达式注入

	SPEL表达式	ognl表达式注入(老了)	spel就好比php中的eval	java特有的

<img width="420" alt="image" src="https://github.com/user-attachments/assets/876cb512-cd01-4de5-914f-606555255578" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/4090fc04-1ca3-4a7a-a6b0-5194b5a3bacc" />


绕过黑名单：

利用反射机制的方法。--- forname   getclass	这些方法。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e4340362-6726-4e95-868d-6cf25c39d4c3" />








# 67：java组件

#### rce函数：

测试通过函数或者参数，url中是否存在这些函数类：

<img width="349" alt="image" src="https://github.com/user-attachments/assets/fa5da90d-76ea-4479-853d-79aad418526c" />


RuntimeExec

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d5288202-2b6f-4d1a-8750-2013f70e70a0" />


 	ScriptEngineManager  jdk1.8之前的、用处不大，jdk太老了/

<img width="420" alt="image" src="https://github.com/user-attachments/assets/85b72a46-720d-43f1-aa6b-4dbccf57a112" />

Groovy


							 ProcessBuilder

<img width="420" alt="image" src="https://github.com/user-attachments/assets/a7b23936-210f-417b-81f4-64bee7a2bc69" />


 ProcessImpl

黑盒中就是看参数，url，功能点测试rce。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/cd572611-4d8b-4518-9495-5c97fae21169" />


####  jndi

java去远程调用rmi和loap协议调用出的rce

利用：

主要用jndi的jar包注入工具，利用工具远程生成一个恶意代码的.class文件，然后调用远程地址加载恶意语句注入。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/46495c64-64c8-414f-b704-efd94da7587e" />


远程调用方法，远程加载.class文件调用执行

jndi是一个内置功能，是java的技术，里面的RMI：远程方法调用注册表	LDAP：轻量级目录访问协议  两个协议常用，不是作为漏洞打的，是作为java漏洞利用方法，利用这个jndi方法来实现漏洞。

就比如说log4j有漏洞，就用jndi注入测试他的rce。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/bb1b397e-7503-44c9-9256-1c94f45a288f" />


rmi和ldap的差异：

限制的java版本编号不同

高版本绕过：[如何绕过高版本JDK的限制进行JNDI注入利用 – KINGX](https://kingx.me/Restrictions-and-Bypass-of-JNDI-Manipulations-RCE.html)

需要分析代码和调用等问题。不过有工具

### 不安全组件

 log4j  基于Java的日志记录框架

logger.error    logger.info

<img width="420" alt="image" src="https://github.com/user-attachments/assets/ecd7bb58-09e1-4c44-b7fa-a153c6f31e6e" />


漏洞库	 https://avd.aliyun.com/search?q=Log4j

FastJson	json解析器，它可以解析JSON格式的字符串，支持将JavaBean序列化为JSON字符串，也可以从JSON字符串反序列化到JavaBean。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/969095d1-865d-4eaa-b5fe-fead5b7872ff" />					 
							
靶场演示	配合aliyun漏洞库

shiro 数据包中的cookie中有remerberme   shiro  能够用于身份验证、授权、加密和会话管理。

XStream 反序列化：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/9b967119-886a-4543-8baf-74fed9e4f7a5" />


Log4j 记录日志的、一般会解析日志：

那黑盒一般测试：一般用dnslog带外测试是否存在可能注入点：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/17d318b6-0cfd-4ae4-8648-f7949b14227c" />

#### Tmall_demo:


项目：一个仿天猫的平台，进行审计找到fastjson漏洞

<img width="420" alt="image" src="https://github.com/user-attachments/assets/03ff8682-4702-447b-af1e-cc9b9478c2e2" />


然后再tmall里面找是否引用过fastjson的库和函数，直接全局搜索

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d070da22-e15f-4e0f-af43-88cfd1cd52de" />


发现引用了fastjson的包，对应版本也有漏洞，然后还引用了对应的函数，那么就可以确定有洞：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/24df5e00-2903-45a5-938f-c469280ad8aa" />


然后就找触发点、然后抓包：


log4j：


然后就抓到对应路径、触发点的数据包、更改文件名让其触发jndi注入：



### 不回显

dnslog	dns协议一般是不会被限制的，是域名解析的。


# 



# 77：业务设计



### 隐私合规

app商家不合规，就是你手机打开会请求权限，什么允许请求你的通讯录，什么请求你的位置。请求你的摄像头、麦克风。正确就是需要请求，如果没有请求那么就不合规。


一些测试的工具mobsf(不是专门的测隐私合规的，可以测app)、appshark（静态分析）、appscan（动态分析）------ 所以这个比较好。https://appscan.ly.com/   

<img width="420" alt="image" src="https://github.com/user-attachments/assets/9ed1f5d3-2417-4938-adc2-e10571ccf393" />


不过用这个工具不能在模拟机中，只能在真机中，而且需要开root。

小程序也可以测，不过大部分都是app。


##### 2:bilibili

权限，个人信息等信息。

小程序直接跳转app，看是第一次还是已经在隐私政策中规定了。

权限弹窗。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/e24b5649-ae1b-49ae-9a33-df570c308a8b" />

2、就是这种app(计算器)是没有必要获取位置

<img width="420" alt="image" src="https://github.com/user-attachments/assets/dcb9106b-4e36-41cd-b780-0606de0f5245" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/5f05a334-f607-4091-ab73-f6eeda542ee9" />


等这种字眼
<img width="420" alt="image" src="https://github.com/user-attachments/assets/53d85616-faaa-44a1-9368-459dbb67b35c" />


例子：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/55782ed7-601b-4eed-b49f-8a17355b7fcf" />


<img width="420" alt="image" src="https://github.com/user-attachments/assets/5a179144-ad20-4630-803d-f832f9210cf4" />


hook：就是你动态调试app时候，然后看着其调用的类

<img width="420" alt="image" src="https://github.com/user-attachments/assets/6ff1dcc0-976e-443f-b2e5-f47be1edf53a" />


或者要你的权限过了、就是此时是你第一次使用它，那么当时的场景你申请查询信用评估是不符合隐私合规：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/c42fc705-a979-4a66-ab59-7ab66b7e73a5" />


利用用户不看条款：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/b063115a-a1dc-4868-99fe-0333170b04a1" />


位置权限：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/649bc346-82a6-4f50-bac0-acb47a1dec0d" />





### url重定向：

比如 https://weixin.qq.com?url=www.xiaodi8.com这种，www.xiaodi8.com的页面和weixin页面一样，实现钓鱼。

<img width="420" alt="image" src="https://github.com/user-attachments/assets/d73b6e34-af9f-4a1e-946c-3712e04e0b33" />


黑盒思路：

<img width="420" alt="image" src="https://github.com/user-attachments/assets/243e4ba2-39fd-4d21-9641-8285a976f565" />


制作钓鱼页面。

翻车到-------

  隐私合规的结果

 资源拒绝服务

<img width="420" alt="image" src="https://github.com/user-attachments/assets/309555a3-0a47-4621-b050-7f24e0970218" />


就是对web资源的调用，占用他的资源。

 压缩包炸弹
