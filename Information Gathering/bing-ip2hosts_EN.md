## bing-ip2hosts Package Description

Bing.com is a search engine owned by Microsoft formerly known as MSN Search and Live Search. It has a unique feature to search for websites hosted on a specific IP address. Bing-ip2hosts uses this feature to enumerate all hostnames which Bing has indexed for a specific IP address. This technique is considered best practice during the reconnaissance phase of a penetration test in order to discover a larger potential attack surface. Bing-ip2hosts is written in the Bash scripting language for Linux. This uses the mobile interface and no API key is required.

Source: http://www.morningstarsecurity.com/research/bing-ip2hosts
[bing-ip2hosts Homepage](http://www.morningstarsecurity.com/research/bing-ip2hosts/) | [Kali bing-ip2hosts Repo](https://gitlab.com/kalilinux/packages/bing-ip2hosts.git;a=summary)

- Author: Andrew Horton
- License: GPLv3

### Tools included in the bing-ip2hosts package

##### bing-ip2hosts – Enumerate hostnames for an IP using bing.com

```
[/vc_column_text][/vc_column][/vc_row][vc_row][vc_column][vc_column_text]
root@kali:~# bing-ip2hosts
bing-ip2hosts (o.4) by Andrew Horton aka urbanadventurer
Homepage: http://www.morningstarsecurity.com/research/bing-ip2hosts

Useful for web intelligence and attack surface mapping of vhosts during
penetration tests. Find hostnames that share an IP address with your target
which can be a hostname or an IP address. This makes use of Microsoft
Bing.com ability to seach by IP address, e.g. "IP:210.48.71.196".

Usage: /usr/bin/bing-ip2hosts [OPTIONS] &lt;IP|hostname&gt;

OPTIONS are:
-n Turn off the progress indicator animation
-t

<dir>Use this directory instead of /tmp. The directory must exist.
-i Optional CSV output. Outputs the IP and hostname on each line, separated by a comma.
-p Optional http:// prefix output. Useful for right-clicking in the shell.</dir>
```

### bing-ip2hosts Usage Examples

```
[/vc_column_text][/vc_column][/vc_row][vc_row][vc_column][vc_column_text]
root@kali:~# bing-ip2hosts -p microsoft.com
[ 65.55.58.201 | Scraping 1 | Found 0 | / ]
http://microsoft.com
http://research.microsoft.com
http://www.answers.microsoft.com
http://www.microsoft.com
http://www.msdn.microsoft.com
```

```
[/vc_column_text][/vc_column][/vc_row][vc_row][vc_column][vc_column_text]
root@kali:~# bing-ip2hosts -p 173.194.33.80
[ 173.194.33.80 | Scraping 60-69 of 73 | Found 41 | | ]| / ]
http://asia.google.com
http://desktop.google.com
http://ejabat.google.com
http://google.netscape.com
http://partner-client.google.com
http://picasa.google.com
```