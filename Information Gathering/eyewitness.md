## eyewitness软件包描述

EyeWitness主要用于对网站，远程桌面和open VNC服务器进行快照，也可以提供一部分服务器头文件，或是识别一些默认的证书。

源地址: https://github.com/ChrisTruncer/EyeWitness
[EyeWitness主页](https://github.com/ChrisTruncer/EyeWitness) | [Kali eyewitness仓库](https://gitlab.com/kalilinux/packages/eyewitness.git)

- 作者: Christopher Truncer
- 证书: GPL-3+

### eyewitness软件包中包含的工具

##### eyewitness – 网络应用快速分类工具

```
root@kali:~# eyewitness -h

################################################################################
#                  EyeWitness                  #
################################################################################

用法: EyeWitness.py [--web] [--headless] [--rdp] [--vnc] [--all-protocols]
           [-f 文件名] [-x 文件名.xml] [--single 单个URL]
           [--createtargets 目标文件.txt] [--no-dns]
           [--timeout 超时秒数] [--jitter # 秒]
           [--threads # 线程] [-d 目录名]
           [--results 每页的主机数] [--no-prompt]
           [--user-agent 用户代理] [--cycle 用户代理类型]
           [--difference 差分界限]
           [--proxy-ip 127.0.0.1] [--proxy-port 8080]
           [--show-selenium] [--resolve]
           [--add-http-ports 添加的HTTP端口]
           [--add-https-ports 添加的HTTPS端口] [--prepend-https]
           [--vhost-name 主机名] [--active-scan] [--resume ew.db]

EyeWitness是用于对多个URL进行快照的工具。

协议:
 --web         使用Selenium的HTTP快照
 --headless    使用PhantomJS Headless的HTTP快照
 --rdp         对RDP服务进行快照
 --vnc         对无认证VNC服务进行快照
 --all-protocols    对所有支持的协议进行快照，使用Selenium处理HTTP

输入参数:
 -f 文件名      包含需要抓取的URL列表的文件，列表内用行分隔开
 -x 文件名.xml    Nmap生成的XML或.Nessus文件
 --single 单个URL  需要捕获的单个URL/Host
 --createtargets 目标文件.txt
            分析.nessus或Nmap生成的XML文件，输出以行分割的URL列表
 --no-dns        在访问网站时跳过DNS解析

时间参数:
 --timeout 超时秒数   请求网页时等待的最长时间（单位：秒）（默认：7）
 --jitter # 秒
            随机访问URL并在访问之间进行一定的延迟
 --threads # 线程
            使用文件输入时运行的线程数

报告输出参数:
 -d 路径名   报告输出的路径
 --results 每页的主机数
            报告中每页的主机数
 --no-prompt      不要提示打开报告

WEB参数:
 --user-agent 用户代理
            为所有请求指定用户代理
 --cycle 用户代理类型
            指定用户代理类型(Browser, Mobile, Crawler, Scanner,Misc, All)
 --difference 差分界限
            指定差分界限，来规定UA请求是否足够接近（默认：50）
 --proxy-ip 127.0.0.1  指定使用的网络代理
 --proxy-port 8080   指定使用的网络代理端口
 --show-selenium    输出selenium的回显
 --resolve       解析目标IP/Hostname
 --add-http-ports 添加的HTTP端口
            额外添加的HTTP端口，用逗号隔开(e.g. '8018,8028')
 --add-https-ports 添加的HTTPS端口
            额外添加的HTTPS端口，用逗号隔开(e.g. '8018,8028')
 --prepend-https    为没有http:\\或https:\\的URL预置标头
 --vhost-name 主机名
            主机头文件里使用的主机名(仅限无标头模式 + 单URL模式)
 --active-scan     尝试主动登入来识别登录页面或证书

恢复参数:
 --resume ew.db     指定db文件路径用以恢复上次的操作
```

### eyewitness用法示例

尝试在无标头模式下对所提供文件里的每一个网站进行快照。

```
root@kali:~# cat urls.txt
https://www.kali.org
http://docs.kali.org
https://tools.kali.org/
https://www.exploit-db.com
https://www.offensive-security.com

root@kali:~# eyewitness -f /root/urls.txt -d screens --headless

################################################################################
#                  EyeWitness                  #
################################################################################

Starting Web Requests (5 Hosts)
Attempting to screenshot https://www.kali.org
Attempting to screenshot http://docs.kali.org
Attempting to screenshot https://tools.kali.org/
Attempting to screenshot https://www.exploit-db.com
Attempting to screenshot https://www.offensive-security.com
Finished in 14.1417660713 seconds

[*] Done! Report written in the /usr/share/eyewitness/screens folder!
Would you like to open the report now? [Y/n] Y
```