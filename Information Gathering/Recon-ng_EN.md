## Recon-ng Package Description

Recon-ng is a full-featured Web Reconnaissance framework written in Python. Complete with independent modules, database interaction, built in convenience functions, interactive help, and command completion, Recon-ng provides a powerful environment in which open source web-based reconnaissance can be conducted quickly and thoroughly.

Recon-ng has a look and feel similar to the Metasploit Framework, reducing the learning curve for leveraging the framework. However, it is quite different. Recon-ng is not intended to compete with existing frameworks, as it is designed exclusively for web-based open source reconnaissance. If you want to exploit, use the Metasploit Framework. If you want to Social Engineer, us the Social Engineer Toolkit. If you want to conduct reconnaissance, use Recon-ng! See the Usage Guide for more information.

Recon-ng is a completely modular framework and makes it easy for even the newest of Python developers to contribute. Each module is a subclass of the “module” class. The “module” class is a customized “cmd” interpreter equipped with built-in functionality that provides simple interfaces to common tasks such as standardizing output, interacting with the database, making web requests, and managing API keys. Therefore, all the hard work has been done. Building modules is simple and takes little more than a few minutes. See the Development Guide for more information.

Source: https://bitbucket.org/LaNMaSteR53/recon-ng
[Recon-ng Homepage](http://recon-ng.com/) | [Kali Recon-ng Repo](https://gitlab.com/kalilinux/packages/recon-ng.git;a=summary)

- Author: Tim Tomes
- License: GPLv3

### Tools included in the recon-ng package

##### recon-ng – Web Reconnaissance framework written in Python

```
root@kali:~# recon-ng --help
usage: recon-ng [-h] [-v] [-w workspace] [-r filename] [--no-check]
        [--no-analytics]

recon-ng - Tim Tomes (@LaNMaSteR53) tjt1980[at]gmail.com

optional arguments:
 -h, --help    show this help message and exit
 -v, --version  show program's version number and exit
 -w workspace   load/create a workspace
 -r filename   load commands from a resource file
 --no-check    disable version check
 --no-analytics  disable analytics reporting
```

### recon-ng Usage Example

Search for results on xssed.com ***(use recon/domains-vulnerabilities/xssed)*** for the target domain ***(set SOURCE cisco.com)***:

```
root@kali:~# recon-ng
                                            
  _/_/_/   _/_/_/_/   _/_/_/   _/_/_/   _/    _/       _/    _/   _/_/_/
  _/   _/  _/     _/     _/    _/  _/_/   _/       _/_/   _/  _/    
 _/_/_/   _/_/_/   _/     _/    _/  _/  _/  _/  _/_/_/_/  _/  _/  _/  _/  _/_/_/
 _/   _/  _/     _/     _/    _/  _/   _/_/       _/   _/_/  _/    _/
_/   _/  _/_/_/_/   _/_/_/   _/_/_/   _/    _/       _/    _/   _/_/_/   
                                            

​                     /\
​                     / \\ /\
​    Sponsored by...      /\  /\/  \\V  \/\
​                 / \\/ // \\\\\ \\ \/\
​                // // BLACK HILLS \/ \\
​                www.blackhillsinfosec.com

​           [recon-ng v4.9.4, Tim Tomes (@LaNMaSteR53)]            

[76] Recon modules
[8]  Reporting modules
[2]  Import modules
[2]  Exploitation modules
[2]  Discovery modules

[recon-ng][default] > use recon/domains-vulnerabilities/xssed
[recon-ng][default][xssed] > set SOURCE cisco.com
SOURCE => cisco.com
[recon-ng][default][xssed] > run

\---------
CISCO.COM
\---------
[*] Category: Redirect
[*] Example: http://www.cisco.com/survey/exit.html?http://xssed.com/
[*] Host: www.cisco.com
[*] Publish_Date: 2012-02-16 00:00:00
[*] Reference: http://xssed.com/mirror/76478/
[*] Status: unfixed
[*] --------------------------------------------------
[*] Category: XSS
[*] Example: http://developer.cisco.com/web/webdialer/wikidocs?p_p_id=1_WAR_wikinavigationportlet_INSTANCE_veD7&p<br>_p_lifecycle=0&p_p_state=normal&p_p_mode=view&p_p_col_id=column-1&p_p_col_count=1&p_r_p_185834411_no<br>deId=803209&p_r_p_185834411_title=%22%3E%3Ch1%3ECross-Site%20Scripting%20@matiaslonigro%3C/h1%3E%3Cs<br>cript%3Ealert%28/xss/%29%3C/script%3E
[*] Host: developer.cisco.com
[*] Publish_Date: 2012-02-13 00:00:00
[*] Reference: http://xssed.com/mirror/76294/
[*] Status: unfixed
...
```