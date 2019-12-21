## copy-router-config Package Description

Copies configuration files from Cisco devices running SNMP.

[copy-router-config Homepage](http://www.offensive-security.com/) | [Kali copy-router-config Repo](https://gitlab.com/kalilinux/packages/copy-router-config.git;a=summary)

- Author: muts
- License: GPLv2

### Tools included in the copy-router-config package

##### copy-router-config.pl – Copies Cisco configs via SNMP

```
root@kali:~# copy-router-config.pl

\######################################################
\# Copy Cisco Router config  - Using SNMP
\# Hacked up by muts - muts@offensive-security.com
\#######################################################

Usage : ./copy-copy-config.pl <router-ip> <tftp-serverip> <community>

Make sure a TFTP server is set up, preferably running from /tmp !
```

[/toggle] [toggle title=”merge-router-config.pl – Merges Cisco configs via SNMP” variation=”deepblue”]

```
root@kali:~# merge-router-config.pl

\######################################################
\# Merge Cisco Router config  - Using SNMP
\# Hacked up by muts - muts@offensive-security.com
\#######################################################

Usage : ./merge-copy-config.pl <router-ip> <tftp-serverip> <community>

Make sure a TFTP server is set up, preferably running from /tmp !
```

### copy-router-config Usage Example

Copy the config from the router ***(192.168.1.1)*** to the TFTP server ***(192.168.1.15)***, authenticating with the community string ***(private)***:

```
root@kali:~# copy-router-config.pl 192.168.1.1 192.168.1.15 private
```

### merge-router-config Usage Example(s)

Merge the config with the router ***(192.168.1.1)***, copying from the TFTP server ***(192.168.1.15)***, using the community string ***(private)***:

```
root@kali:~# merge-router-config.pl 192.168.1.1 192.168.1.15 private
```