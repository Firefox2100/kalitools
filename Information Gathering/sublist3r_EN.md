## sublist3r Package Description

Sublist3r is a python tool designed to enumerate subdomains of websites using OSINT. It helps penetration testers and bug hunters collect and gather subdomains for the domain they are targeting. Sublist3r enumerates subdomains using many search engines such as Google, Yahoo, Bing, Baidu, and Ask. Sublist3r also enumerates subdomains using Netcraft, Virustotal, ThreatCrowd, DNSdumpster, and ReverseDNS.

Source: https://github.com/aboul3la/Sublist3r
[Sublist3r Homepage](https://github.com/aboul3la/Sublist3r) | [Kali sublist3r Repo](https://gitlab.com/kalilinux/packages/sublist3r.git)

- Author: Ahmed Aboul-Ela
- License: GPL-2+

### Tools included in the sublist3r package

##### sublist3r – Fast subdomains enumeration tool for penetration testers

```
root@kali:~# sublist3r -h
usage: sublist3r [-h] -d DOMAIN [-b [BRUTEFORCE]] [-p PORTS] [-v [VERBOSE]]
         [-t THREADS] [-e ENGINES] [-o OUTPUT]

OPTIONS:
 -h, --help       show this help message and exit
 -d DOMAIN, --domain DOMAIN
            Domain name to enumerate it's subdomains
 -b [BRUTEFORCE], --bruteforce [BRUTEFORCE]
            Enable the subbrute bruteforce module
 -p PORTS, --ports PORTS
            Scan the found subdomains against specified tcp ports
 -v [VERBOSE], --verbose [VERBOSE]
            Enable Verbosity and display results in realtime
 -t THREADS, --threads THREADS
            Number of threads to use for subbrute bruteforce
 -e ENGINES, --engines ENGINES
            Specify a comma-separated list of search engines
 -o OUTPUT, --output OUTPUT
            Save the results to text file

Example: python /usr/share/sublist3r/sublist3r -d google.com
```

### sublist3r Usage Examples

Search for subdomains of kali.org (***-d kali.org***) using the Bing search engine (***-e bing***) with 3 threads (***-t 3***).

```
root@kali:~# sublist3r -d kali.org -t 3 -e bing

         ____     _   _ _   _  _____
        / ___| _  _| |__ | (_)___| |_|___ / _ __
        \___ \| | | | '_ \| | / __| __| |_ \| '__|
         ___) | |_| | |_) | | \__ \ |_ ___) | |
        |____/ \__,_|_.__/|_|_|___/\__|____/|_|

        \# Coded By Ahmed Aboul-Ela - @aboul3la
  
[-] Enumerating subdomains now for kali.org
[-] Searching now in Bing..
[-] Total Unique Subdomains Found: 19
www.kali.org
archive-3.kali.org
archive-4.kali.org
archive-5.kali.org
bugs.kali.org
cdimage.kali.org
docs.kali.org
ar.docs.kali.org
he.docs.kali.org
id.docs.kali.org
tr.docs.kali.org
forums.kali.org
git.kali.org
http.kali.org
images.kali.org
pkg.kali.org
repo.kali.org
security.kali.org
tools.kali.org
```