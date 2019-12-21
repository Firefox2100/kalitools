## cisco-torch Package Description

Cisco Torch mass scanning, fingerprinting, and exploitation tool was written while working on the next edition of the “Hacking Exposed Cisco Networks”, since the tools available on the market could not meet our needs.

The main feature that makes Cisco-torch different from similar tools is the extensive use of forking to launch multiple scanning processes on the background for maximum scanning efficiency. Also, it uses several methods of application layer fingerprinting simultaneously, if needed. We wanted something fast to discover remote Cisco hosts running Telnet, SSH, Web, NTP and SNMP services and launch dictionary attacks against the services discovered.

Source: http://www.hackingciscoexposed.com/?link=tools
[cisco-torch Homepage](http://www.hackingciscoexposed.com/?link=tools) | [Kali cisco-torch Repo](https://gitlab.com/kalilinux/packages/cisco-torch.git;a=summary)

- Author: Born by Arhont Team
- License: LGPL-2.1

### Tools included in the cisco-torch package

##### cisco-torch – Cisco device scanner

```
root@kali:~# cisco-torch
Using config file torch.conf...
Loading include and plugin ...
 version
usage: cisco-torch <options> <IP,hostname,network>

or: cisco-torch <options> -F <hostlist>

Available options:
-O <output file>
-A   All fingerprint scan types combined
-t   Cisco Telnetd scan
-s   Cisco SSHd scan
-u   Cisco SNMP scan
-g   Cisco config or tftp file download
-n   NTP fingerprinting scan
-j   TFTP fingerprinting scan
-l <type>  loglevel
    c  critical (default)
    v  verbose
    d  debug
-w   Cisco Webserver scan
-z   Cisco IOS HTTP Authorization Vulnerability Scan
-c   Cisco Webserver with SSL support scan
-b   Password dictionary attack (use with -s, -u, -c, -w , -j or -t only)
-V   Print tool version and exit
examples:  cisco-torch -A 10.10.0.0/16
    cisco-torch -s -b -F sshtocheck.txt
    cisco-torch -w -z 10.10.0.0/16
    cisco-torch -j -b -g -F tftptocheck.txt
```

### cisco-torch Usage Example”

Run all available scan types ***(-A)*** against the target IP address ***(192.168.99.202)***:

```
root@kali:~# cisco-torch -A 192.168.99.202
Using config file torch.conf...
Loading include and plugin ...

\###############################################################
\#  Cisco Torch Mass Scanner          #
\#  Becase we need it...                    #
\#  http://www.arhont.com/cisco-torch.pl            #
\###############################################################

List of targets contains 1 host(s)
8853:  Checking 192.168.99.202 ...
HUH db not found, it should be in fingerprint.db
Skipping Telnet fingerprint
\* Cisco by SNMP found ***
*System Description: Cisco Internetwork Operating System Software
IOS (tm) 3600 Software (C3640-IK9O3S-M), Version 12.3(22), RELEASE SOFTWARE (fc2)
Technical Support: http://www.cisco.com/techsupport
Copyright (c) 1986-2007 by cisco Systems, Inc.
Compiled Wed 24-Jan-07 1

Cisco-IOS Webserver found
 HTTP/1.1 401 Unauthorized
Date: Tue, 13 Apr 1993 00:57:07 GMT
Server: cisco-IOS
Accept-Ranges: none
WWW-Authenticate: Basic realm="level_15_access"

401 Unauthorized


 Cisco WWW-Authenticate webserver found
 HTTP/1.1 401 Unauthorized
Date: Tue, 13 Apr 1993 00:57:07 GMT
Server: cisco-IOS
Accept-Ranges: none
WWW-Authenticate: Basic realm="level_15_access"

401 Unauthorized


--->
\- All scans done. Cisco Torch Mass Scanner  -
---> Exiting.
```