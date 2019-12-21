## python-faraday Package Description

Faraday introduces a new concept – IPE (Integrated Penetration-Test Environment) a multiuser Penetration test IDE. Designed for distribution, indexation and analysis of the data generated during a security audit.

The main purpose of Faraday is to re-use the available tools in the community to take advantage of them in a multiuser way.

Designed for simplicity, users should notice no difference between their own terminal application and the one included in Faraday. Developed with a specialized set of functionalities that help users improve their own work. Do you remember yourself programming without an IDE? Well, Faraday does the same as an IDE does for you when programming, but from the perspective of a penetration test.

Source: https://github.com/infobyte/faraday
[Faraday Homepage](https://www.faradaysec.com/) | [Kali python-faraday Repo](https://gitlab.com/kalilinux/packages/python-faraday.git;a=summary) | [Kali python-faraday Package](http://pkg.kali.org/pkg/commix)

- Author: Infobyte LLC
- License: GPLv3

### Tools included in the python-faraday package

##### python-faraday – Collaborative Penetration Test IDE

```
root@kali:~# python-faraday -h
usage: faraday.py [-h] [-n HOST] [-px PORT_XMLRPC] [-pr PORT_REST] [-d]
         [--profile] [--profile-output PROFILE_OUTPUT]
         [--profile-depth PROFILE_DEPTH] [--disable-excepthook]
         [--dev-mode] [--ignore-deps] [--update] [--cert CERT_PATH]
         [--gui GUI] [--cli] [-w WORKSPACE] [-r FILENAME]

Faraday's launcher parser.

optional arguments:
 -h, --help       show this help message and exit
 -d, --debug      Enables debug mode. Default = disabled
 --disable-excepthook  Disable the application exception hook that allows to
            send error reports to developers.
 --dev-mode       Enable dev mode. This will use the user config and
            plugin folder.
 --ignore-deps     Ignore python dependencies resolution.
 --update        Update Faraday IDE.
 --cert CERT_PATH    Path to the valid CouchDB certificate
 --gui GUI       Select interface to start faraday. Supported values
            are gtk and 'no' (no GUI at all). Defaults to GTK
 --cli         Set this flag to avoid gui and use faraday as a cli.
 -w WORKSPACE, --workspace WORKSPACE
            Workspace to be opened
 -r FILENAME, --report FILENAME
            Report to be parsed by the cli

connection:
 -n HOST, --hostname HOST
            The hostname where both server APIs will listen
            (XMLRPC and RESTful). Default = localhost
 -px PORT_XMLRPC, --port-xmlrpc PORT_XMLRPC
            Sets the port where the api XMLRPCServer will listen.
            Default = 9876
 -pr PORT_REST, --port-rest PORT_REST
            Sets the port where the api RESTful server will
            listen. Default = 9977

profiling:
 --profile       Enables application profiling. When this option is
            used --profile-output and --profile-depth can also be
            used. Default = disabled
 --profile-output PROFILE_OUTPUT
            Sets the profile output filename. If no value is
            provided, standard output will be used
 --profile-depth PROFILE_DEPTH
            Sets the profile number of entries (depth). Default =
            500
```

### Faraday Usage Examples

Faraday is a GUI application that consists of a ZSH terminal and a sidebar with details about your workspaces and hosts.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/faraday-main.png)](http://tools.kali.org/wp-content/uploads/2017/03/faraday-main.png)

When Faraday supports the command you are running, it will automatically detect it and import the results. In the example below, the original [nmap](http://tools.kali.org/information-gathering/nmap) command that was entered was ***nmap -A 192.168.0.7\***, which Faraday converted on the fly.

```
>>> WELCOME TO FARADAY
[+] Current Workspace: dev1
[+] API: OK
[faraday](dev1) kali#  nmap -oX /root/.faraday/data/devel1_Nmap_output-3.46164772371.xml -A 192.168.0.7 2>&1 | tee -a tmp.tu0ldZUG2JgzuHvLOjBYEzBx3Bu7O

Starting Nmap 7.40 ( https://nmap.org ) at 2017-03-07 13:46 MST
Nmap scan report for pi-hole (192.168.0.7)
Host is up (0.0011s latency).
Not shown: 995 closed ports
PORT   STATE SERVICE   VERSION
22/tcp  open  ssh     OpenSSH 6.7p1 Raspbian 5+deb8u3 (protocol 2.0)
| ssh-hostkey:
|  1024 f7:5d:7c:e2:c5:46:32:19:08:e9:4b:79:5e:80:1c:83 (DSA)
|  2048 3c:f9:1d:ce:03:0f:2e:d2:17:05:77:af:81:54:32:fc (RSA)
|_  256 ea:20:d1:e0:e1:89:2c:65:9e:0d:d0:d0:e9:8b:9b:28 (ECDSA)
53/tcp  open  domain   dnsmasq 2.72
| dns-nsid:
|_  bind.version: dnsmasq-2.72
80/tcp  open  http    lighttpd 1.4.35
|_http-server-header: lighttpd/1.4.35
|_http-title: Welcome page
110/tcp open  tcpwrapped
143/tcp open  tcpwrapped
Device type: general purpose
Running: Linux 2.4.X|3.X
OS CPE: cpe:/o:linux:linux_kernel:2.4.37 cpe:/o:linux:linux_kernel:3.2
OS details: DD-WRT v24-sp2 (Linux 2.4.37), Linux 3.2
Network Distance: 2 hops
Service Info: OS: Linux; CPE: cpe:/o:linux:linux_kernel

TRACEROUTE (using port 80/tcp)
HOP RTT   ADDRESS
1  0.27 ms 172.16.206.2
2  0.21 ms pi-hole (192.168.0.7)

OS and Service detection performed. Please report any incorrect results at https://nmap.org/submit/ .
Nmap done: 1 IP address (1 host up) scanned in 18.41 seconds
[faraday](devel1) kali#
```

Once the nmap scan is finished, double-clicking on the host under the ***Hosts\*** tab will bring up details about the host, its services, and any vulnerabilities that were detected.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/faraday-host-details.png)](http://tools.kali.org/wp-content/uploads/2017/03/faraday-host-details.png)

The excellent [dirb](http://tools.kali.org/web-applications/dirb) utility is also supported by Faraday by default:

```
[faraday](devel1) kali#  dirb http://192.168.0.23/commix-testbed -w 2>&1 | tee -a tmp.qNejUxvvrPpbGPVEfwf8OZOuM1F1E

\-----------------
DIRB v2.22   
By The Dark Raver
\-----------------

START_TIME: Tue Mar  7 13:58:52 2017
URL_BASE: http://192.168.0.23/commix-testbed/
WORDLIST_FILES: /usr/share/dirb/wordlists/common.txt
OPTION: Not Stoping on warning messages

\-----------------

GENERATED WORDS: 4612                                

---- Scanning URL: http://192.168.0.23/commix-testbed/ ----
                                                                             ==> DIRECTORY: http://192.168.0.23/commix-testbed/css/                                                            
==> DIRECTORY: http://192.168.0.23/commix-testbed/fonts/                                                           
==> DIRECTORY: http://192.168.0.23/commix-testbed/img/                                                            
\+ http://192.168.0.23/commix-testbed/index.php (CODE:200|SIZE:14346)                                                     
==> DIRECTORY: http://192.168.0.23/commix-testbed/js/                                                             
==> DIRECTORY: http://192.168.0.23/commix-testbed/readme/                                                           
                                                                                       
---- Entering directory: http://192.168.0.23/commix-testbed/css/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.             
  (Use mode '-w' if you want to scan it anyway)
                                                                                       
---- Entering directory: http://192.168.0.23/commix-testbed/fonts/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.             
  (Use mode '-w' if you want to scan it anyway)
                                                                                       
---- Entering directory: http://192.168.0.23/commix-testbed/img/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.             
  (Use mode '-w' if you want to scan it anyway)
                                                                                       
---- Entering directory: http://192.168.0.23/commix-testbed/js/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.             
  (Use mode '-w' if you want to scan it anyway)
                                                                                       
---- Entering directory: http://192.168.0.23/commix-testbed/readme/ ----
(!) WARNING: Directory IS LISTABLE. No need to scan it.             
  (Use mode '-w' if you want to scan it anyway)
                                                                                       
\-----------------
END_TIME: Tue Mar  7 14:04:24 2017
DOWNLOADED: 27672 - FOUND: 1
```

When the scan is finished, double-clicking on the host will bring up its details, including the directories that dirb detected.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/faraday-vuln-details.png)](http://tools.kali.org/wp-content/uploads/2017/03/faraday-vuln-details.png)

Take a look in the ***/usr/share/python-faraday/plugins/repo*** directory to see what other applications Faraday supports.

```
root@kali:/usr/share/python-faraday/plugins/repo# ls
acunetix  dnsrecon    listurl    netsparker   retina      wapiti
amap    dnswalk    maltego    nexpose     reverseraider  wcscan
appscan  fierce     masscan    nexpose-full  sentinel     webfuzzer
arachni  fruitywifi   medusa     nikto      skipfish     whois
arp-scan  ftp      metagoofil   nmap      sqlmap      wpscan
beef    goohost    metasploit   openvas     sshdefaultscan  x1
burp    hping3     metasploiton  pasteanalyzer  sslcheck     zap
dig    hydra     ndiff     peepingtom   telnet
dirb    impact     nessus     ping      theharvester
dnsenum  __init__.py  netcat     propecia    traceroute
dnsmap   __init__.pyc  netdiscover  qualysguard   w3af
```

Faraday also includes a full-featured web interface that provides you, your team, and any other interested parties with an immense amount of information.

[![img](http://tools.kali.org/wp-content/uploads/2017/03/faraday-web-dash.png)](http://tools.kali.org/wp-content/uploads/2017/03/faraday-web-dash.png) 