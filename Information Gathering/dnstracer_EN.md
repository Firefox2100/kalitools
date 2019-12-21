## dnstracer Package Description

dnstracer determines where a given Domain Name Server (DNS) gets its information from for a given hostname, and follows the chain of DNS servers back to the authoritative answer.

Source: http://www.mavetju.org/unix/general.php
[dnstracer Homepage](http://freshmeat.net/projects/dnstracer) | [Kali dnstracer Repo](https://gitlab.com/kalilinux/packages/dnstracer.git;a=summary)

- Author: Edwin Groothuis
- License: BSD

### tools included in the dnstracer package

##### dnstracer – trace DNS queries to the source

```
root@kali:~# dnstracer
DNSTRACER version 1.8.1 - (c) Edwin Groothuis - http://www.mavetju.org
Usage: dnstracer [options] [host]
  -c: disable local caching, default enabled
  -C: enable negative caching, default disabled
  -o: enable overview of received answers, default disabled
  -q <querytype>: query-type to use for the DNS requests, default A
  -r <retries>: amount of retries for DNS requests, default 3
  -s <server>: use this server for the initial request, default localhost
         If . is specified, A.ROOT-SERVERS.NET will be used.
  -t <maximum timeout>: Limit time to wait per try
  -v: verbose
  -S <ip address>: use this source address.
  -4: don't query IPv6 servers
```

### dnstracer Usage Example

Scan a domain ***(example.com)***, retry up to 3 times ***(-r 3)***, and display verbose output ***(-v)***:

```
root@kali:~# dnstracer -r 3 -v example.com
Tracing to example.com[a] via 192.168.1.1, maximum of 3 retries
192.168.1.1 (192.168.1.1) IP HEADER
\- Destination address:  192.168.1.1
DNS HEADER (send)
```