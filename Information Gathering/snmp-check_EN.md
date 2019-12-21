## snmp-check Package Description

Like to snmpwalk, snmp-check allows you to enumerate the SNMP devices and places the output in a very human readable friendly format. It could be useful for penetration testing or systems monitoring. Distributed under GPL license and based on “Athena-2k” script by jshaw.

Features
snmp-check supports the following enumerations:

- contact
- description
- detect write access (separate action by enumeration)
- devices
- domain
- hardware and storage informations
- hostname
- IIS statistics
- IP forwarding
- listening UDP ports
- location
- motd
- mountpoints
- network interfaces
- network services
- processes
- routing information
- software components
- system uptime
- TCP connections
- total memory
- uptime
- user accounts

Source: http://www.nothink.org/codes/snmpcheck/index.php
[snmp-check Homepage](http://www.nothink.org/codes/snmpcheck/index.php) | [Kali snmp-check Repo](https://gitlab.com/kalilinux/packages/snmpcheck.git;a=summary)

- Author: Matteo Cantoni
- License: GPLv2

### Tools included in the snmp-check package

##### snmp-check – SNMP service enumeration tool

```
root@kali:~# snmp-check -h
snmp-check v1.9 - SNMP enumerator
Copyright (c) 2005-2015 by Matteo Cantoni (www.nothink.org)

 Usage: snmp-check [OPTIONS] <target IP address>

 -p --port     : SNMP port. Default port is 161;
 -c --community  : SNMP community. Default is public;
 -v --version   : SNMP version (1,2c). Default is 1;

 -w --write    : detect write access (separate action by enumeration);

 -d --disable_tcp : disable TCP connections enumeration!
 -t --timeout   : timeout in seconds. Default is 5;
 -r --retries   : request retries. Default is 1;
 -i --info     : show script version;
 -h --help     : show help menu;

root@kali:~#
```

### snmp-check Usage Example

Scan the target host ***(192.168.1.2)*** using the public SNMP community string ***(-c public)***:

```
root@kali:~# snmp-check 192.168.1.2 -c public
snmp-check v1.9 - SNMP enumerator
Copyright (c) 2005-2015 by Matteo Cantoni (www.nothink.org)

[+] Try to connect to 192.168.1.2:161 using SNMPv1 and community 'public'

[*] System information:

 Host IP address        : 192.168.1.2
 Hostname            : ...retracted...
 Description          : ...retracted...
 Contact            : ...retracted...
 Location            : ...retracted...
 Uptime snmp          : -
 Uptime system         : 3 days, 00:13:51.05
 System date          : -

[*] Network information:

....SNIP...

[*] Network interfaces:

....SNIP...


[*] Network IP:

....SNIP...

[*] Routing information:

....SNIP...

[*] TCP connections and listening ports:

....SNIP...

[*] Listening UDP ports:

....SNIP...

root@kali:~#
```