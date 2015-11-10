## 在Ubuntu系统下的ftp服务器搭建教程（vsftpd的安装与配置）
#### 目录&步骤
1. [更新安装包](#1)
2. [安装vsftpd](#2)
3. [新建工作目录和用户](#3)
4. [配置文件](#4)
5. [新建用户文件](#5)

---
<p id = "1"><b>1. 更新安装包</b></p>    
`apt-get update`  

---
<p id = "2"><b>2. 安装vsftpd</b></p>  
1. 安装vsftpd  
`apt-get install vsftpd`  
2. 查看vsftpd是否安装成功  
`service vsftps restart`    

---
<p id = "3"><b>3. 新建工作目录</b></p>  
1. 建立工作目录  
`mkdir /home/ftp` 
2. 添加用户  
`usradd -d /home/ftp -s /bin/bash myftp（用户名）`  
3. 修改密码  
`passwd myftp`  

---
<p id = "4"><b>4. 配置文件</b></p>  
1. 打开配置文件vsftpd.conf  
`vi /etc/vsftpd.conf`  
2. 在文件最后添加代码  
`userlist_deny=NO`  
`userlist_enable=YES`  
`userlist_file=/etc/allowed_users`  
3. 将以下代码去除注释（去除#）  
`#seccomp_sandbox=NO`  
`#local_enable=YES`  

---
<p id = 5><b>5. 新建用户文件</b></p>  
1. 新建/etc/allowed_users文件  
`vi /etc/allowed_users`  
`添加myftp（用户名）后退出`  
2. 查看禁止访问的用户名单  
`vi /etc/ftpusers`   
`这个文件记录的是禁止访问ftp服务器的用户list，所以必须保证文件中没有myftp用户名`  

---
**使用cuteftp连接ftp服务器并测试是否搭建成功**  
#### 完成
