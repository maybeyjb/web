
# sql：

绕过这种()的：



![image-20250222210208298](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621027.png)

![image-20250222213606401](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621028.png)



有些注入点：

比如是上传文件，文件的名字会保存到数据库，这时候也会有sql注入的条件。

MYSQL-数据请求方法：

GET POST SERVER FILES HTTP头等。

这种是get的，post穿不了：

![image-20250222214235415](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621029.png)

post：

![image-20250222214851722](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621030.png)

r就是对get post cookie都可以传

![image-20250222215212683](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621031.png)

cookie传参

![image-20250222215449075](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621032.png)

这里注入后发现长度变化，存在注入。

![image-20250222223045654](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621033.png)

#### $_SERVER：

![image-20250222224804627](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621034.png)

```
$_SERVER['HTTP_X_FORWARDED_FOR'];
这儿的也可以改为sql注入语句。
```

![image-20250222225701236](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621035.png)

```
$_SERVER['HTTP_REFERER']; //访问来源 Referer
```



![image-20250222230309585](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621036.png)

抓包也发现这里的refer是baidu，是用baidu来跳转到method.php的

![image-20250222230422440](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621037.png)

#### 演示：

利用$_SERVER['HTTP_X_FORWARDED_FOR'];进行注入、xff注入：

X-FORWARDED-FOR：

![image-20250223142544594](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621038.png)

![image-20250223142752286](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621039.png)

2、

IP配置到代码中 那就不是产生注入了，但这种可以绕过，就是让ip为127.0.0.1：

![image-20250223143032490](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621040.png)

  

得看网站是不是xff头绕过， 其他的具体对待分析。

那么难道Ip都能绕过吗，不是，是只有这种php的HTTP_X_FORWARDED_FOR能绕过，换一个函数或者或一个语言，就可能绕不了。

#### 请求格式

MYSQL-数据请求格式

base64的，那么对应的注入语句也应该是base64注入：

![image-20250223144213151](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621041.png)

json：

![image-20250223144435249](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621042.png)

![image-20250223144612138](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621043.png)

# sql

### 增删改查

查select	增insert into  	删 delete	改update 

查是对数据进行操作,	增删改是对结果，就是看最后的结果，对数据内容不关心，关心的是增加成功没有。所以引出盲注。

![image-20250224150113472](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621045.png)

### 盲注：

正常注入：

![image-20250224151157912](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621046.png)

没有回显的话：

![image-20250224151234669](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621047.png)

所以就需要采用盲注

#### 布尔

布尔盲注：逻辑判断、就是猜数据库的名，条件：需要有回显

常用函数：regexp,like,ascii,left,ord,mid

![image-20250224152207317](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621048.png)

判断正确就正常回显，判断错误就无回显、判断数据库名前两位是不是dd	（demo01）：

![image-20250224152143650](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621049.png)



####  延时

延时注入 延时判断  不需要回显	 

条件：没有

 if   ,   sleep

![image-20250224152800658](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621050.png)

延时注入：

![image-20250224153139630](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621051.png)



####  报错

报错注入：报错回显   

条件：需要对面做了报错处理

​	![image-20250224154111711](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621052.png)

floor，updatexml，extractvalue	报错注入函数很多

![image-20250224154315682](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621053.png)

文件上传怎么导致的xss注入，就是将文件名改成注入语句。

利用insert插入语句。

 测试

![image-20250224155957483](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621054.png)

源码分析这里是有报错处理函数的：

![image-20250224155619870](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621055.png)

报错注入、注意：这里id是没有1的，所以如果是1 and  就不会执行and后面的sql语句，所以这里是1 or

![image-20250224155819825](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621056.png)

### cms：

搭建cms演示。

![image-20250224164119208](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621057.png)

发现调用处在r=contact的发表言论这里，插入报错语句：

![image-20250224164143834](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621058.png)



kkcms

delete注入：数据包里有时候空格要换成%20，   而且对单引号过滤了，需要绕过：ascis 码绕过  这里看看16进制能不能绕过。

判断注入，找到调用的路径为admin/cms_usergroup.php?

![image-20250224170542822](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621059.png)

进行注入，参数为get['del']：这里需要进行url编码，因为是在url框中的。

![image-20250224170657808](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621060.png)

而且对单引号过滤 了，ascii绕过。ord就是转换用的。

![image-20250224171135954](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621061.png)

16进制也可以。

![image-20250224171258704](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621062.png)

#sql

### 二次注入

条件；注入条件：插入时有转义函数或配置，后续有利用插入的数据

![image-20250224183636259](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621063.png)

就是先插进去sql语句，二次数据库调用的时候引发sql注入。

演示二次注入

注册用户时候用户名带有sql语句：

![image-20250224181757829](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621064.png)

然后登录注册的用户后点击更改密码，发现执行注入语句：

![image-20250224182107620](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621065.png)

就是在你更改密码的时候，会对你的账户进行确认，确认你当前的用户名，此时产生注入。

![image-20250224182525155](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621066.png)

开启转义函数

![image-20250224183503226](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621067.png)

转义函数这会对单引号进行 / 处理

![image-20250224183536088](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621068.png)

所以如果没有转义或魔术函数，就无法注入  addslashes() 	gcp()

不然你的注入语句不是字符串，或者就报错执行不了。这种函数其实是防止sql注入的，但是二次注入却利用到它。

![image-20250224184312821](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621069.png)

cms演示  前端限制长度，更改

插入（sql语句）   +	 查看(调用插入的sql语言)	=	 二次注入



这里先插入：

![image-20250224214030169](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621070.png)

在查看个人简历的时候就执行了sql语句，那么就成功进行二次注入。



###  堆叠注入

 mysqli_query()
