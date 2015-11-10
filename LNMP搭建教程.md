## 在Ubuntu系统下的LNMP搭建教程   
####目录&步骤
1. [简述LNMP](#1)
2. [安装nginx](#2)
3. [安装MySQL server](#3)
4. [安装PHP](#4)

---
<p id = "1"><b>简述LNMP</b></p>
* LNMP的通用含义是：Linux系统 + Nginx + MySQL + PHP 这种网站服务器架构。     
* Linux是目前最流行的操作系统，代表版本有Ubuntu、Debian、Centos、Fedora等；   
* Nginx是一款高性能的HTTP和反向代理服务器，也是一款IMAP/POP3/SMTP代理服务器；   
* MySQL是一种小型关系型数据库管理系统；   
* PHP是一种在服务器端执行的嵌入HTML文档的脚本语言。

---
<p id = "2"><b>安装nginx</b></p>
1. 先更新安装包   
`apt-get update`
2. 安装nginx   
`apt-get install nginx`
3. 查看是否安装成功   
在浏览器中输入服务器IP地址查看欢迎页面。  
4. 配置nginx  
`vi /etc/nginx/sites-available/default`   
将一下代码前的#去除（即取消注释一下代码）  
`localtion = /50x.html {`  
      `root /usr/share/nginx/html; ` 
`}`     
`localtion ~ \.php$ { ` 
      `try_files $uri = 404; ` 
      `fastcgi_split_path_info ^(.+\.php)(/.+)$; ` 
      `fastcgi_pass unix:/var/run/php5-fpm.sock; ` 
      `fastcgi_index index.php;`  
      `include fastcgi_params;`  
`}`     
5. 重载nginx配置文件   
`service nginx reload`   
6. 重启nginx   
`service nginx restart` 

---
<p id = "3"><b>安装MySQL server</b></p>
1. 安装MySQL server  
`apt-get install mysql-server`  
2. 设置MySQL root用户密码  
3. 检查MySQL服务器状态  
`service mysql status`  
4. 安装MySQL Client    
`apt-get install mysql-client` 

---
<p id = "4"><b>安装PHP</b></p>  
1. 安装PHP5    
`apt-get install php5-fpm` 
2. 安装以下功能插件    
`apt-get install php5 php5-cgi php5-curl php5-dev php5-gd php5-mysql php5-pspell php5-recode php5-snmp php5-sqlite php5-tidy php5-xmlrpc php5-xsl php5-imagick php5-imap php5-intl php5-mcrypt php5-memcache php5-memcached php5-ming php5-ps php-pear php-apc`  
3. 配置php.ini  
`vi /etc/php5/fpm/php.ini`    
`将 ;cgi.fix_pathinfo=1 去掉注释并改为 cgi.fix_pathinfo=0`    
4. 重载、重启php和nginx  
 `service php5-fpm reload`  
 `service php5-fpm restart`  
 `service nginx reload ` 
 `service nginx restart`  
5. 创建PHP探针文件“info.php”    
`vi /etc/share/nginx/html/infp.php`    
文件代码  
` <?php ` 
   ` phpinfp();`  
`?> `   
6. 测试LNMP是否安装成功  
`在浏览器中输入 http://服务器IP地址/info.php`  
出现版本信息页面，说明安装成功。

---
#####完成


