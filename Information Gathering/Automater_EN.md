## Automater Package Description

Automater is a URL/Domain, IP Address, and Md5 Hash OSINT tool aimed at making the analysis process easier for intrusion Analysts. Given a target (URL, IP, or HASH) or a file full of targets Automater will return relevant results from sources like the following: IPvoid.com, Robtex.com, Fortiguard.com, unshorten.me, Urlvoid.com, Labs.alienvault.com, ThreatExpert, VxVault, and VirusTotal.

Source: http://www.tekdefense.com/automater/

[Automater Homepage](http://www.tekdefense.com/automater/) | [Kali Automater Repo](https://gitlab.com/kalilinux/packages/automater.git;a=summary)

- Author: TekDefense.com
- License: Other

### Tools included in the automater package

##### automater – A IP and URL analysis tool

```
root@kali:~# automater -h
usage: Automater.py [-h] [-o OUTPUT] [-w WEB] [-c CSV] [-d DELAY] [-s SOURCE]
[--p] [--proxy PROXY] [-a USERAGENT]
target

IP, URL, and Hash Passive Analysis tool

positional arguments:
target List one IP Address (CIDR or dash notation accepted),
URL or Hash to query or pass the filename of a file
containing IP Address info, URL or Hash to query each
separated by a newline.

optional arguments:
-h, --help show this help message and exit
-o OUTPUT, --output OUTPUT
This option will output the results to a file.
-w WEB, --web WEB This option will output the results to an HTML file.
-c CSV, --csv CSV This option will output the results to a CSV file.
-d DELAY, --delay DELAY
This will change the delay to the inputted seconds.
Default is 2.
-s SOURCE, --source SOURCE
This option will only run the target against a
specific source engine to pull associated domains.
Options are defined in the name attribute of the site
element in the XML configuration file
--p, --post This option tells the program to post information to
sites that allow posting. By default the program will
NOT post to sites that require a post.
--proxy PROXY This option will set a proxy to use (eg.
proxy.example.com:8080)
-a USERAGENT, --useragent USERAGENT
This option allows the user to set the user-agent seen
by web servers being utilized. By default, the user-
agent is set to Automater/version
```

### automater Usage Example

Use ***robtex*** as the source ***(-s)*** to scan for information on IP address ***50.116.53.73***:

```
root@kali:~# automater -s robtex 50.116.53.73
[*] Checking http://api.tekdefense.com/robtex/rob.php?q=50.116.53.73

____________________ Results found for: 50.116.53.73 ____________________
[+] A records from Robtex.com: www.kali.org
```