在工具中：

![image-20250224215840629](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621071.png)

在注入中运行不行：

因为mysqli_query 是不支持多条sql语句执行，

![image-20250224220115520](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621072.png)

```
mysqli_multi_query支持多条sql语句。
```

![image-20250224220309259](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621073.png)

支持还要看数据库类型支不支持。

ctf

dnslog  带外注入   	concat() 拼接符、带外的条件多

条件：ROOT高权限且支持load_file()   （高权限+那个开关）

能这样不如直接读取文件了。

![image-20250224221048656](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621074.png)

## Mysql提权：

![image-20250305214318603](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621075.png)

1、udf提权

[数据库提权系统---Mysql-udf提权 - 墨天轮 (modb.pro)](https://www.modb.pro/db/134200)

![image-20250305214343452](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621076.png)

udf：就是自己定义的函数，一般都是dll文件，是c、c++写的。

利用ll这种动态链接库，可以调用cmd，实现的提权

![image-20250305214514841](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621077.png)

条件： 	目录一般都是mysql安装目录

![image-20250305214533128](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621078.png)

![image-20250305214734668](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621079.png)

上传dll，sqlmap是自带dll文件的，我们只需通过webshell或者hex上传、

这里演示是通过hex上传：

<img width="1205" height="287" alt="image" src="https://github.com/user-attachments/assets/128d1ff3-b6f2-43a8-8469-e3082f044905" />


这里上传hex，可能会不允许上传，因为secure_file_priv设置的为null。就是禁止写入，所以需要设置为secure_file_priv=

![image-20250305220938751](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621081.png)

导出hex后，在新建一个表，导入上面导出的txt文件内容到表里面作为一个c的变量。也就是说此时c变量的值是udf.dll文件的hex值：

![image-20250305221230514](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621082.png)

然后在将对应的c值导到对应路径文件下，这里导出的对应路径文件需要用语法查。

然后查出来的路径如果没有对应文件就新建一个，路径保持一致、mysql索引目录

![image-20250305221904096](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621083.png)

下来就是利用导入的dll文件了。

1、4、创建一个函数(cmdshell)，用来执行udf.dll文件	5、利用自己创建的函数执行cmd命令

![image-20250305222420393](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621084.png)

![image-20250305222720534](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621085.png)



[MYSQL数据库提权的几种方法——提权教程-CSDN博客](https://blog.csdn.net/weixin_40412037/article/details/112541157?ops_request_misc=%7B%22request%5Fid%22%3A%2204790aa6f51eeaec1d4d4ca72e5fe0e8%22%2C%22scm%22%3A%2220140713.130102334..%22%7D&request_id=04790aa6f51eeaec1d4d4ca72e5fe0e8&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~baidu_landing_v2~default-1-112541157-null-null.142^v101^pc_search_result_base9&utm_term=mysql提权的几种方式&spm=1018.2226.3001.4187)

mof提权：mof也是windows系统的一个文件nullevt.mof、用mysql的root权限了以后，然后使用root权限去执行我们上传的mof。隔了一定时间以后这个mof就会被执行，这个mof当中有一段是vbs脚本，这个vbs大多数的是cmd的添加管理员用户的命令。

主要：用sql语句将系统当中默认的nullevt.mof给替换掉，让系统执行我们这个恶意的mof文件，来添加admin账户。

![image-20250305224632138](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621086.png)

 启动项重启提权：

导出自定义bat或vbs到启动目录配合重启执行

自己写一个.bat文件里面是你的恶意命令、通过文件上传上传adduser.bat文件到网站根目录、在通过sql命令写入到启动项中、bat在对方重启后就会自启动执行恶意命令。

![image-20250305225137502](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621087.png)

# sqlmap  

演示	sqlmap扫目标时候会自动创建一个目录用来保存你的注入结果。

使用默认字典猜库，mysql5.0后面会有information表，不用爆破。access数据库就是需要用字典进行爆破。

![image-20250313145829594](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621088.png)

扫到这种就是可能有sql注入点的：

![image-20250313155729213](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621089.png)

 高权限。

[1. sqlmap超详细笔记+思维导图 - bmjoker - 博客园 (cnblogs.com)](https://www.cnblogs.com/bmjoker/p/9326258.html)

--is-dba      #是否是数据库管理员 

 post注入  ：  --data + 参数

![image-20250313213914551](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621090.png)

### 数据包-r

 数据包注入，整个数据包保存位txt文件放到sqlmap目录下在txt文件中的注入点加   *     直接  -r  + 目标数据包文件。

一般建议使用数据包进行注入，因为sqlmap注入时候，会用自己的请求头注入，但是有的数据包会识别，这时候就可能因为请求不同导致没有注入。所以用目标自身的数据包就成功几率大。

![image-20250313214707122](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621091.png)

然后保存到sqlmap目录下：

![image-20250313215742518](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621092.png)

当注入点为json数据注入不了，所以最好还是将目标的整个数据包拿出来进行注入。

### tamper

tamper	base64编码注入

sqlmap自带tamper脚本目录，里面有py文件，针对一些加密编码，绕过一些过滤这些。  只需要后面加上--tamper= 对应脚本名称，即可。

![image-20250313225437231](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621093.png)

 自己编写tamper脚本，针对一些过滤。

这里是过滤了一些关键字过滤。 主要是用到py的replace函数，设计绕过，就是处理替换字符串。

![image-20250313225911400](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621094.png)

 -v参数  提升注入等级、就会注入http头，cookie、注入的参数变多了。然后自身也会用一些绕过姿势尝试。

![image-20250313230206789](https://cdn.jsdelivr.net/gh/maybeyjb/blue-team/img/202506161621095.png)

  加代理，配合bp

