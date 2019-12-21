## nbtscan-unixwiz Package Description

This is a command-line tool that scans for open NETBIOS nameservers on a local or remote TCP/IP network, and this is a first step in finding of open shares. It is based on the functionality of the standard Windows tool nbtstat, but it operates on a range of addresses instead of just one.

Source: http://unixwiz.net/tools/nbtscan.html
[nbtscan-unixwiz Homepage](http://unixwiz.net/tools/nbtscan.html) | [Kali nbtscan-unixwiz Repo](https://gitlab.com/kalilinux/packages/nbtscan-unixwiz.git;a=tree;h=refs/heads/kali/master;hb=refs/heads/kali/master)

- Author: Steve Friedl
- License: public-domain

### Tools included in the nbtscan-unixwiz package

##### nbtscan-unixwiz – Scanner for open NETBIOS nameservers

```
root@kali:~# nbtscan-unixwiz
nbtscan 1.0.35 - 2008-04-08 - http://www.unixwiz.net/tools/

usage: nbtscan-unixwiz [options] target [targets...]

  Targets are lists of IP addresses, DNS names, or address
  ranges. Ranges can be in /nbits notation ("192.168.12.0/24")
  or with a range in the last octet ("192.168.12.64-97")

  -V     show Version information
  -f     show Full NBT resource record responses (recommended)
  -H     generate HTTP headers
  -v     turn on more Verbose debugging
  -n     No looking up inverse names of IP addresses responding
  -p <n>   bind to UDP Port <n> (default=0)
  -m     include MAC address in response (implied by '-f')
  -T <n>   Timeout the no-responses in <n> seconds (default=2 secs)
  -w <n>   Wait <n> msecs after each write (default=10 ms)
  -t <n>   Try each address <n> tries (default=1)
  -P     generate results in perl hashref format
```

### nbtscan-unixwiz Usage Examples

Scan a range of IP addresses ***(192.168.0.100-110)*** without doing inverse name lookups ***(-n)***:

```
root@kali:~# nbtscan-unixwiz -n 192.168.0.100-110
192.168.0.105  WORKGROUP\RETROPIE        SHARING
*timeout (normal end of scan)
```

Scan a single IP address ***(192.168.0.38)*** and show Full NBT resource record responses ***(-f)***:

```
root@kali:~# nbtscan-unixwiz -f 192.168.0.38
192.168.0.38   WORKGROUP\DOOKOSSEL       SHARING
 DOOKOSSEL    <00> UNIQUE Workstation Service
 DOOKOSSEL    <03> UNIQUE Messenger Service<3>
 DOOKOSSEL    <20> UNIQUE File Server Service
 ..__MSBROWSE__.<01> GROUP  Master Browser
 WORKGROUP    <00> GROUP  Domain Name
 WORKGROUP    <1d> UNIQUE Master Browser
 WORKGROUP    <1e> GROUP  Browser Service Elections
 00:00:00:00:00:00  ETHER
```



<iframe src="https://asciinema.org/a/104243/embed?" id="asciicast-iframe-104243" name="asciicast-iframe-104243" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 627px;"></iframe>