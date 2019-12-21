# DMitry

February 18, 2014

[Information Gathering](https://tools.kali.org/category/information-gathering)

## DMitry Package Description

DMitry (Deepmagic Information Gathering Tool) is a UNIX/(GNU)Linux Command Line Application coded in C. DMitry has the ability to gather as much information as possible about a host. Base functionality is able to gather possible subdomains, email addresses, uptime information, tcp port scan, whois lookups, and more.

The following is a list of the current features:

- An Open Source Project.
- Perform an Internet Number whois lookup.
- Retrieve possible uptime data, system and server data.
- Perform a SubDomain search on a target host.
- Perform an E-Mail address search on a target host.
- Perform a TCP Portscan on the host target.
- A Modular program allowing user specified modules

Source: http://mor-pah.net/software/dmitry-deepmagic-information-gathering-tool/
[DMitry Homepage](http://mor-pah.net/software/dmitry-deepmagic-information-gathering-tool/) | [Kali DMitry Repo](https://gitlab.com/kalilinux/packages/dmitry.git;a=summary)

- Author: James Greig
- License: GPLv3

### Tools included in the dmitry package

##### dmitry – Deepmagic Information Gathering Tool



<iframe src="https://asciinema.org/a/31154/embed?" id="asciicast-iframe-31154" name="asciicast-iframe-31154" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 638px; float: none; visibility: visible; height: 530px;"></iframe>


```
root@kali:~# dmitry -h
Deepmagic Information Gathering Tool
"There be some deep magic going on"

dmitry: invalid option -- 'h'
Usage: dmitry [-winsepfb] [-t 0-9] [-o %host.txt] host
-o Save output to %host.txt or to file specified by -o file
-i Perform a whois lookup on the IP address of a host
-w Perform a whois lookup on the domain name of a host
-n Retrieve Netcraft.com information on a host
-s Perform a search for possible subdomains
-e Perform a search for possible email addresses
-p Perform a TCP port scan on a host
\* -f Perform a TCP port scan on a host showing output reporting filtered ports
\* -b Read in the banner received from the scanned port
\* -t 0-9 Set the TTL in seconds when scanning a TCP port ( Default 2 )
*Requires the -p flagged to be passed
```

### dmitry Usage Example

Run a ***domain whois lookup (w)***, an ***IP whois lookup (i)***, retrieve ***Netcraft info (n)***, search for ***subdomains (s)***, search for ***email addresses (e)***, do a TCP port scan ***(p)***, and save the output to ***example.txt (o)*** for the domain ***example.com***:

```
root@kali:~# dmitry -winsepo example.txt example.com
Deepmagic Information Gathering Tool
"There be some deep magic going on"

Writing output to 'example.txt'

HostIP:93.184.216.119
HostName:example.com

Gathered Inet-whois information for 93.184.216.119
\---------------------------------
```

infogathering, portscanning, recon
Related Posts
WOL-E
18 Feb 2014
lbd
18 Feb 2014
CaseFile
19 Feb 2014