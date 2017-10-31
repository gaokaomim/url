# url
题目:从URL输入到页面展现到底发生什么

前言<br/>
打开浏览器从输入网址到网页呈现在大家面前，背后到底发生了什么？经历怎么样的一个过程？这是本文要探讨的问题！
### 一、URL到底是啥
URL（Uniform Resource Locator），统一资源定位符,用于定位互联网上资源，俗称网址。
比如 http://www.w3school.com.cn/html/index.asp,遵守以下的语法规则:scheme://host.domain:port/path/filename
解释:
scheme - 定义因特网服务的类型。常见的协议有http、https、ftp、file，其中最常见的类型是 http，而https则是进行加密的网络传输。
host - 定义域主机（http 的默认主机是 www）
domain - 定义因特网域名，比如 w3school.com.cn
:port - 定义主机上的端口号（http 的默认端口号是 80）
path - 定义服务器上的路径（如果省略，则文档必须位于网站的根目录中）。
filename - 定义文档/资源的名称
### 二、域名解析(DNS)
  在游览器输入网址后,首先要经过域名解析,因为游览器并不能识别域名,需要通过域名直接找到相应的IP地址,大家这里或许会有个疑问---为啥要设置域名?怎么不一会开始就给个IP地
址?这样可以省去解析麻烦.<br/>
  我们先来了解下什么是IP地址<br/>
  IP地址是指互联网协议地址,是IP Address的缩写.IP地址是IP协议提供的一种统一的地址格式,它为互联网上的每个网络和每一台主机分配一个逻辑地址,以此来屏蔽物理地址的差异<br/>
  IP地址是一个32位的二进制数,比如127.0.0.1为本机IP;如果每个网址都是一串数字,那就不便记忆!<br/>
  域名就相当于IP地址乔装打扮的伪装者,带着一副面具.它的作用就是便于记忆和沟通的一组服务器的地址.但这样有时候会带来一种风险----DNS劫持，就是使域名对应的不再是原本对应的IP，其效果就是对特定的网络不能访问或访问的是假网址，又难于被用户发觉，曾导致巴西最大银行巴西银行近1%客户受到攻击而导致账户被盗.
### 三、域名解析流程
  浏览器缓存：如果在之前对该url指定的主机进行过访问，浏览器会缓存该主机的IP一段时间（该时间浏览器指定），然后通过该IP地址找到对应主机;<br/>
  系统缓存：若浏览器中无该缓存，那么就到系统缓存中进行查询，浏览器会进行系统调用，查询缓存;<br/>
  路由器缓存：如果系统缓存中也没有，那么就到路由器缓存中进行查询;<br/>
  ISP DNS 缓存：如果路由器缓存依旧未命中，那么就到ISP DNS中查询，一般的域名都能在这里查询得到;<br/>
  递归搜索：如果以上都没有查询到，那么就会到顶级域名服务器的根服务器中进行递归查询，只要该域名存在就肯定能找得到; <br/>
  通过域名解析查找到对应的IP地址之后，通过IP地址查找到对应的服务器，浏览器将用户发起的http请求发送给服务器。下一步就到了服务器处理阶段的工作<br/>
### 四、服务器处理响应请求
#### 1.服务器
  服务器是网络环境中的高性能计算机,它侦听网络上的其他计算机(客户机)提交的服务请求,并提供相应的服务,比如网页服务、文件下载服务、邮件服务、视频服务.而客户端主要的功能是游览网页、看视频、听音乐等等,两者截然不同.每台服务器上都会安装处理请求的应用--web server.常见的web server产品有apache、nginx、IIS或Lighttpd等.
  web server 担任管控的角色,对于不同用户发送的请求,会结合配置文件,把不同请求委托给服务器上处理相应请求的程序进行处理（例如CGI脚本，JSP脚本，servlets，ASP脚本，服务器端JavaScript，或者一些其它的服务器端技术等）,然后返回后台程序处理产生的结果作为响应.
![服务器和客户端区别.png](https://github.com/gaokaomim/url/blob/master/img/icon_02.png)


