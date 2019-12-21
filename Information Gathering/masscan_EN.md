<iframe src="https://asciinema.org/a/31820/embed?" id="asciicast-iframe-31820" name="asciicast-iframe-31820" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 686px; float: none; visibility: visible; height: 627px;"></iframe>


## masscan Package Description

This is the fastest Internet port scanner. It can scan the entire Internet in under 6 minutes, transmitting 10 million packets per second.

It produces results similar to nmap, the most famous port scanner. Internally, it operates more like scanrand, unicornscan, and ZMap, using asynchronous transmission. The major difference is that it’s faster than these other scanners. In addition, it’s more flexible, allowing arbitrary address ranges and port ranges.

NOTE: masscan uses a custom TCP/IP stack. Anything other than simple port scans will cause conflict with the local TCP/IP stack. This means you need to either use the -S option to use a separate IP address, or configure your operating system to firewall the ports that masscan uses.

Source: https://github.com/robertdavidgraham/masscan
[masscan Homepage](https://github.com/robertdavidgraham/masscan) | [Kali masscan Repo](https://gitlab.com/kalilinux/packages/masscan.git;a=summary)

- Author: Robert Graham
- License: A-GPL-3

### Tools included in the masscan package

##### masscan – Asynchronous TCP port scanner

```
root@kali:~# masscan
usage:
masscan -p80,8000-8100 10.0.0.0/8 --rate=10000
 scan some web ports on 10.x.x.x at 10kpps
masscan --nmap
 list those options that are compatible with nmap
masscan -p80 10.0.0.0/8 --banners -oB <filename>
 save results of scan in binary format to <filename>
masscan --open --banners --readscan <filename> -oX <savefile>
 read binary scan results in <filename> and save them as xml in <savefile>
```

### masscan Usage Example

Scan for a selection of ports ***(-p22,80,445)*** across a given subnet ***(192.168.1.0/24)***:

```
root@kali:~# masscan -p22,80,445 192.168.1.0/24

Starting masscan 1.0.3 (http://bit.ly/14GZzcT) at 2014-05-13 21:35:12 GMT
 -- forced options: -sS -Pn -n --randomize-hosts -v --send-eth
Initiating SYN Stealth Scan
Scanning 256 hosts [3 ports/host]
Discovered open port 22/tcp on 192.168.1.217
Discovered open port 445/tcp on 192.168.1.220
Discovered open port 80/tcp on 192.168.1.230
```