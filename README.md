# awd_worm_phpwebshell_framework
awd-php-webshell awd比赛落地RPG，别人还在慢慢捡武器，目的是快速批量持续控制靶机。等我一场比赛完会公开源码，持续改进完善中。


假设shell.php已经上传到目录，
上传目录为upload，ip为192.168.1.1 

php服务端部分： 

1.访问http://192.168.1.1/upload/shell.php  正常不带参数访问是返回状态码500

2.带参数下划线访问，会自动感染全站php文件，所有php可以当shell连接 eg:http://192.168.1.1/upload/shell.php?_

3.如上带下划线参数访问后，右键查看页面源代码可以看到所有被感染的php地址。

4.可以使用python把所有url爬下来，爬取规则：checks_arr = html.find_all(attrs={'id': 'check_url'})

python客户端部分：

1.在文件上方cmd=‘’参数输入想要执行的命令

2.webshell_url=‘’填你上传的地址或者感染的php地址

前端部分：

1.浏览者会自动循环跳转带参数“_”原生ajax请求进行传播

复活框架：

比赛中getshell方法很多，可能有rce，可能有上传、可能有包含。

只需要在复活框架中的getshell模块函数返回一个蠕虫马的url即可

重置环境也没用，等工作人员走过来告诉你已经重置了，就已经getshell很久了。

删了一个蠕虫马可以互相复活。
