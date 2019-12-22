## Xplico Package Description

The goal of Xplico is extract from an internet traffic capture the applications data contained. For example, from a pcap file Xplico extracts each email (POP, IMAP, and SMTP protocols), all HTTP contents, each VoIP call (SIP, MGCP, H323), FTP, TFTP, and so on. Xplico is not a network protocol analyzer.

Source: http://sourceforge.net/projects/xplico/files/Xplico%20versions
[Xplico Homepage](http://www.xplico.org/) | [Kali Xplico Repo](https://gitlab.com/kalilinux/packages/xplico.git;a=summary)

- Author: Gianluca Costa, Andre de Franceschi
- License: GPLv2

### Tools included in the xplico package

##### xplico – Network Forensic Analysis Tool (NFAT)

```
root@kali:~# xplico -h
xplico v1.2.1
Internet Traffic Decoder (NFAT).
See http://www.xplico.org for more information.

Copyright 2007-2017 Gianluca Costa & Andrea de Franceschi and contributors.
This is free software; see the source for copying conditions. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

This product includes GeoLite data created by MaxMind, available from http://www.maxmind.com/.

usage: xplico [-v] [-c <config_file>] [-h] [-s] [-g] [-l] [-i <prot>] -m <capute_module>
  -v version
  -c config file
  -h this help
  -i info of protocol 'prot'
  -g display graph-tree of protocols
  -l print all log in the screen
  -s print every second the deconding status
  -m capture type module
  NOTE: parameters MUST respect this order!
```

### xplico Usage Example

Use the rltm module ***(-m rltm)*** and analyze traffic on interface eth0 ***(-i eth0)***:

```
root@kali:~# xplico -m rltm -i eth0
xplico v1.0.1
Internet Traffic Decoder (NFAT).
See http://www.xplico.org for more information.

Copyright 2007-2012 Gianluca Costa & Andrea de Franceschi and contributors.
This is free software; see the source for copying conditions. There is NO
warranty; not even for MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.

This product includes GeoLite data created by MaxMind, available from http://www.maxmind.com/.
Configuration file (/opt/xplico/cfg/xplico_cli.cfg) found!
GeoLiteCity.dat found!
pcapf: running: 0/0, subflow:0/0, tot pkt:1
pol: running: 0/0, subflow:0/0, tot pkt:0
eth: running: 0/0, subflow:0/0, tot pkt:1
pppoe: running: 0/0, subflow:0/0, tot pkt:0
ppp: running: 0/0, subflow:0/0, tot pkt:0
ip: running: 0/0, subflow:0/0, tot pkt:0
```