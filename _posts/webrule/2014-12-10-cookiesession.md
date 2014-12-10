---
layout: post
title: "cookie和session"
category: "webrule"
tags: ["webrule"]
tagline: "个人笔记"
---
{% include JB/setup %}
## Cookie，浏览器的客户通行证
- 由浏览器管理，具有不可跨域性
- 浏览器只提交name和value属性
- 如果未设置有效期，则存储在内存，随着窗口关闭而删除
- 如果设置有效期，则存储在硬盘
- 不同窗口用不同cookie，（链接或脚本打开的窗口属于父子窗口，用同一个cookie）
- cookie只能覆盖不能主动修改和删除
- 跨子域：需要设置域Domain(".xxx.com")，a.xxx.com和b.xxx.com的cookie才能共用
- 路径+域=cookie作用范围
- 验证方法：
    - 1、将用户名和加密密码放到cookie，与数据库做对比来做验证
    - 2、将用户名和加密算法(用户名和密码)放到cookie，通过判断加密规则来做验证

## Session，服务端的客户档案表
- 每次访问都更新有效期
- 长久未访问则删除
- session客户端的实现方式
   - cookie：通过cookie携带sessionid(会员卡号，用来对应客户)来验证
   - url重写(cookie被禁用的情况）：附加方式(http://.../xxx;sid=)，参数方式(http://.../xxx?sid=)
   - 表单隐藏字段（比较少用）

## php操作session
- session\_start()
   - 如果cookie中的name=value有sessionName=sessionid，如果文件sess\_{sessionid}不存在，则创建sess\_{sessionid}文件
   - 如果cookie中的name=value没有sessionName=sessionid(第一次访问), 则php(创建并发送cookie,创建session文件，两者先后顺序？)
- 如何销毁一个Session？
   - 第一步，销毁session存在服务器端的数据: session\_destroy();
   - 第二步，删除客户端的session cookie: setcookie(session\_name(),'',time()-3600);，需要关闭浏览器(cookie在浏览器进程中)。
   - 第三步，销毁全局变量$\_SESSION :$\_SESSION=array();

## session跨域名/SSO
- 要满足
   - 1、一个是各个服务器对同一个客户端产生的SESSION ID 必须相同，并且可通过同一个 COOKIE 进行传递，也就是说各个服务器必须可以读取同一个名为 PHPSESSID 的COOKIE；
   - 2、另一个是 SESSION 数据的存储方式/位置必须保证各个服务器都能够访问到。
- 如何产生相同sessionID？
   - 跨子域: 子域要设置相同domain，session\_set\_cookie\_params(1800 , '/', '.test.com');
   - 跨域：

        - １、在Ａ系统下成功登录后，利用JS动态创建一个隐藏的iframe，通过iframe的src属性将Ａ域下的cookie值作为get参数重定向到Ｂ系统下b.jsp页面上；

                var _frm = document.createElement("iframe");
                _frm.style.display="none";
                _frm.src = "http://www.222.com/setcookie.php?mycookie=xxxxx";//此处xxx最好编码
                document.body.appendChild(_frm);

        - 2、在Ｂ系统的setcookie.php页面中来获取Ａ系统中所传过来的cookie值，并将所获取到值写入用户的cookie中，当然域是自己的了，这样就简单的实现了cookie跨域的访问；不过这其中有个问题需要注意，就是在IE浏览器下这样操作不能成功，需要在setocokie.php页面中设置P3P HTTP Header就可以解决了（具体詳細信息可以参考:http://www.w3.org/P3P/)，P3P设置代码为：

                header('P3P: CP="CURa ADMa DEVa PSAo PSDo OUR BUS UNI PUR INT DEM STA PRE COM NAV OTC NOI DSP COR"');//ecshop这么设置的

- 如何访问同一个session数据？
    - 数据库存储
    - NFS方式
