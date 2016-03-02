## Ubuntu之使用speedtest-cli测试VPS速度
#### 目录&步骤
1. [speedtest-cli概述](#1)  
2. [安装speedtest-cli](#2)  
3. [使用speedtest-cli测试网速](#3)  

---
<p id = "1"><b>1. speedtest-cli概述</b></p>
在可用于测试宽带速度的网站中，Speedtest.net也许是使用最广泛的，其工作原理并不复杂：它在你浏览器中加载JavaScript代码并自动检测离你
最近的Speedtest.net服务器，然后向服务器发送HTTP GET and POST请求来测试上行/下行速度。  
Speedtest.net提供了一个命令行版本——speedtest-cli，来测试宽带连接速度。  

---
<p id = "2"><b>2. 安装speedtest-cli</b></p>
speedtest-cli是一个用Python编写的轻量级Linux命令行工具。  
命令如下:    
`wget https://raw.github.com/sivel/speedtest-cli/master/speedtest_cli.py`  
`chmod a+rx speedtest_cli.py`  
`sudo mv speedtest_cli.py /usr/local/bin/speedtest-cli`  
`sudo chown root:root /usr/local/bin/speedtest-cli`  

---
<p id = "3"><b>3. 使用speedtest-cli测试网速</b></p>
`speedtest-cli`  
输入这个命令后，它会自动发现离你最近的Speedtest.net服务器，然后打印出测试网络上/下行速率。  
`speedtest-cli --share`  
使用这个命令会把你的测试结果上传到Speedtest.net服务器并以图形的形式分享给其他人。  
`speedtest-cli --list`  
使用这个命令，它会打印出所有的Speedtest.net服务器（按照离你的地理距离由近及远排序）。  

---
### END
