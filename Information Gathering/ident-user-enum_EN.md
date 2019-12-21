## ident-user-enum Package Description

ident-user-enum is a simple PERL script to query the ident service (113/TCP) in order to determine the owner of the process listening on each TCP port of a target system.
This can help to prioritise target service during a pentest (you might want to attack services running as root first). Alternatively, the list of usernames gathered can be used for password guessing attacks on other network services.

Source: http://pentestmonkey.net/tools/user-enumeration/ident-user-enum
[ident-user-enum Homepage](http://pentestmonkey.net/tools/user-enumeration/ident-user-enum) | [Kali ident-user-enum Repo](https://gitlab.com/kalilinux/packages/ident-user-enum.git)

- Author: pentestmonkey
- License: GPLv2

### Tools included in the ident-user-enum package

##### ident-user-enum – Query ident to determine the owner of a TCP network process

```
root@kali:~# ident-user-enum
ident-user-enum v1.0 ( http://pentestmonkey.net/tools/ident-user-enum )

Usage: ident-user-enum.pl ip port [ port [ port ... ] ]

Queries the ident service (113/TCP) to determine the OS-level user running
the process listening on a given TCP port.  More than one port can be supplied.
```

### ident-user-enum Usage Examples

Scan the remote host (***192.168.1.13***) and determine which user is running the service on the specified ports (***22 139 445***).

```
root@kali:~# ident-user-enum 192.168.1.13 22 139 445
ident-user-enum v1.0 ( http://pentestmonkey.net/tools/ident-user-enum )

192.168.1.13:22 root
192.168.1.13:139  root
192.168.1.13:445  root
```



<iframe src="https://asciinema.org/a/107704/embed?" id="asciicast-iframe-107704" name="asciicast-iframe-107704" scrolling="no" allowfullscreen="true" style="box-sizing: border-box; max-width: 100%; border: 0px; overflow: hidden; margin: 0px; display: inline-block; width: 678px; float: none; visibility: visible; height: 563px;"></iframe>