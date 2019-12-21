## InTrace Package Description

InTrace is a traceroute-like application that enables users to enumerate IP hops exploiting existing TCP connections, both initiated from local network (local system) or from remote hosts. It could be useful for network reconnaissance and firewall bypassing.

Source: https://github.com/robertswiecki/intrace
[InTrace Homepage](https://github.com/robertswiecki/intrace) | [Kali InTrace Repo](https://gitlab.com/kalilinux/packages/intrace.git;a=summary)

- Author: Robert Swiecki
- License: GPLv3

### Tools included in the intrace package

##### intrace – Traceroute-like application piggybacking on existing TCP connections

```
root@kali:~# intrace
InTrace, version 1.5 (C)2007-2011 Robert Swiecki <robert@swiecki.net>
2014/05/20 09:59:29.627368 <INFO> Usage: intrace <-h hostname> [-p <port>] [-d <debuglevel>] [-s <payloadsize>] [-6]
```

### intrace Usage Example

Run a trace to the target host ***(-h www.example.com)*** using port 80 ***(-p 80)*** with a packet size of 4 bytes ***(-s 4)***:

```
root@kali:~# intrace -h www.example.com -p 80 -s 4
InTrace 1.5 -- R: 93.184.216.119/80 (80) L: 192.168.1.130/51654
Payload Size: 4 bytes, Seq: 0x0d6dbb02, Ack: 0x8605bff0
Status: Packets sent #8

 \#  [src addr]     [icmp src addr]   [pkt type]
 \1.  [192.168.1.1   ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \2.  [192.168.0.1   ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \3.  [  ---      ]  [  ---      ]  [NO REPLY]
 \4.  [64.59.184.185  ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \5.  [66.163.70.25  ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \6.  [66.163.64.150  ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \7.  [66.163.75.117  ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
 \8.  [206.223.119.59 ]  [93.184.216.119 ]  [ICMP_TIMXCEED]
```