## 在Ubuntu系统下的LNMP搭建教程   
#####步骤
1. [简述LNMP](#1)
2. [安装nginx](#2)
3. []
4. 

<p id = "1"><b>简述LNMP</b></p>
LNMP的通用含义是：Linux系统 + Nginx + MySQL + PHP 这种网站服务器架构。  
1. Linux是目前最流行的操作系统，代表版本有Ubuntu、Debian、Centos、Fedora等；
2. Nginx是一款高性能的HTTP和反向代理服务器，也是一款IMAP/POP3/SMTP代理服务器；
3. MySQL是一种小型关系型数据库管理系统；
4. PHP是一种在服务器端执行的嵌入HTML文档的脚本语言。

<p id = "2"><b>安装nginx</b></p>
1. 先更新安装包   
`apt-get update`
2. 安装nginx   
`apt-get install nginx`
3. 查看是否安装成功   
在浏览器中输入服务器IP地址查看欢迎页面。
