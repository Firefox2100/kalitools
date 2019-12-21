## dnsmap Package Description

dnsmap was originally released back in 2006 and was inspired by the fictional story “The Thief No One Saw” by Paul Craig, which can be found in the book “Stealing the Network – How to 0wn the Box”.

dnsmap is mainly meant to be used by pentesters during the information gathering/enumeration phase of infrastructure security assessments. During the enumeration stage, the security consultant would typically discover the target company’s IP netblocks, domain names, phone numbers, etc …

Subdomain brute-forcing is another technique that should be used in the enumeration stage, as it’s especially useful when other domain enumeration techniques such as zone transfers don’t work (I rarely see zone transfers being publicly allowed these days by the way).

Source: http://code.google.com/p/dnsmap/
[dnsmap Homepage](http://code.google.com/p/dnsmap/) | [Kali dnsmap Repo](https://gitlab.com/kalilinux/packages/dnsmap.git;a=summary)

- Author: pagvac
- License: GPLv2

### Tools included in the dnsmap package

##### dnsmap – DNS domain name brute forcing tool

```
root@kali:~# dnsmap
dnsmap 0.30 - DNS Network Mapper by pagvac (gnucitizen.org)

usage: dnsmap <target-domain> [options]
options:
-w <wordlist-file>
-r <regular-results-file>
-c <csv-results-file>
-d <delay-millisecs>
-i <ips-to-ignore> (useful if you're obtaining false positives)

e.g.:
dnsmap target-domain.foo
dnsmap target-domain.foo -w yourwordlist.txt -r /tmp/domainbf_results.txt
dnsmap target-fomain.foo -r /tmp/ -d 3000
dnsmap target-fomain.foo -r ./domainbf_results.txt
```

### dnsmap-bulk.sh – DNS domain name brute forcing tool

```
root@kali:~# dnsmap-bulk.sh
usage: dnsmap-bulk.sh <domains-file> [results-path]
e.g.:
dnsmap-bulk.sh domains.txt
dnsmap-bulk.sh domains.txt /tmp/
```

### dnsmap Usage Example

Scan ***example.com*** using a wordlist ***(-w /usr/share/wordlists/dnsmap.txt)***:

```
root@kali:~# dnsmap example.com -w /usr/share/wordlists/dnsmap.txt
dnsmap 0.30 - DNS Network Mapper by pagvac (gnucitizen.org)

[+] searching (sub)domains for example.com using /usr/share/wordlists/dnsmap.txt
[+] using maximum random delay of 10 millisecond(s) between requests
```

### dnsmap-bulk Usage Example

Create a file containing domain names to scan ***(domains.txt)*** and pass it to dnsmap-bulk.sh:

```
root@kali:~# echo "example.com" >> domains.txt
root@kali:~# echo "example.org" >> domains.txt
root@kali:~# dnsmap-bulk.sh domains.txt
dnsmap 0.30 - DNS Network Mapper by pagvac (gnucitizen.org)

[+] searching (sub)domains for example.com using built-in wordlist
[+] using maximum random delay of 10 millisecond(s) between requests
```