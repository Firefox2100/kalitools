## p0f Package Description

P0f is a tool that utilizes an array of sophisticated, purely passive traffic fingerprinting mechanisms to identify the players behind any incidental TCP/IP communications (often as little as a single normal SYN) without interfering in any way. Version 3 is a complete rewrite of the original codebase, incorporating a significant number of improvements to network-level fingerprinting, and introducing the ability to reason about application-level payloads (e.g., HTTP).
Some of p0f’s capabilities include:

- Highly scalable and extremely fast identification of the operating system and software on both endpoints of a vanilla TCP connection – especially in settings where NMap probes are blocked, too slow, unreliable, or would simply set off alarms.

- Measurement of system uptime and network hookup, distance (including topology behind NAT or packet filters), user language preferences, and so on.

- Automated detection of connection sharing / NAT, load balancing, and application-level proxying setups.

- Detection of clients and servers that forge declarative statements such as X-Mailer or User-Agent.

The tool can be operated in the foreground or as a daemon, and offers a simple real-time API for third-party components that wish to obtain additional information about the actors they are talking to.

Common uses for p0f include reconnaissance during penetration tests; routine network monitoring; detection of unauthorized network interconnects in corporate environments; providing signals for abuse-prevention tools; and miscellanous forensics.

Source: http://lcamtuf.coredump.cx/p0f3/
  [p0f Homepage](http://lcamtuf.coredump.cx/p0f3/) | [Kali p0f Repo](https://gitlab.com/kalilinux/packages/p0f.git;a=summary)

- Author: Michal Zalewski
- License: LGPL-2

### Tools included in the p0f package

##### p0f – Passive OS fingerprinting tool

```
root@kali:~# p0f -h
--- p0f 3.09b by Michal Zalewski <lcamtuf@coredump.cx> ---

p0f: invalid option -- 'h'
Usage: p0f [ ...options... ] [ 'filter rule' ]

Network interface options:

  -i iface  - listen on the specified network interface
  -r file  - read offline pcap data from a given file
  -p     - put the listening interface in promiscuous mode
  -L     - list all available interfaces

Operating mode and output settings:

  -f file  - read fingerprint database from 'file' (/etc/p0f/p0f.fp)
  -o file  - write information to the specified log file
  -s name  - answer to API queries at a named unix socket
  -u user  - switch to the specified unprivileged account and chroot
  -d     - fork into background (requires -o or -s)

Performance-related options:

  -S limit  - limit number of parallel API connections (20)
  -t c,h   - set connection / host cache age limits (30s,120m)
  -m c,h   - cap the number of active connections / hosts (1000,10000)

Optional filter expressions (man tcpdump) can be specified in the command
line to prevent p0f from looking at incidental network traffic.

Problems? You can reach the author at <lcamtuf@coredump.cx>.
```

### p0f Usage Example

Use interface eth0 ***(-i eth0)*** in promiscuous mode ***(-p)***, saving the results to a file ***(-o /tmp/p0f.log)***:

```
root@kali:~# p0f -i eth0 -p -o /tmp/p0f.log
-- p0f 3.09b by Michal Zalewski <lcamtuf@coredump.cx> ---

[+] Closed 1 file descriptor.
[+] Loaded 322 signatures from '/etc/p0f/p0f.fp'.
[+] Intercepting traffic on interface 'eth0'.
[+] Default packet filtering configured [+VLAN].
[+] Log file '/tmp/p0f.log' opened for writing.
[+] Entered main event loop.

.-[ 192.168.1.15/35834 -> 173.246.39.185/873 (syn) ]-
|
| client  = 192.168.1.15/35834
| os    = Linux 3.11 and newer
| dist   = 0
| params  = none
| raw_sig  = 4:64+0:0:1460:mss*20,7:mss,sok,ts,nop,ws:df,id+:0
```