## 无梦生教你翻墙：如何在服务器端搭建shadowsocks教程  
#### 目录&步骤  
1. [更新安装包](#1)
2. [安装Python环境](#2)
3. [安装shadowsocks](#3)
4. [修改配置文件](#4)
5. [运行shadowsocks](#5)
6. [浏览器端使用SwitchyOmega扩展插件](#6)  
7. [shadowsocks客户端下载](#7)

---
<p id = "1"><b>更新安装包</b></p>  
`apt-get update`  

---
<p id = "2"><b>安装Python环境</b></p>   
`apt-get install python-pip`  

---
<p id = "3"><b>安装shadowsocks</b></p>   
`pip install shadowsocks`  

---
<p id = "4"><b>修改配置文件</b></p>  
1. 打开配置文件  
`vi /etc/shadowsocks.json`  
1. 编辑  
`{`  
    `"server":"你的服务器IP地址",`  
    `"server_port":8380（自定义端口）,`  
    `"local_address":"127.0.0.1",`  
    `"local_port":1080,`  
    `"password":"你的密码",`  
    `"timeout":600,`  
    `"method":"aes-256-cfb",`  
    `"fast_open":false,`  
    `"workers":1`  
    `}`  
    保存并退出  
    
    ---
    <p id = "5"><b>运行</b></p>  
    1. 前台运行  
    `ssserver -c /etc/shadowsocks.json`  
    2. 后台运行  
    `ssserver -c /etc/shadowsocks.json -d start`   
    3. 停止运行
    `ssserver -c /etc/shadowsocks.json -d stop`  
    4. 重启  
    `ssserver -c /etc/shadowsocks.json -d restart`  
    
    ---
    <p id = "6"><b>浏览器端使用SwitchyOmega扩展插件</b></p>   
    在浏览器端添加扩展插件SwitchOmega并配置相关信息  
    [点我下载SwitchyOmega](#https://github.com/FelisCatus/SwitchyOmega/releases)  
    
    ---
    <p id = "7"><b>shadowsocks客户端下载</b></p>   
    [点我下载shadowsocks客户端](#http://pan.baidu.com/s/1c09b3ZM)  
    密码: yd8j  
    ---
    完成
